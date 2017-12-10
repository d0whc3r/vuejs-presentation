title: VueJS presentation
class: animation-fade
layout: true

<!-- This slide will serve as the base layout for all your slides -->
.bottom-bar[
  {{title}}
]

---

class: impact

# {{title}}
## VueJS, Javascript framework

---

# What is Vue?

> Pronounced /vjuː/ (like view) is a progressive javascript framework for building user interfaces.

## Strong points

- Focus (build user interfaces)
- Simplicity (syntax is simple and easy to follow)
- Compactness (25kb more or less, no 1 million dependencies)
- Speed (Angular, react, meteor...)
- Versatility (works well for small and sophisticated apps)

---

# Basics

- Virtual DOM
> Working with a copy of DOM and update differences in real DOM
- Reactive: data changes => DOM changes
- A Vue instance/component works like a (view)model. Populating and mutating its own data
> Isolated components in .vue files
- Easy to install
> Project template vue-cli manager
- Detailed, clean and understandable docs

---

# Basics - Properties and Methods

- `data`: Object with stored properties that become reactive
- `computed`: Object with computed properties and use like data properties
- `methods`: Object with stored functions to use

> All properties and methods could be used in component/instance or in its html template

Vue proxies all properties in *data*, *computed*, and *methods* to __root__ object

---

# Basics - Vue Instance

- An application is started with one Vue Instance

![](./images/simple-instance1.png)

---

# Basics - Vue Instance

- An application is started with one Vue Instance

![](./images/simple-instance2.png)

---

# Basics - Lifecycles

.col-2[
![small](./images/lifecycle.png)
]

.col-10.text-small[
- `beforeCreate`: First event, before element added to DOM (also run in server-side rendering); **data** has not been made reactive and **events** have not been set up yet
- `created`: Can access reactive **data** and **events** are active. Templates and virtual DOM have not yet been mounted or rendered
- `beforeMount`: Runs before the initial render (it doesn't get called when doing server-side rendering)
- `mounted`: After element rendered, it will have full access to the reactive component and templates
- `beforeUpdate`: Before data changes and the update cycle begins, before DOM is patched and re-rendered
- `updated`: After data changes on your component and the DOM re-renders
- `beforeDestroy`: Before component teardown. Component will still be fully present and functional
- `destroyed`: Nothing left on the component. Everything that was attached to it has been destroyed
]

---

# Basics - Interpolations

## Text

Most common and basic data binding with "Mustaches" syntax

``` html
<span>Message: {{ msg }}</span>
```

---

# Basics - Interpolations

## Attributes

"Mustaches" **cannot** be used inside HTML attributes. Instead, use a v-bind directive:

``` html
<div v-bind:id="dynamicId"></div>
```

In case of boolean attributes:

``` html
<button v-bind:disabled="isButtonDisabled">Button</button>
```

If `isButtonDisabled` has the value of `null`, `undefined`, or `false`, the disabled attribute will not even be included in the render

---

# Basics - Interpolations

## Using JavaScript Expressions

Vue.js actually supports the full power of JavaScript expressions inside all data bindings:

``` html
{{ ok ? 'YES' : 'NO' }}

{{ message.split('').reverse().join('') }}

<div v-bind:id="'list-' + id"></div>
```

Each binding can only contain **one single expression**, so the following will **NOT** work:

``` html
{{ var a = 1 }}

{{ if (ok) { return message } }}
```

---

# Basics - Directives

- Directives are special attributes with the `v-` prefix.
- Directive attribute values are expected to be a **single JavaScript expression**

``` html
<p v-if="seen">Now you see me</p>
<p v-else>Nothing to see</p>
```

- Some vue directives

```
v-for, v-if, v-else-if, v-else, v-show, v-text, v-bind, v-on...
```

- Can create custom directives

---

# Basics - Directives

## Arguments

Some directives can take an "argument", denoted by a colon after the directive name.

``` html
<a v-bind:href="url"> ... </a>
<a v-on:click="doSomething"> ... </a>
```

---

# Basics - Directives

## Modifiers

Modifiers are special postfixes denoted by a dot, which indicate that a directive should be bound in some special way.

``` html
<form v-on:submit.prevent="onSubmit"> ... </form>
```

---

# Basics - Directives

## Shorthands

ue.js provides special shorthands for two of the most often used directives, `v-bind` and `v-on`:

``` html
<!-- full syntax -->
<a v-bind:href="url"> ... </a>
<a v-on:click="doSomething"> ... </a>

<!-- shorthand -->
<a :href="url"> ... </a>
<a @click="doSomething"> ... </a>
```

---

# Methods, Computed and Watchers

## Methods

![large](./images/methods1.png)


---

# Methods, Computed and Watchers

## Methods

![large](./images/methods2.png)


---

# Methods, Computed and Watchers

## Computed properties

.col-6[
![big](./images/computedprops1.png)
]

---

# Methods, Computed and Watchers

## Computed properties

.col-6[
![big](./images/computedprops2.png)
]

.col-6[
We could use a javascript inline expresion like: `message.split('').reverse().join('')` or the **method** described before; the difference is that **computed properties are cached based on their dependencies**.

A computed property will only re-evaluate when some of its dependencies have changed. This means as long as `message` has not changed, multiple access to the `reversedMessage` **computed property** will immediately return the previously computed result **without having to run the function again**.
]

---

# Methods, Computed and Watchers

## Watched property

Vue does provide a more generic way to observe and react to data changes on a Vue instance

![big](./images/watched1.png)

---

# Methods, Computed and Watchers

## Watched property

Vue does provide a more generic way to observe and react to data changes on a Vue instance

![big](./images/watched2.png)

---

# Methods, Computed and Watchers

## Watched property

Last example could be done in less lines and effort using computed property

![big](./images/watched3.png)

---

# Methods, Computed and Watchers

## Computed Setter

.text-small[
``` javascript
// ...
computed: {
  fullName: {
    // getter
    get: function () {
      return this.firstName + ' ' + this.lastName
    },
    // setter
    set: function (newValue) {
      var names = newValue.split(' ')
      this.firstName = names[0]
      this.lastName = names[names.length - 1]
    }
  }
}
// ...
vm.fullName = 'John Doe'
```
]

---



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
