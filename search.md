---
layout: page
title: Search
permalink: /search/
---

<input type="search" id="q" placeholder="Search posts…" autofocus
       style="width:100%;padding:.5em;font-size:1em;box-sizing:border-box">
<ul id="results" class="post-list"></ul>

<script>
(function () {
  var q = document.getElementById('q'),
      out = document.getElementById('results'),
      data = [];
  fetch('{{ "/search.json" | relative_url }}')
    .then(function (r) { return r.json(); })
    .then(function (d) { data = d; });
  q.addEventListener('input', function () {
    var t = q.value.trim().toLowerCase();
    out.innerHTML = '';
    if (!t) return;
    data.filter(function (p) {
      return (p.title + ' ' + p.content + ' ' + (p.categories || []).join(' '))
             .toLowerCase().indexOf(t) > -1;
    }).slice(0, 50).forEach(function (p) {
      var li = document.createElement('li');
      li.innerHTML = '<a href="' + p.url + '">' + p.title + '</a> — <small>' + p.date + '</small>';
      out.appendChild(li);
    });
  });
})();
</script>
