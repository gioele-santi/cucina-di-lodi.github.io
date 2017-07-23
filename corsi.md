---
layout: page
title: Corsi
permalink: /corsi/
---

<!-- Introduzione -->
<section id="about" class="container content-section text-center">
    <div class="row">
        <div class="col-lg-8 col-lg-offset-2">
          <br/><br/>
          <h2>Corsi di cucina</h2>
          <br/>
            <p>Cucinare non è solo sminuzzare gli ingredienti, metterli in una padella e stare attenti a non bruciarli.</p>
            <p>Cucinare è anche saper scegliere gli ingredienti e maneggiarli con cura ed abbinarli al meglio.</p>
            <p>Comprendere le tecniche di cottura per esaltare i sapori.</p>
            <p>Ma anche capire meglio quello che mangiamo tutti i giorni, scegliere alternative più salutari e perché no risparmiare sulla spesa ma senza rinunciare alla qualità.</p>
            <br/>
          </div>
    </div>
</section>


<section id="services">
<!-- Page Content -->
{% for post in site.corsi %}
  {% capture thecycle %}{% cycle 'odd', 'even' %}{% endcapture %}
    {% if thecycle == 'odd' %}
    <div class="content-section-a">

        <div class="container">

            <div class="row">
                <div class="col-lg-5 col-sm-6">
                    {% include separator_heading.html %}
                    <div class="clearfix"></div>
                    <h2 class="section-heading">{{ post.title }}</h2>
                    <div class="lead">{{ post.content }}</div>
                </div>
                <div class="col-lg-5 col-lg-offset-2 col-sm-6">
                    {% if post.images[0] != null %}
                        <!-- Immagine inserita -->
                        {% assign image = post.images[0] %}
                            <img class="img-responsive img-rounded" src="{{ image.url }}" alt="{{ image.alt }}">
                        {% else %}
                        <!-- Immagine non inserita -->
                    {% endif %}
                </div>
            </div>

        </div>
        <!-- /.container -->

    </div>
    <!-- /.content-section-a -->
    {% else %}

    <div class="content-section-b">

        <div class="container">

            <div class="row">
                <div class="col-lg-5 col-lg-offset-1 col-sm-push-6  col-sm-6">
                    {% include separator_heading_reverse.html %}
                    <div class="clearfix"></div>
                    <h2 class="section-heading">{{ post.title }}</h2>
                    <div class="lead">{{ post.content }}</div>
                </div>
                <div class="col-lg-5 col-sm-pull-6  col-sm-6">
                  {% if post.images[0] != null %}
                        <!-- Immagine inserita -->
                        {% assign image = post.images[0] %}
                            <img class="img-responsive img-rounded" src="{{ image.url }}" alt="{{ image.alt }}">
                        {% else %}
                        <!-- Immagine non inserita -->
                    {% endif %}
                </div>
            </div>

        </div>
        <!-- /.container -->

    </div>
    <!-- /.content-section-b -->
    {% endif %}
{% endfor %}
</section>