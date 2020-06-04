---
layout: single
title: "Portfolio"
header:
    overlay_image: /assets/images/image_beach.jpeg
permalink: /portfolio/
author_profile: true
classes: wide

twitter-vote:
  - image_path: /assets/images/twitter-vote/logo.jpg
    alt: "Twitter vote"
    title: "Guess your vote using Twitter"
    excerpt: "Can I guess the party you will vote just knowing your last tweets?
	In this project I use Twitter API to extract tweets of open voters of different Spanish parties. Then applying different ML models, we try to guess the party you are going to vote based on the text content of your tweets (language/expressions/user_mentions)."
    url: /portfolio/twitter-vote/
    btn_label: "Article"
    btn_class: "btn--primary"
covid19:
  - image_path: /assets/images/logo-COVID19.png
    alt: "COVID19 Dashboard"
    title: "COVID19 Dashboard"
    excerpt: "A website displaying live COVID19 data in an interactive way,"
    url: https://dashboard-covid19data.herokuapp.com/
    btn_label: "Website"
    btn_class: "btn--primary"
understanding-tests:
  - image_path: /assets/images/understanding-tests.png
    alt: "Understanding tests"
    title: "Understanding Bayesian tests"
    excerpt: "Test fail. There are false positive and false negatives. So if I take a test and the result is positive, how confident can I be that I am infected? Can I trust that test?
	This is a tool that helps understand Bayesian tests, i.e. helps understand COVID19 tests or any othe test that replies with positive/negative output."
    url: https://dashboard-covid19data.herokuapp.com/understanding-tests
    btn_label: "Website"
    btn_class: "btn--primary"
sudoku:
  - image_path: /assets/images/sudoku.png
    alt: "Solve any sudoku"
    title: "Solve any sudoku"
    excerpt: "This is a sudoku game done in Python. The backend is able to solve any 9x9 sudoku. I created as well a GUI
	that generates random sudokus and give you hints on how to solve if you need help. "
    url: https://github.com/inimaz/Sudoku_solver
    btn_label: "Code"
    btn_class: "btn--primary"
vasco:
  - image_path: /assets/images/vasco.png
    alt: "VASCO"
    title: "The VASCO"
    excerpt: "The Vanishing & Appearing Sources during a Century of Observations (VASCO) project aims at finding astro-physically interesting mismatches between historical sky surveys: ‘Which object flickered out from our celestial radar?’, ‘Which locations hint at astronomical spectacles to discover?’. This is a collaborative international project in which we aim to compare images from different telescopes to find rare phenomena in the universe."
    url: https://vasconsite.wordpress.com/
    btn_label: "Main website"
    btn_class: "btn--primary"	
asbronomers:
  - image_path: /assets/images/asbronomers.png
    alt: "Asbronomers"
    title: "Asbronomers (blog)"
    excerpt: "Astronomy blog where we talk about the universe with a fun approach."
    url: http://asbronomers.com/	
    btn_label: "Website"
    btn_class: "btn--primary"
---

## Skills

**Tools**: Python, JAVA, Jupyter Notebook, SQL, Tableau, Git

**Libraries**: NumPy, Pandas, Scikit-learn, matplotlib, seaborn, nltk, BeautifulSoup, WEKA, tkinter


## Personal projects

Take a look to some of the projects I have been working on:
{% include feature_row id="twitter-vote" type="left" %}
{% include feature_row id="covid19" type="left" %}
{% include feature_row id="understanding-tests" type="left" %}
{% include feature_row id="sudoku" type="left" %}
See <i class="fab fa-fw fa-github"></i>[My Github profile](https://github.com/inimaz) to follow the latest projects I have been working on.

## Collaborations
{% include feature_row id="vasco" type="left" %}
{% include feature_row id="asbronomers" type="left" %}