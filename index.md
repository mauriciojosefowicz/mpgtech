---
layout: default
title: "MPG Tech | Soluções Têxteis"
---

<section id="proposta">
  <h2>Sua Conexão Estratégica no Setor Têxtil</h2>
  <p>Com foco em eficiência, qualidade e atendimento consultivo, sou o elo entre sua confecção e três das maiores referências do mercado nacional. Minha missão é entender as demandas da sua produção e fornecer as melhores soluções em insumos e serviços.</p>
  <p>Otimize sua cadeia de suprimentos contando com excelência em fios, aviamentos e tinturaria.</p>
</section>

<section id="aviamentos">
  <h2>Círculo | Aviamentos Industriais – Linhas e Zíperes</h2>
  <p>Representando a linha completa de insumos essenciais para a sua confecção: linhas de costura, zíperes e variados acessórios industriais.</p>
</section>

<section id="tinturaria">
  <h2>GS Tinturaria – Serviços de Tingimento de Malha</h2>
  <p>Parceira ideal para o serviço de valor agregado que sua malha exige — qualidade, uniformidade de cor e pontualidade.</p>
</section>

<section id="fios">
  <h2>Fios Têxteis de Alta Performance</h2>
  <p>Os fios de poliamida distribuídos pela Cremer Erzkontor representam tecnologia e performance no desenvolvimento de tecidos, ideais para produtos que exigem toque macio e resistência.</p>
</section>

<section id="blog">
  <h2>Blog | Conteúdo Têxtil</h2>
  <div class="blog-container">
    {% for post in site.posts limit:3 %}
      <div class="blog-card">
        {% if post.image %}
          <img src="{{ post.image }}" alt="{{ post.title }}" class="thumb-blog" />
        {% endif %}
        <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
        <p class="data-post">{{ post.date | date: "%d de %B de %Y" }}</p>
        <p>{{ post.excerpt }}</p>
        <a class="leia-mais" href="{{ post.url | relative_url }}">Ler mais →</a>
      </div>
    {% endfor %}
  </div>

  <p style="text-align:center; margin-top:20px;">
    <a href="{{ '/blog/' | relative_url }}">Ver todos os posts</a>
  </p>
</section>

<section id="contato">
  <h2>Entre em Contato</h2>
  <p>
    <strong>Mauricio Josefowicz</strong><br>
    Telefone / WhatsApp: <a href="https://wa.me/5547999977900" target="_blank">(47) 99997‑7900</a><br>
    E‑mail: <a href="mailto:mauricio.mpgtech@gmail.com">mauricio.mpgtech@gmail.com</a><br>
    Instagram: <a href="https://www.instagram.com/mpgtech" target="_blank">@mpgtech</a>
  </p>
</section>
