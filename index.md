title: VueJS
class: animation-fade
layout: true

<!-- This slide will serve as the base layout for all your slides -->
.bottom-bar[
  {{title}}
]

---

class: impact

# {{title}}
## Vuejs presentation

---

# What is Vue?

> Pronounced /vjuː/ (like view) is a progressive javascript framework for building user interfaces.

## Strong points

- Focus (build user interfaces)
- Simplicity (syntax is simple and easy to follow)
- Compactness (25kb more or less, no 1 million dependencies)
- Speed (Angular, react, metheor...)
- Versatility (works well for small and sophisticated apps)

---

# Basics

- Virtual DOM
> Working with a copy of DOM and update differences in real DOM
- Reactive: data changes => DOM changes
- A Vue instance/component works like a (view)model. Populating and mutating its own data
> Isolated components in .vue files
- Easy to install
> vue-cli manager
- Detailed, clean and understandable docs

---

# Vue Instance

- An application is started with one Vue Instance

--

.col-5.center[
**javascript**

``` javascript
new Vue({
  el: '#app',
  data() {
    return {
      greeting: 'Hello all!',
    };
  },
});
```
]

--

.col-5.col-offset-1[
**HTML**

``` html
<div id="app">
  <h1>{{ greeting }}</h1>
</div>
```
]

--
 
.col-6.col-offset-1[
**Result**
 
``` html
<div id="app">
  <h1>Hello all!</h1>
</div>
```
]

---

...

---

# The basics

## Getting started

Use [Markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) to write your slides. Don't be afraid, it's really easy!

--

## Making points

Look how you can make *some* points:
--

- Create slides with your **favorite text editor**
--

- Focus on your **content**, not the tool
--

- You can finally be **productive**!

---

# There's more

## Syntax highlighting

You can also add `code` to your slides:
```html
<div class="impact">Some HTML code</div>
```

## CSS classes

You can use .alt[shortcut] syntax to apply .big[some style!]

...or just <span class="alt">HTML</span> if you prefer.

---

# And more...

## 12-column grid layout

Use to the included **grid layout** classes to split content easily:
.col-6[
  ### Left column

  - I'm on the left
  - It's neat!
]
.col-6[
  ### Right column

  - I'm on the right
  - I love it!
]

## Learn the tricks

See the [wiki](https://github.com/gnab/remark/wiki) to learn more of what you can do with .alt[Remark.js]
