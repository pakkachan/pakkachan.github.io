---
layout: post
title: "Solving Jane Street's \"Can you reverse engineer an ASIC\" puzzle"
permalink: /asic/
excerpt: "Reverse engineering the Jane Street ASIC puzzle from the GDS up."
---

{% comment %}
  The body lives in the puzzle repo and is symlinked in:

    _includes/asic_summary.md -> asic-puzzle-2026/summary/final_summary.md
    asic/images               -> asic-puzzle-2026/summary/images

  The permalink is /asic/, so the image paths in that file (images/1_anatomy.png)
  resolve against asic/images/ without the source file needing to know about the
  site. Its first line is the top-level "# ..." heading, which is dropped here
  because the post layout already prints page.title. We strip the first line
  rather than match its exact text, so retitling the source cannot bring the
  duplicate heading back.
{% endcomment %}

{% assign nl = '
' %}
{% capture body %}{% include asic_summary.md %}{% endcapture %}
{% comment %}
  Append a build-stamp query to every .png link so a regenerated figure is never
  served from browser cache. The URL changes each build, forcing a refetch.
{% endcomment %}
{% capture png_stamp %}.png?v={{ site.time | date: '%s' }}){% endcapture %}
{{ body | split: nl | slice: 1, 100000 | join: nl | replace: '.png)', png_stamp }}
