---
layout: single
title: "Books"
permalink: /books/
author_profile: true
---

<style>
  .books-intro { font-size: 1.15rem !important; line-height: 1.75 !important; color: #1d1d1f !important;
                 max-width: 560px; margin: 0 0 44px !important; text-align: left !important; }

  .bgrid { display: grid; grid-template-columns: repeat(3, 1fr);
           gap: 36px 24px; margin: 0 0 56px; }

  @media (max-width: 900px) {
    .bgrid { grid-template-columns: repeat(2, 1fr); }
  }

  .book { display: flex; flex-direction: column; }
  .book .cover { width: 100%; aspect-ratio: 2 / 3; border-radius: 4px; display: block; object-fit: cover;
                 box-shadow: 0 3px 14px rgba(0,0,0,.16);
                 transition: transform .25s ease, box-shadow .25s ease; }
  .book:hover .cover { transform: translateY(-4px); box-shadow: 0 8px 22px rgba(0,0,0,.22); }

  .book .ph { position: relative; width: 100%; aspect-ratio: 2 / 3; border-radius: 4px;
              box-shadow: 0 3px 14px rgba(0,0,0,.16);
              display: flex; flex-direction: column; align-items: center; justify-content: center;
              padding: 22px; text-align: center; color: #fff;
              background: linear-gradient(155deg, #4a5d4e, #2f3d33);
              transition: transform .25s ease, box-shadow .25s ease; }
  .book .ph::after { content: ""; position: absolute; inset: 10px; border: 1px solid rgba(255,255,255,.35);
                     border-radius: 2px; pointer-events: none; }
  .book .ph-title { font-family: Georgia, 'Times New Roman', serif; font-size: .98rem; font-weight: 600;
                    line-height: 1.3; letter-spacing: .01em; }
  .book .ph-rule { width: 28px; height: 1px; background: rgba(255,255,255,.5); margin: 12px 0 10px; }
  .book .ph-author { font-size: .68rem; font-weight: 500; text-transform: uppercase;
                     letter-spacing: .1em; opacity: .85; }
  .book .ph-1 { background: linear-gradient(155deg, #7c4258, #55293c); }
  .book .ph-2 { background: linear-gradient(155deg, #4d5d70, #333f4e); }
  .book .ph-3 { background: linear-gradient(155deg, #8a6a3b, #62492a); }
  .book .ph-4 { background: linear-gradient(155deg, #6d5a66, #4a3c47); }
  .book:hover .ph { transform: translateY(-4px); box-shadow: 0 8px 22px rgba(0,0,0,.22); }

  .book .t { margin: 16px 0 0 !important; font-size: .98rem !important; font-weight: 500;
             color: #1d1d1f !important; line-height: 1.35 !important; text-align: left !important; }
  .book .a { margin: 3px 0 0 !important; font-size: .84rem !important; color: #6e6e73 !important;
             text-align: left !important; }
  .book .n { margin: 10px 0 0 !important; font-size: .92rem !important; line-height: 1.6 !important;
             color: #33333a !important; text-align: left !important; }
  .book .more { margin-top: auto; padding-top: 10px; font-size: .83rem; color: #8a3d5f; text-decoration: none;
                align-self: flex-start; border-bottom: 1px solid transparent; }
  .book .more:hover { border-bottom-color: #8a3d5f; }

  .books-foot { margin-top: 16px !important; padding-top: 24px; border-top: 1px solid #e3e0d4;
                font-size: .86rem !important; color: #6e6e73 !important; }
  .books-foot a { color: #8a3d5f; text-decoration: none; }

  @media (max-width: 560px) {
    .bgrid { grid-template-columns: repeat(2, 1fr); gap: 32px 20px; }
  }
</style>

<p class="books-intro"> I love reading. These are some of the books that I still think about and would read again. </p>

<div class="bgrid">
{% for b in site.data.books %}
  <div class="book">
    {% assign phn = forloop.index0 | modulo: 5 %}

    {% if b.isbn != blank %}
      <img class="cover"
        src="https://books.google.com/books/content?vid=ISBN{{ b.isbn }}&printsec=frontcover&img=1&zoom=1"
        alt="{{ b.title }} cover" loading="lazy"
        onerror="if(!this.dataset.alt){this.dataset.alt=1;this.src='https://covers.openlibrary.org/b/isbn/{{ b.isbn }}-M.jpg?default=false';}else{this.style.display='none';this.nextElementSibling.style.display='flex';}">
      <div class="ph ph-{{ phn }}" style="display:none">
        <span class="ph-title">{{ b.title }}</span>
        <span class="ph-rule"></span>
        <span class="ph-author">{{ b.author }}</span>
      </div>
    {% elsif b.cover != blank %}
      <img class="cover" src="{{ b.cover }}" alt="{{ b.title }} cover" loading="lazy"
           onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
      <div class="ph ph-{{ phn }}" style="display:none">
        <span class="ph-title">{{ b.title }}</span>
        <span class="ph-rule"></span>
        <span class="ph-author">{{ b.author }}</span>
      </div>
    {% else %}
      <div class="ph ph-{{ phn }}">
        <span class="ph-title">{{ b.title }}</span>
        <span class="ph-rule"></span>
        <span class="ph-author">{{ b.author }}</span>
      </div>
    {% endif %}
    
    <p class="t">{{ b.title }}</p>
    <p class="a">{{ b.author }}</p>
    <p class="n">{{ b.note }}</p>
    
    {% if b.full != blank %}
      {% assign review = site.books | where: "slug", b.full | first %}
      {% if review %}<a class="more" href="{{ review.url }}">Full review →</a>{% endif %}
    {% endif %}

  </div>
{% endfor %}
</div>

<p class="books-foot">The full list, including everything I did not write about, lives on <a href="https://www.goodreads.com/user/show/14112847-pallavi">Goodreads</a>.</p>