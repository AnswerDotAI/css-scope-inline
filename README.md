# 🌘 CSS Scope Inline

![cover](https://github.com/gnat/css-scope-inline/assets/24665/c4935c1b-34e3-4220-9d42-11f064999a57)
(Art by [shahabalizadeh](https://www.artstation.com/artwork/zDgdd))

## Why does this exist?

* You want an easy inline vanilla CSS experience without Tailwind CSS.
* Hate typing individual class and id selectors over.. and over..
* Wish to co-locate your `<style>` tags for ⚡️ [Locality of Behavior (LoB)](https://htmx.org/essays/locality-of-behaviour/)
* Really wish `this` would work in `<style>` tags.
* Want access to all new features including [CSS Nesting](https://caniuse.com/css-nesting) and animations.
* Want to keep the ability to copy + paste styles from your inspector.
* No build step. Dependency-free. Only 15 lines!
* Pairs well with [Surreal](https://github.com/gnat/surreal) and [htmx](https://htmx.org)
* Want fewer layers, less complexity. Are aware of the cargo cult. ✈️

✨ Want to also inline scope your `<script>` tags? See our companion project, [Surreal](https://github.com/gnat/surreal)

## 👁️ How does it look?
```html
<div>
    <style>
        .this { background: red; } /* ✨ .self and .me also work! */
        .this button { background: blue; }
    </style>
    <button>I'm blue</button>
</div>
```
Get a taste- see the [Live Example](https://gnat.github.io/css-scope-inline/example.html)! Then [view source](https://github.com/gnat/css-scope-inline/blob/main/example.html).

## 🌘 How does it work?

This uses `MutationObserver` to monitor the DOM, and the moment a `<style>` tag is seen, it scopes the styles to whatever the parent element is. No flashing or popping. 

This method also leaves your existing styles untouched, allowing you to mix and match at your liesure.

## 🤔 Why consider this over Tailwind CSS?

Use whatever you'd like, but there's a few advantages with this approach:

* No suffering from FOUC (a flash of unstyled content) as experienced in Tailwind CDN, Twind, UnoCSS.
* No high risk of eventually requiring a build step. It just works.
* No chance of [deprecations](https://windicss.org/posts/sunsetting.html). 15 lines is infinitely maintainable.
* Universal vanilla CSS. No special syntax or editor plugins to install.
