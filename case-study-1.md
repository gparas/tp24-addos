---
layout: cases
---

{% for addon in site.data.addons %}
  <div class="card mb-3">
    <div class="card-body p-lg-4">
      <div class="row">
        <div class="col-md-auto d-flex mb-4">
          <div class="addons-icon">
            {% include icon-{{ addon.title | downcase | replace: " ", "_" }}.html %}
          </div>
        </div>
        <div class="col-md">
          <div class="d-flex align-items-center mb-2">
            <h4 class="card-title mb-0 mr-2">{{ addon.title }}</h4>
            {% unless addon.badge == false %}
              <span class="badge badge-pill {% if addon.badge != 'Special Offer' %}badge-info{% else %}badge-danger{% endif %}">
                {{ addon.badge }}
              </span>
            {% endunless %}
          </div>
          <p class="card-text d-none d-md-block">{{"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vestibulum maximus convallis quam, sit amet volutpat lorem eleifend congue. Nullam eget tristique ante, id sagittis tellus." | truncatewords: 12 }}</p>
          <ul class="fa-ul ml-4">
          {% for service in addon.services %}
            <li>
              <span class="fa-li"><i class="fas fa-check text-success"></i></span>{{ service }}
            </li>
          {% endfor %}
          </ul>
        </div>
        <div class="col-md-auto text-center d-flex d-md-block align-self-center align-items-center">
          <div class="text-primary h3 mb-0">{{ addon.price | prepend: "€" }}</div>
          <div class="text-small text-muted mb-0 mb-md-3">/ person</div>
          <div class="btn-group ml-auto" role="group">
            <button type="button" class="btn btn-default">
              <i class="fas fa-circle text-muted"></i>
              <span class="pl-1">Yes</span>
            </button>
            <button type="button" class="btn btn-default">
              <i class="fas fa-circle text-muted"></i>
              <span class="pl-1">No</span>
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
{% endfor %}
