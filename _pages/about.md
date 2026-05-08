---
layout: single
title: "Rachael Kee"
permalink: /
author_profile: true
classes: wide
redirect_from:
  - /about/
  - /about.html
---

{% include base_path %}
{% assign headshot = site.author.avatar | default: "profile.png" %}
{% assign recent_news = site.posts | where_exp: "post", "post.date <= site.time" %}

<style>
  .home-hero {
    display: grid;
    grid-template-columns: minmax(240px, 290px) 1fr;
    gap: clamp(1.5rem, 4vw, 3rem);
    align-items: center;
    margin: 0.5rem 0 2.25rem;
  }

  .home-portrait {
    margin: 0;
    padding: 0.85rem;
    border-radius: 1.75rem;
    background: linear-gradient(145deg, rgba(29, 78, 66, 0.16), rgba(15, 23, 42, 0.05));
    box-shadow: 0 20px 50px rgba(15, 23, 42, 0.12);
  }

  .home-portrait img {
    display: block;
    width: 100%;
    aspect-ratio: 1 / 1;
    object-fit: cover;
    border-radius: 1.25rem;
    background: #f3f4f6;
  }

  .home-kicker {
    margin: 0 0 0.75rem;
    font-size: 0.8rem;
    font-weight: 700;
    letter-spacing: 0.16em;
    text-transform: uppercase;
    color: #5f726a;
  }

  .home-lead {
    margin: 0;
    font-size: clamp(1.2rem, 2vw, 1.48rem);
    line-height: 1.7;
    color: #1f2937;
  }

  .home-actions {
    display: flex;
    flex-wrap: wrap;
    gap: 0.75rem;
    margin-top: 1.35rem;
  }

  .home-section {
    margin-top: 2.75rem;
  }

  .home-section__label {
    margin: 0 0 0.85rem;
    font-size: 0.78rem;
    font-weight: 700;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: #6b7280;
  }

  .home-links {
    display: grid;
    grid-template-columns: repeat(3, minmax(0, 1fr));
    gap: 1rem;
  }

  .home-link {
    display: block;
    padding: 1.05rem 1.1rem;
    border: 1px solid rgba(148, 163, 184, 0.28);
    border-radius: 1rem;
    background: linear-gradient(180deg, #ffffff 0%, #fbfcfd 100%);
    color: inherit;
    text-decoration: none;
    box-shadow: 0 12px 28px rgba(15, 23, 42, 0.05);
    transition: transform 140ms ease, box-shadow 140ms ease, border-color 140ms ease;
  }

  .home-link:hover {
    transform: translateY(-2px);
    border-color: rgba(32, 93, 79, 0.28);
    box-shadow: 0 16px 32px rgba(15, 23, 42, 0.08);
  }

  .home-link h3 {
    margin: 0 0 0.3rem;
    font-size: 1.02rem;
  }

  .home-link p {
    margin: 0;
    color: #4b5563;
    font-size: 0.95rem;
    line-height: 1.55;
  }

  .home-news {
    display: grid;
    gap: 1rem;
  }

  .home-news__item {
    padding: 1rem 1.1rem;
    border-left: 3px solid #1f6f5b;
    border-radius: 0.85rem;
    background: #fafafa;
  }

  .home-news__meta {
    margin: 0 0 0.4rem;
    font-size: 0.9rem;
    color: #6b7280;
  }

  .home-news__item h3 {
    margin: 0;
    font-size: 1.05rem;
  }

  .home-news__item p {
    margin: 0.5rem 0 0;
    color: #374151;
    line-height: 1.6;
  }

  .home-news__more {
    margin-top: 0.9rem;
  }

  @media (max-width: 900px) {
    .home-hero {
      grid-template-columns: 1fr;
    }

    .home-links {
      grid-template-columns: 1fr 1fr;
    }
  }

  @media (max-width: 640px) {
    .home-links {
      grid-template-columns: 1fr;
    }
  }
</style>

<div class="home-hero">
  <figure class="home-portrait">
    <img src="{{ headshot | prepend: '/images/' | prepend: base_path }}" alt="Portrait of Rachael Kee" />
  </figure>

  <div class="home-hero__copy">
    <p class="home-kicker">PhD Candidate in Communication · UC Davis</p>
    <p class="home-lead">Rachael Kee studies neurobiological explanations of human communication, with a particular interest in sleep neuroscience, media effects, and computational approaches to social science.</p>
    <div class="home-actions">
      <a class="btn" href="{{ base_path }}/research/">Research</a>
      <a class="btn" href="{{ base_path }}/publications/">Publications</a>
      <a class="btn" href="{{ base_path }}/cv/">CV</a>
      <a class="btn btn--inverse" href="mailto:rlkee@ucdavis.edu">Contact</a>
    </div>
  </div>
</div>

<section class="home-section">
  <p class="home-section__label">Explore</p>
  <div class="home-links">
    <a class="home-link" href="{{ base_path }}/research/">
      <h3>Research</h3>
      <p>Research questions, methods, and the themes that connect sleep, media, and communication.</p>
    </a>
    <a class="home-link" href="{{ base_path }}/publications/">
      <h3>Publications</h3>
      <p>Current journal articles and conference papers, organized by collection.</p>
    </a>
    <a class="home-link" href="{{ base_path }}/cv/">
      <h3>CV</h3>
      <p>A compact overview of training, experience, and academic service.</p>
    </a>
    <a class="home-link" href="{{ base_path }}/talks/">
      <h3>Talks</h3>
      <p>Invited talks, conference presentations, and related scholarly events.</p>
    </a>
    <a class="home-link" href="{{ base_path }}/teaching/">
      <h3>Teaching</h3>
      <p>Courses, instruction, and mentoring experience.</p>
    </a>
    <a class="home-link" href="{{ base_path }}/year-archive/">
      <h3>News</h3>
      <p>Recent updates, conference activity, and research milestones.</p>
    </a>
  </div>
</section>

<section class="home-section">
  <p class="home-section__label">Recent News</p>
  <div class="home-news">
    {% if recent_news.size > 0 %}
      {% for post in recent_news limit: 3 %}
        <article class="home-news__item">
          <p class="home-news__meta">{{ post.date | date: "%B %Y" }}</p>
          <h3><a href="{{ base_path }}{{ post.url }}">{{ post.title }}</a></h3>
          {% if post.excerpt %}
            <p>{{ post.excerpt | strip_html | truncate: 180 }}</p>
          {% endif %}
        </article>
      {% endfor %}
      <p class="home-news__more"><a href="{{ base_path }}/year-archive/">View all news</a></p>
    {% else %}
      <p>No news items have been published yet.</p>
    {% endif %}
  </div>
</section>
