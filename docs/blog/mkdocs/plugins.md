---
title: mkdocs plugins
description: Mkdocs plugins and extensions that i used
date: "2022-04-18"
banner: ../images/mkdocs.png
tags:
    - mkdocs
    - plugins
    - extensions
---
# mkdocs-material
Speak for itself
[Getting started](https://squidfunk.github.io/mkdocs-material/getting-started/)

---

# MkDocs Awesome Pages
The [awesome-pages](https://github.com/lukasgeiter/mkdocs-awesome-pages-plugin) plugin allows you to customize how your pages show up the navigation of your MkDocs without having to configure the full structure in your mkdocs.yml  
For more [info](https://github.com/lukasgeiter/mkdocs-awesome-pages-plugin)

```title="install"
pip install mkdocs-awesome-pages-plugin
```

```title="yml config"
plugins:
    - awesome-pages
```

### Usage
Create `.pages` file in subdirectory to order

```
nav:
    - subdirectory
    - page1.md
    - page2.md
```

!!! Note 
    More examples in project README

---

# mkdocs-jupyter
Use Jupyter Notebooks in mkdocs  
[github](https://github.com/danielfrg/mkdocs-jupyter)

![](images/mkdocs-jupyter.png)

```title="install"
pip install mkdocs-jupyter
```

### Usage

```yml title="mkdocs.yml"
plugins:
  - mkdocs-jupyter
```

- The first h1 header (#) in your notebook will be used as the title.

---

# Video

This plugin allows you to embed videos on the documentation pages using a simple Markdown syntax. [github](https://github.com/soulless-viewer/mkdocs-video)

```bash title="install"
pip install mkdocs-video
```

### config
```yml title="mkdocs.yml"
plugins:
  - mkdocs-video
```

### usage

```
![type:video](https://www.youtube.com/embed/LXb3EKWsInQ)
```