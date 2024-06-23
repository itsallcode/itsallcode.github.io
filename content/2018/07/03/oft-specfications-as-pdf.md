---
title: "Oft Specfications as Pdf"
date: 2018-07-03T19:46:42+02:00
draft: true
params:
    author: Sebastian
---

[PDFs](https://www.techterms.com/definition/pdf) are a fixed-size document format, which means that they made more sense in the days when PCs all had about the same video resolutions and screen geometries. But even then, they were never perfect for displaying them on a screen because most are in portrait mode and monitors rarely were. Nowadays, displays especially in mobile devices come in all shapes and sizes, so fixed-size formats are even more obsolete.

What PDFs excel at to the present day is a universal document exchange format for read-only documents — especially if you plan on printing them.

While specifications seldom get printed these days, they still tend to get archived — especially [PDF-A](https://en.wikipedia.org/wiki/PDF/A) — and a universally accepted format helps. That being said, we plan to make converting [OFT-native](https://medium.com/@williamwilling/oft-planning-made-leaner-5fc52e2e77f9) (aka. "requirement-enhanced Markdown") easy.

**The requirements are:**
- Creates PDFs
- Is platform-independent
- Separates content from layout
- Customizable style (so that projects or companies can apply their corporate design)
- Based on free software

While there is nothing wrong with users replacing parts of the tool chain with proprietary choices, our reference implementation is going to be free-software only.

**These are the options we are discussing so far:**
1. **HTML + CSS + [HTML2PDF](https://github.com/spipu/html2pdf) Renderer**

This is a variant where we let a Markdown renderer create HTML for us and use printer-centric CSS as style and layout customization method. The benefits are that you have a broad base of developers these days who know how to tweak CSS, so it is easy for them to tweak the CSS stylesheet however they need. The downside is that the quality depends mostly on how good the PDF converter is.

2. **[LaTex](https://www.latex-project.org/) 2 PDF**

LaTex makes absolutely beautiful and professional documents. There is no doubt about that. The ability to customize via macros is only limited by the user’s imagination.

On the other hand, outside of the academic world, there are not so many people who have previous experience with LaTeX. Also, there are a lot of dependencies involved and they differ depending on the platform.

3. **[DocBook](https://en.wikipedia.org/wiki/DocBook)**

DocBook shares the basic concept of separation of content and style with TeX. DocBook layouts are customizable through [XSLT stylesheets](https://en.wikipedia.org/wiki/XSLT). The DocBook documents are XML files that have a strictly defined schema, so the content structure is not customizable like in TeX. Depending on your perspective, this is either a weakness or a strength (since it enforces a uniform document format).

DocBook is also known for producing quality PDFs. And the dependencies should be pretty homogeneous between platforms.

**Popularity Contest**

I tried to find numbers about the popularity of LaTeX vs. DocBook. Since none popped up right away, I went for a different approach: comparing search term popularity on [Google Trends](https://trends.google.com/trends/explore?q=DocBook,%2Fm%2F04mdr).

I know that the results need to be treated with a healthy dose of skepticism, since more searches could simply mean one of the two is harder to use. Also, while there is only one DocBook, there are a whole bunch of TeX variants out there.

If the search term popularity is any indication, LaTeX wins this contest with flying colors.

**What’s your opinion? Any arguments I missed?**