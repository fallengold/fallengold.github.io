<h2 id="publications">Publications</h2>

<div class="publications publication-list">
  {% for paper in site.data.publications.main %}
  <article class="publication-entry{% unless paper.image %} publication-entry-text-only{% endunless %}">
    {% if paper.image %}
    <div class="publication-figure">
      {% if paper.image_link %}<a href="{{ paper.image_link }}" target="_blank" rel="noopener" aria-label="View full-resolution figure for {{ paper.title | escape }}">{% endif %}
        <img src="{{ paper.image }}" alt="{{ paper.image_alt | default: paper.title | escape }}" loading="lazy">
      {% if paper.image_link %}</a>{% endif %}
      {% if paper.conference_short %}<span class="publication-badge">{{ paper.conference_short }}</span>{% endif %}
    </div>
    {% endif %}
    <div class="publication-info">
      <h3 class="publication-title">{% if paper.pdf %}<a href="{{ paper.pdf }}">{{ paper.title }}</a>{% else %}{{ paper.title }}{% endif %}</h3>
      <div class="publication-authors">{{ paper.authors }}</div>
      <div class="publication-venue"><em>{{ paper.conference }}</em></div>
      <div class="publication-links">
        {% if paper.pdf %}<a href="{{ paper.pdf }}" target="_blank" rel="noopener">PDF</a>{% endif %}
        {% if paper.code %}<a href="{{ paper.code }}" target="_blank" rel="noopener">Code</a>{% endif %}
        {% if paper.page %}<a href="{{ paper.page }}" target="_blank" rel="noopener">Project Page</a>{% endif %}
        {% if paper.bibtex %}<a href="{{ paper.bibtex }}" target="_blank" rel="noopener">BibTeX</a>{% endif %}
        {% if paper.image_link %}<a href="{{ paper.image_link }}" target="_blank" rel="noopener">Figure PDF</a>{% endif %}
        {% if paper.notes %}<span class="publication-note">{{ paper.notes }}</span>{% endif %}
      </div>
      {% if paper.summary %}
      <details class="publication-abstract">
        <summary>Overview</summary>
        <p>{{ paper.summary }}</p>
      </details>
      {% endif %}
    </div>
  </article>
  {% endfor %}
</div>
