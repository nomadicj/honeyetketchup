---
layout: default
title: Tous les articles
permalink: /blog/
---

<div class="container py-5">
  <div class="row justify-content-center">
    <div class="col-lg-10">
      <header class="mb-5 text-center">
        <h1 class="display-4 fw-bold mb-3">{{ site.t.fr.blog.title }}</h1>
        <p class="lead text-muted">{{ site.t.fr.blog.subtitle }}</p>
      </header>

      <div class="row">
        <div class="col-lg-8">
          {% for post in site.posts %}
          <article class="card border-0 shadow-sm mb-4 fadeIn hover-shadow article-card">
            <div class="card-body p-4">
              <div class="d-flex align-items-center mb-3">
                <div class="rounded-circle bg-light d-flex align-items-center justify-content-center me-3" style="width: 45px; height: 45px;">
                  <i class="bi bi-calendar3 text-primary"></i>
                </div>
                <span class="text-muted">{{ post.date | date: "%-d %B %Y" }}</span>
              </div>
              
              <h2 class="card-title h4 fw-bold mb-3">
                <a href="{{ post.url | relative_url }}" class="text-decoration-none stretched-link text-dark">
                  {{ post.title | escape }}
                </a>
              </h2>
              
              <div class="mb-3">
                {% for category in post.categories %}
                <span class="badge bg-light text-dark me-2 mb-2">{{ category }}</span>
                {% endfor %}
              </div>
              
              <div class="card-text mb-3">
                {{ post.excerpt | strip_html | truncatewords: 30 }}
              </div>
              
              <div class="text-end">
                <a href="{{ post.url | relative_url }}" class="btn btn-sm btn-outline-primary">
                  {{ site.t.fr.blog.continue_reading }} <i class="bi bi-arrow-right ms-1"></i>
                </a>
              </div>
            </div>
          </article>
          {% endfor %}
        </div>
        
        <div class="col-lg-4">
          <div class="position-sticky" style="top: 2rem;">
            <div class="card border-0 shadow-sm mb-4">
              <div class="card-header bg-primary text-white py-3">
                <h5 class="card-title m-0">
                  <i class="bi bi-book me-2"></i> {{ site.t.fr.blog.about_book }}
                </h5>
              </div>
              <div class="card-body">
                <img src="/images/book-cover.jpg" alt="Honey et Ketchup couverture" class="img-fluid rounded shadow-sm mb-3">
                <h6 class="fw-bold">Honey et Ketchup</h6>
                <p class="small text-muted mb-3">Par {{ site.book.authors | join: " & " }}</p>
                <p class="small">{{ site.t.fr.blog.book_summary }}</p>
                <a href="{{ site.baseurl }}/" class="btn btn-outline-primary btn-sm d-block">{{ site.t.fr.home.read_review }}</a>
              </div>
            </div>
            
            <div class="card border-0 shadow-sm mb-4">
              <div class="card-header bg-light py-3">
                <h5 class="card-title m-0">
                  <i class="bi bi-tags me-2"></i> {{ site.t.fr.blog.categories }}
                </h5>
              </div>
              <div class="card-body">
                <div class="d-flex flex-wrap gap-2">
                  {% assign categories = site.posts | map: "categories" | flatten | uniq %}
                  {% for category in categories %}
                  <a href="#" class="badge bg-light text-dark text-decoration-none p-2">{{ category }}</a>
                  {% endfor %}
                </div>
              </div>
            </div>
            
            <div class="card border-0 shadow-sm">
              <div class="card-header bg-light py-3">
                <h5 class="card-title m-0">
                  <i class="bi bi-lightbulb me-2"></i> {{ site.t.fr.blog.resources }}
                </h5>
              </div>
              <div class="card-body">
                <ul class="list-unstyled mb-0">
                  <li class="mb-2">
                    <a href="{{ site.baseurl }}/resources/#activities" class="text-decoration-none d-flex align-items-center">
                      <i class="bi bi-star me-2 text-warning"></i>
                      <span>{{ site.t.fr.blog.classroom_activities }}</span>
                    </a>
                  </li>
                  <li class="mb-2">
                    <a href="{{ site.baseurl }}/resources/#discussion" class="text-decoration-none d-flex align-items-center">
                      <i class="bi bi-chat-dots me-2 text-primary"></i>
                      <span>{{ site.t.fr.blog.discussion_questions }}</span>
                    </a>
                  </li>
                  <li>
                    <a href="{{ site.baseurl }}/resources/#similar-books" class="text-decoration-none d-flex align-items-center">
                      <i class="bi bi-collection me-2 text-success"></i>
                      <span>{{ site.t.fr.blog.similar_books }}</span>
                    </a>
                  </li>
                </ul>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>

<style>
  .hover-shadow {
    transition: transform 0.2s ease, box-shadow 0.2s ease;
  }
  
  .hover-shadow:hover {
    transform: translateY(-5px);
    box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1) !important;
  }
  
  .fadeIn {
    animation: fadeIn 0.5s ease-in;
  }
  
  @keyframes fadeIn {
    0% { opacity: 0; transform: translateY(10px); }
    100% { opacity: 1; transform: translateY(0); }
  }
  
  .article-card {
    transition: all 0.3s ease;
  }
  
  .article-card:hover {
    border-left: 4px solid #0d6efd !important;
  }
</style>