---
layout: default
title: "MPG Tech | Soluções Têxteis"
---

<main class="container">

  <!-- Proposta -->
  <section id="proposta">
    <h2>Sua Conexão Estratégica no Setor Têxtil</h2>
    <p>Com foco em eficiência, qualidade e atendimento consultivo, sou o elo entre sua confecção e três das maiores referências do mercado nacional. Minha missão é entender as demandas da sua produção e fornecer as melhores soluções em insumos e serviços.</p>
    <p>Otimize sua cadeia de suprimentos contando com a excelência em fios, aviamentos e tinturaria.</p>
  </section>

  <!-- Aviamentos -->
  <section id="aviamentos" class="empresa-circulo">
    <h2>Círculo | Aviamentos Industriais</h2>
    <div class="carrossel-3x1" id="carrossel-circulo">
      <div class="carrossel-lista-imagens">
        <img src="{{ site.baseurl }}/imagens/circulo_linha_120_2.png" alt="">
        <img src="{{ site.baseurl }}/imagens/circulo_fitas_1.png" alt="">
        <img src="{{ site.baseurl }}/imagens/circulo_linha_overlock_1.png" alt="">
        <img src="{{ site.baseurl }}/imagens/circulo_ziper_1.png" alt="">
        <img src="{{ site.baseurl }}/imagens/circulo_colas.png" alt="">
        <img src="{{ site.baseurl }}/imagens/circulo_tesoura.png" alt="">
      </div>
    </div>
    <p>Linhas, zíperes e aviamentos industriais fornecidos pela Círculo S/A.</p>
  </section>

  <!-- Tinturaria -->
  <section id="tinturaria" class="empresa-gs">
    <h2>GS Tinturaria | Tingimento de Malhas</h2>
    <div class="carrossel-3x1" id="carrossel-gs">
      <div class="carrossel-lista-imagens">
        <img src="{{ site.baseurl }}/imagens/gs_acabamento_1.png" alt="">
        <img src="{{ site.baseurl }}/imagens/gs_acabamento_2.png" alt="">
        <img src="{{ site.baseurl }}/imagens/gs_acabamento_3.png" alt="">
        <img src="{{ site.baseurl }}/imagens/gs_maquinas_1.png" alt="">
        <img src="{{ site.baseurl }}/imagens/gs_rama_1.png" alt="">
      </div>
    </div>
    <p>Serviços de tingimento e acabamento com qualidade e pontualidade garantidas.</p>
  </section>

  <!-- Fios -->
  <section id="fios" class="empresa-cremer">
    <h2>Fios Têxteis de Poliamida (Nylon)</h2>
    <div class="carrossel-3x1" id="carrossel-cremer">
      <div class="carrossel-lista-imagens">
        <img src="{{ site.baseurl }}/imagens/cremer_homem_1.png" alt="">
        <img src="{{ site.baseurl }}/imagens/cremer_pecas_1.png" alt="">
        <img src="{{ site.baseurl }}/imagens/cremer_mulher_1.png" alt="">
        <img src="{{ site.baseurl }}/imagens/cremer_pecas_2.png" alt="">
        <img src="{{ site.baseurl }}/imagens/cremer_pecas_3.png" alt="">
      </div>
    </div>

    <p>Os fios de poliamida importados e distribuídos pela Cremer Erzkontor são sinônimo de tecnologia e performance no desenvolvimento de tecidos.</p>
    <p>Ofereço acesso direto a este insumo de alto valor, ideal para produtos que exigem toque macio, resistência e excelência em malharia e tecelagem.</p>
    <ul>
      <li>Distribuição, importação direta e financiamento de importação.</li>
      <li>Especificações técnicas e prazos sob consulta.</li>
    </ul>
  </section>

  <!-- Blog -->
  <section id="blog">
    <h2>Blog | Notícias e Conteúdo Têxtil</h2>
    <p>Acompanhe novidades do setor, tendências e atualizações.</p>
    <div class="blog-container">
      {% for post in site.posts limit:3 %}
        <div class="blog-card">
          {% if post.image %}
            <img src="{{ post.image | relative_url }}" alt="{{ post.title }}" class="thumb-blog">
          {% endif %}
          <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
          <p class="data-post">{{ post.date | date: "%d de %B de %Y" }}</p>
          <p>{{ post.excerpt }}</p>
          <a class="leia-mais" href="{{ post.url | relative_url }}">Ler mais →</a>
        </div>
      {% endfor %}
    </div>
    <p style="text-align:center; margin-top:20px;">
      <a href="{{ '/blog/' | relative_url }}">Ver todos os posts</a>
    </p>
  </section>

  <!-- Contato -->
  <section id="contato">
    <h2>Entre em Contato Agora</h2>
    <p>Sua produção não pode parar. Fale comigo:</p>
    <p>
      <strong>Mauricio Josefowicz</strong><br>
      Telefone / WhatsApp: <a href="https://wa.me/5547999977900" target="_blank">(47) 99997‑7900</a><br>
      E‑mail: <a href="mailto:mauricio.mpgtech@gmail.com">mauricio.mpgtech@gmail.com</a><br>
      Instagram: <a href="https://www.instagram.com/mpgtech" target="_blank">@mpgtech</a>
    </p>
  </section>

</main>

<script>
  function iniciarCarrossel(idCarrossel, intervalo) {
    const carrossel = document.getElementById(idCarrossel);
    if (!carrossel) return;
    const lista = carrossel.querySelector('.carrossel-lista-imagens');
    const imagens = Array.from(lista.querySelectorAll('img'));
    const blocos = [];
    const num = imagens.length;
    for (let i = 0; i < num; i += 3) {
      const bloco = document.createElement('div');
      bloco.classList.add('carrossel-bloco');
      for (let j = 0; j < 3; j++) {
        const img = imagens[(i + j) % num];
        bloco.append(img.cloneNode(true));
      }
      blocos.push(bloco);
      carrossel.append(bloco);
    }
    lista.remove();
    let indice = 0;
    function mostrar(i){
      blocos.forEach(b=>b.classList.remove('ativo'));
      blocos[i].classList.add('ativo');
    }
    function proximo(){
      indice=(indice+1)%blocos.length; mostrar(indice);
    }
    mostrar(indice);
    if(blocos.length>1) setInterval(proximo,intervalo);
  }
  document.addEventListener('DOMContentLoaded',()=>{
    iniciarCarrossel('carrossel-circulo',5000);
    iniciarCarrossel('carrossel-gs',5000);
    iniciarCarrossel('carrossel-cremer',5000);
  });
</script>
