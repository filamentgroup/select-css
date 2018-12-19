select-css
==========


Cross-browser select element CSS for consistent select element styling.

Article: https://www.filamentgroup.com/lab/select-css.html



---

Demo page: [http://filamentgroup.github.io/select-css/demo/](http://filamentgroup.github.io/select-css/demo/)

Download: [select-css.css](https://github.com/filamentgroup/select-css/blob/master/src/select-css.css)

Available [on npm](https://www.npmjs.com/package/fg-select-css): `npm install fg-select-css`

---

## Usage

Include the following file:

* [`src/select-css.css`](src/select-css.css): main component code

Its CSS will style any select with a class of `select-css`

### Notes on the CSS

The CSS for this is fine to use as-is, but if you're editing it at all, you might want to be aware of a few numbers and values that help it look right.

- The `select` is set to `display: block` by default but you can style it `display: inline-block; width: auto;` if you'd like it to sit alongside a `label`.
- The background of the `select` is created using two background images: the first is an svg arrow icon (expressed inline as a data URI) and the second is a repeating linear gradient. Either URL could be an external image if you'd like. If you change the icon image, be aware that its size is set in the first section of the later `background-size: .65em auto, 100%;` property. And its position is set via `background-position: right .7em top 50%, 0 0;` (which is `.7em` from the right side, respectively). Also, if the size changes, you might want to make more right padding on the button so that it doesn't overlap the `select`'s text, but be aware that in IE9 and older, the custom arrow will not appear, and the browser's default arrow will show to the left of the padding, so don't add too much there or IE9's arrow will be inset really far.
- The linear gradient background is important to keep, because its presence actually prevents IE9 and older from recognizing the background property, and as a result it won't show the custom icon alongside its unhideable native one. **If you want a flat color, use a linear gradient between two of the same color values.**
- The `appearance` rule and its and prefixed versions are important to unset some default browser `select` styling.
- The `font-size: 16px;` rule is important because iOS Safari will zoom-in the site layout if the `select`'s text is less than 16px. Generally, this behavior is annoying so we try to avoid it with a 16px font size on `select`s.
- The `.select-css option` keeps `option` elements from inheriting the bold font weight of the `select` button itself.
- As noted in [Scott O'Hara's article](https://scottaohara.github.io/a11y_styled_form_controls/src/select/), setting background color on the `select` (though not background *image* as I've used here, can cause `option` elements to inherit background colors as well, which can cause problems. So avoid doing that. ) 
- The `.select-css::-ms-expand` rule instructs IE11 and IE10 to hide the menu icon pseudo element, so the custom icon behind it can appear. Thanks for the tip, Jelmer de Maat.


#### For Posterity:
* [v1](https://github.com/filamentgroup/select-css/tree/v1)
* [v9: February 26, 2016](http://output.jsbin.com/wurazow)
* [v8: September 18, 2015](http://output.jsbin.com/yaruh)

If you’re looking for a custom select that uses JavaScript for additional features, check out [`select`](https://github.com/filamentgroup/select).
