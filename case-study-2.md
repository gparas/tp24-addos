---
layout: cases
---

{% for addon in site.data.addons %}
  <div class="card mb-4">
    <div class="card-header bg-white addons-header">
      <div class="row">
        <div class="col-md-auto d-none d-md-flex">
          {% include icon-{{ addon.title | downcase | replace: " ", "_" }}-48.html %}
        </div>
        <div class="col-md">
          <div class="d-flex align-items-center">
            <h4 class="card-title mb-0 mr-2">{{ addon.title }}</h4>
            {% unless addon.badge == false %}
              <span class="badge badge-pill {% if addon.badge != 'Special Offer' %}badge-info{% else %}badge-danger{% endif %}">
                {{ addon.badge }}
              </span>
            {% endunless %}
          </div>
          <p class="card-text text-muted d-none d-md-block">{{"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vestibulum maximus convallis quam, sit amet volutpat lorem eleifend congue. Nullam eget tristique ante, id sagittis tellus." | truncatewords: 8 }}</p>
        </div>
      </div>
    </div>
    <div class="list-group list-group-flush">
      <label
        for="{{ addon.title | downcase | replace: " ", "-" }}-yes"
        class="list-group-item border-dashed p-md-4"
      >
        <div class="row align-items-center">
          <div class="col-md-auto">
            <input id="{{ addon.title | downcase | replace: " ", "-" }}-yes" type="radio" name="{{ addon.title | downcase | replace: " ", "-" }}">
          </div>
          <div class="col-md">
            <ul class="fa-ul ml-4 mb-0">
            {% for service in addon.services %}
              <li>
                <span class="fa-li"><i class="fas fa-check text-success"></i></span>{{ service }}
              </li>
            {% endfor %}
            </ul>
          </div>
          <div class="col-md">
            <div class="text-primary h3 mb-0">{{ addon.price | prepend: "€" }}</div>
          </div>
        </div>
        
      </label>
      <label
        for="{{ addon.title | downcase | replace: " ", "-" }}-no"
        class="list-group-item border-dashed p-md-4"
      >
        <input id="{{ addon.title | downcase | replace: " ", "-" }}-no" type="radio" name="{{ addon.title | downcase | replace: " ", "-" }}">
        No thanks, I will take the risk
      </label>
    </div>
  </div>
{% endfor %}
