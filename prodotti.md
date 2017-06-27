---
layout: page
title: Prodotti
permalink: /prodotti/
---

Questo è un elenco dei nostri prodotti

{% for product in site.pasta %}
  <div class="pasta">
    <h2 class="pasta-title">{{ product.title }}</h2>
    
    {% if product.images[0] != null %}
        <!-- Immagine inserita -->
    {% assign image = product.images[0] %}
            <div class="img_crop">
                <img src="{{ image.url }}" alt="{{ image.alt }}">
            </div>
        {% else %}
        <!-- Immagine non inserita -->
    {% endif %}
    
    {{ product.content }}
  </div>
{% endfor %}