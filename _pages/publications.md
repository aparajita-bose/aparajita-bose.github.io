---
layout: page
permalink: /publications/
title: Publications
# description: Publications by categories in reversed chronological order.
nav: true
nav_order: 2
---

<!-- _pages/publications.md -->

<!-- Bibsearch Feature -->

{% include bib_search.liquid %}

<div class="publications">

<h3 style="margin-top: 2em;">Publications In-Progress</h3>

{% bibliography --query @*[inprogress=true]* %}

<h3 style="margin-top: 2em;">Published Publications</h3>

{% bibliography --query @*[selected=true]* %}

</div>
