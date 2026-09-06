<div class="container my-5">
  <div class="row row-cols-1 row-cols-md-2 row-cols-lg-3 g-4">
    
    {% for post in site.posts %}
    <div class="col">
      <div class="card h-100 shadow-sm border-0 bg-light">
        
        <!-- Post Thumbnail Image (Optional) -->
        {% if post.image %}
        <img src="{{ post.image | relative_url }}" class="card-img-top" alt="{{ post.title }}" style="height: 200px; object-fit: cover;">
        {% else %}
        <!-- Fallback geometric banner if your post doesn't have an image -->
        <div class="bg-secondary text-white text-center py-5 card-img-top" style="height: 200px; opacity: 0.7;">
          <i class="bi bi-journal-text fs-1"></i>
        </div>
        {% endif %}

        <div class="card-body d-flex flex-column">
          <!-- Date and Metadata -->
          <small class="text-muted mb-2">
            <i class="bi bi-calendar3"></i> {{ post.date | date: "%B %d, %Y" }}
          </small>
          
          <!-- Post Title Link -->
          <h5 class="card-title font-weight-bold">
            <a href="{{ post.url | relative_url }}" class="text-dark text-decoration-none stretched-link">
              {{ post.title }}
            </a>
          </h5>
          
          <!-- Post Short Excerpt Summary -->
          <p class="card-text text-secondary small flex-grow-1">
            {{ post.excerpt | strip_html | truncatewords: 25 }}
          </p>
          
          <div class="mt-auto pt-3 border-top text-primary font-weight-bold small">
            Read Article <i class="bi bi-arrow-right"></i>
          </div>
        </div>
      </div>
    </div>
    {% endfor %}

  </div>
</div>
