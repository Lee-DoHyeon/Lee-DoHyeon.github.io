---
title: "Read"
layout: splash
permalink: /read/
author_profile: false
# header:
#   overlay_color: "#000"
#   overlay_filter: "0.5"
#   overlay_image: /assets/images/unsplash-image-1.jpg
#   actions:
#     - label: "Download"
#       url: "https://github.com/mmistakes/minimal-mistakes/"
#   caption: "Photo credit: [**Unsplash**](https://unsplash.com)"
# excerpt: "Bacon ipsum dolor sit amet salami ham hock ham, hamburger corned beef short ribs kielbasa biltong t-bone drumstick tri-tip tail sirloin pork chop."
intro:
  - excerpt: '"Thoughts become perception, perception becomes reality. Alter your thoughts, alter your reality."<br><span style="display: block; text-align: center;">Attributed to <em>William James</em></span>'
feature_row:
  - image_path: assets/images/Read/meditation.jpg
    alt: "Meditation"
    title: "Meditation"
    excerpt: "This section delves into various thoughts and deep reflections arising from daily life. It explores ideas, reflections, philosophical musings, future visions, and noted challenges."
    url: "read/meditation"
    btn_label: "Read More"
    btn_class: "btn--primary"
  - image_path: assets/images/Read/Motivation.jpg
    alt: "Motivation"
    title: "Motivation"
    excerpt: "This section captures insights and inspiration from various media experiences, such as books, papers, lectures, and arts. It aims to expand knowledge and ignite inspiration."
    url: "read/motivation"
    btn_label: "Read More"
    btn_class: "btn--primary"
  - image_path: assets/images/Read/Movement.jpg
    alt: "Movement"
    title: "Movement"
    excerpt: "This section showcases creative and practical activities, including short art production, volunteering, and more. It celebrates various creative endeavors and active pursuits."
    url: "read/movement"
    btn_label: "Read More"
    btn_class: "btn--primary"
---

<br>
<h1 id="page-title" class="page__title p-name" itemprop="headline">
  <a href="http://localhost:4000/read/" class="u-url" itemprop="url">Read</a>
</h1>
<br>
{% include feature_row id="intro" type="center" %}
{% include feature_row %}

<div class="recent-posts-container">
  <div class="recent-posts-column">
    {% include recent_posts_en.html %}
  </div>
  <div class="recent-posts-column">
    {% include recent_posts_kr.html %}
  </div>
</div>

<style>
.recent-posts-container {
  display: flex;
  justify-content: space-between;
}

.recent-posts-column {
  flex: 1;
  margin: 0 10px;
}

@media (max-width: 784px) {
  .recent-posts-container {
    display: block;
  }

  .recent-posts-column {
    margin: 0 0 20px 0;
  }
}
</style>
