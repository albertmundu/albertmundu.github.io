---
layout: page
permalink: /publications/
title: publications
description: publications by categories in reversed chronological order.
nav: true
nav_order: 1
---

<!-- _pages/publications.md -->

<!-- Bibsearch Feature -->

{% include bib_search.liquid %}

<div class="pub-view-toggle d-flex justify-content-end mb-2">
  <button id="btn-card-view" class="btn btn-sm pub-view-btn active" onclick="setPubView('card')" title="Card view">
    <i class="ti ti-layout-grid"></i>
  </button>
  <button id="btn-list-view" class="btn btn-sm pub-view-btn" onclick="setPubView('list')" title="List view">
    <i class="ti ti-list"></i>
  </button>
</div>

<div class="publications">

{% bibliography %}

</div>

<script>
  function setPubView(view) {
    var pubs = document.querySelector('.publications');
    var cardBtn = document.getElementById('btn-card-view');
    var listBtn = document.getElementById('btn-list-view');
    if (view === 'list') {
      pubs.classList.add('list-view');
      listBtn.classList.add('active');
      cardBtn.classList.remove('active');
    } else {
      pubs.classList.remove('list-view');
      cardBtn.classList.add('active');
      listBtn.classList.remove('active');
    }
    localStorage.setItem('pub-view', view);
  }
  document.addEventListener('DOMContentLoaded', function () {
    if (localStorage.getItem('pub-view') === 'list') setPubView('list');
  });
</script>
