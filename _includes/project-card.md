<div class="card">
  <h3><a href="{{ include.href }}">{{ include.title }}</a></h3>
  <p>{{ include.summary }}</p>
  <ul class="tags">
    {% assign tlist = include.tags | split: ',' %}
    {% for t in tlist %}
      <li>{{ t | strip }}</li>
    {% endfor %}
  </ul>
</div>
