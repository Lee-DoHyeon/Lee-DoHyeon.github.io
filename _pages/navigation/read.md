---
title: "Read"
layout: single
permalink: /read/
date: 2016-03-23T11:48:41-04:00
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
  - excerpt: 'Nullam suscipit et nam, tellus velit pellentesque at malesuada, enim eaque. Quis nulla, netus tempor in diam gravida tincidunt, *proin faucibus* voluptate felis id sollicitudin. Centered with `type="center"`'
feature_row:
  - image_path: assets/images/unsplash-gallery-image-1-th.jpg
    alt: "Meditation"
    title: "Meditation"
    excerpt: "Ideas, Insights, Essays, and Beliefs"
    url: "meditation"
    btn_label: "Read More"
    btn_class: "btn--primary"
  - image_path: /assets/images/unsplash-gallery-image-2-th.jpg
    alt: "Motivation"
    title: "Motivation"
    excerpt: "Books, Movies, Papers, and Exhibitions"
    url: "motivation"
    btn_label: "Read More"
    btn_class: "btn--primary"
  - image_path: /assets/images/unsplash-gallery-image-2-th.jpg
    alt: "Movement"
    title: "Movement"
    excerpt: "Creativity, Production, Writing, and Movement"
    url: "movement"
    btn_label: "Read More"
    btn_class: "btn--primary"
---

{% include feature_row id="intro" type="center" %}

{% include feature_row %}

{% include recent_posts.html %}
