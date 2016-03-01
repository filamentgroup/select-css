select-css
==========


Cross-browser CSS for consistent select element styling.

---

Demo page: [http://filamentgroup.github.io/select-css/demo/](http://filamentgroup.github.io/select-css/demo/)

Download: [select-css.css](https://github.com/filamentgroup/select-css/blob/master/src/select-css.css) and [select-css-compat.css](https://github.com/filamentgroup/select-css/blob/master/src/select-css-compat.css)

Available on npm: `npm install fg-select-css`

---

If you’re looking for the JS version of the select plugin, check out [`select`](https://github.com/filamentgroup/select).

## How it works

This styles a native select consistently cross-platform with only minimal CSS. The native select is then styled so it is essentially invisible (no appearance, border, bg) leaving only the select's text visible. There is a wrapper around the select that has the majority of the button styles (gradient, shadow, border, etc.).

There are three different CSS-only grades used in this select plugin:

1. *A-grade*: Uses custom pseudo-element arrow and hides the native arrow using `appearance: none` (or a compatible vendor prefixed property).
1. *B-grade*: Uses a custom pseudo-element arrow but hides the native arrow by making the native select wider than the container (usually using <code>calc()</code> to keep 100% width but add a fixed amount) and hiding the arrow using <code>overflow: hidden</code>.
1. *C-grade*: Uses the native select and not the custom arrow.

*Important*: The plugin should never show both the custom arrow and the native arrow at the same time. Any browser that renders both will be considered to be a visual bug and we’d love to have you file an issue on it.


## Browser Support

### A-Grade using only `select-css.css`

* MS Edge 12 and 13
* Firefox 35 through 44
* Chrome 28 through 48
* Opera 15 through 35
* Safari 9
* Yandex 14.12
* iOS 9
* Android 4.3 through 5.1

### C-Grade using only `select-css.css`

* Internet Explorer 6 through 11
* Firefox 3.6 through 34
* Chrome 15 through 27
* Opera 10.6 through 12.16
* Safari 4 through 8
* iOS 3 through 8
* Windows Phone 7.5 through 8.1
* Android 2.3, 4.2
* Blackberry 5

Most of the C-Grade support minimums are as comprehensive as Browserstack allows.

### Add `select-css-compat.css` to add B-Grade to:

* Firefox 4 through 34
* Internet Explorer 10 and 11

### For Posterity:

* [v9: February 26, 2016](http://output.jsbin.com/wurazow)
* [v8: September 18, 2015](http://output.jsbin.com/yaruh)