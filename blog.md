---
layout: default
title: cheatsheet
permalink: /cheatsheet/
---

<h1 class="text-3xl font-bold mb-12 tracking-tight">Config Guides</h1>

<div class="flex flex-col gap-10">
  {% for post in site.posts %}
  <article class="group cursor-pointer">
    <a href="{{ post.url | relative_url }}" class="block">
      <div class="flex flex-col md:flex-row md:items-baseline gap-2 md:gap-8">
        <span class="text-sm text-gray-400 font-medium w-32 shrink-0">
          {{ post.date | date: "%B %d, %Y" }}
        </span>
        <div>
          <h2 class="text-xl font-bold text-gray-900 dark:text-gray-100 group-hover:text-blue-600 dark:group-hover:text-blue-400 transition-colors mb-2">
            {{ post.title }}
          </h2>
          <p class="text-gray-500 dark:text-gray-400 leading-relaxed max-w-2xl">
            {{ post.excerpt | strip_html | truncatewords: 25 }}
          </p>
          <span class="text-xs text-gray-400 mt-2 block">
            {% assign words = post.content | number_of_words %}
            {% if words < 360 %}
              1 min read
            {% else %}
              {{ words | divided_by: 180 }} min read
            {% endif %}
          </span>
        </div>
      </div>
    </a>
  </article>
  {% endfor %}
</div>
