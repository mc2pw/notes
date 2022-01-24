---
title: Publishing a blog with pandoc
date: 2022-01-24T00:44:03.188Z
abstract: "This is the first post of this minimalist blog I created using [pandoc-blog](https://github.com/lukasschwab/pandoc-blog)."
versions: "https://github.com/mc2pw/notes/blob/master/misc/pandoc-based-blog.md"
permalink: "https://e.mc2.pw/p/pandoc-based-blog.html"
tags: ["pandoc"]
---
<!-- Other possible metadata for organizing can be index_permalink, prev_permalink, next_permalink and the corresponding index-versions, prev_versions, next_versions. Also include updated (timestamp), when it applies. -->

I've been intending for some time to have a blog where I collect my notes and thoughts on topics of my interest. Some time ago I tried Hugo, which is a static blog generator. This site is a static blog (at the time of publishing, it's hosted on Netlify). However, I found Hugo too complicated and distracting for my purposes, so I opted for using pandoc, a versatile tool that converts Markdown to HTML. This way I can host all my posts at separate repositories (such as [git repository](https://github.com/mc2pw/notes)) and show the history of changes. [pandoc-blog](https://github.com/lukasschwab/pandoc-blog) is a small repository that is ready out of the box for the task of converting my Markdown files into the files served by this site. So far I've done these changes to the pandoc-blog repository, which I've committed to [my fork](https://github.com/lukasschwab/mc2pw):

- Create an index.yaml file and pass it as the `--metadata-file` option to pandoc when using the templates/index.html template
- Set the MathJax script url as the `--mathjax` option.
- Display the `versions` link (a link to the repository file of the post) when provided in the metadata block.
- Add more margin at the bottom of the page, etc.

After having customized templates/index.html and index.yaml, I only have to copy a Markdown file from a repository to the posts directory (and images to the img directory) each time I'm ready for publishing a new post.

This is some Python code.

```python
print("Hola Mundo!")
```

This is Euler's identity.

$$ e^{i\pi} + 1 = 0 $$

This is the associativity of a monad.

$$\require{AMScd}
\begin{CD}
TTT @>{\mu T}>> TT\\
@V{T\mu}VV @V{\mu}VV \\
TT @>{\mu}>> T
\end{CD}$$
<!-- For more mathjax see math.stackexchange etc. -->

This is an image of _Cyperus Rotundus_.

![Cyperus Rotundus](../img/misc/cyperus-rotundus.jpg)

That's it, no configuration, no special commands, ready to render code, math and images.
