---
layout: page
title: Books
permalink: /books/
nav: true
nav_order: 3
description: Favourite quotes and the books shaping my thinking, by topic.
---

## Favourite quotes

<!-- Awaiting Aravind's content — do not fill without approval. -->

## Bookshelf

{% for shelf in site.data.books.shelves %}
<h3 class="book-topic">{{ shelf.topic }}</h3>
{% if shelf.books and shelf.books.size > 0 %}
<div class="book-shelf">
{% for b in shelf.books %}
<figure class="book">
{% if b.cover %}<img class="book-cover" src="{{ b.cover }}" alt="{{ b.title }} cover" loading="lazy">{% else %}<span class="book-cover book-cover--placeholder"></span>{% endif %}
<figcaption class="book-meta">
<span class="book-title">{{ b.title }}</span>
{% if b.author %}<span class="book-author">{{ b.author }}</span>{% endif %}
{% if b.thoughts %}<span class="book-thoughts">{{ b.thoughts }}</span>{% endif %}
</figcaption>
</figure>
{% endfor %}
</div>
{% else %}
<p class="shelf-empty">Coming soon.</p>
{% endif %}
{% endfor %}
