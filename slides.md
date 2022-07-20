---
# try also 'default' to start simple
theme: default
# random image from a curated Unsplash collection by Anthony
background: https://images.unsplash.com/photo-1555109307-f7d9da25c244
# apply any windi css classes to the current slide
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: true
# some information about the slides, markdown enabled
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# persist drawings in exports and build
drawings:
  persist: false
---

# Docker and GitHub Actions

Camila Pozas - TechOps

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="abs-br m-6 flex gap-2">
  <a href="https://github.com/camipozas/docker-gh-actions" title="Open in Editor" class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <carbon:edit />
  </a>
  <a href="https://github.com/camipozas" target="_blank" alt="GitHub"
    class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>


---
src: ./slides/2-what-is-docker.md
---

---

---
src: ./slides/3-creating-container.md
---

---
src: ./slides/4-how-to-make-dockerfile.md
---

---
src: ./slides/5-docker-main-commands.md
---

---
src: ./slides/6-basic-example-docker.md
---

---
src:./slides/7-another-example-docker.md
---

---
src: ./slides/8-key-terms-docker-commands.md
---

---
src: ./slides/9-docker-commands.md
---

---
src: ./slides/10-github-actions.md
---

---
src: ./slides/11-how-it-works.md
---

---
src: ./slides/12-understanding-workflow.md
---

---
src: ./slides/13-why-is-it-useful.md
---

---
src: ./slides/14-learn-more.md
---