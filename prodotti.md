---
layout: page
title: pages.products

namespace: products

permalink: /prodotti/
permalink_it: /prodotti/
permalink_en: /products/
permalink_jp: /shokuhin/
---

<!-- Introduzione -->
<section id="about" class="container content-section text-center">
    <div class="row">
        <div class="col-lg-8 col-lg-offset-2">
            <br/><br/>
            {% tf products_presentation.md %}
            <br/>
          </div>
    </div>
</section>


<section id="services">
<!-- Page Content -->
{% for post in site.pasta %}
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
                    {% if post.images[1] != null %}
                        <!-- Immagine inserita -->
                        {% assign image = post.images[1] %}
                            <br><br>
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
                    {% if post.images[1] != null %}
                        <!-- Immagine inserita -->
                        {% assign image = post.images[1] %}
                            <br><br>
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