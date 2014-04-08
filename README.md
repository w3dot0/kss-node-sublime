# kss-node-sublime

Generate [Sublime Text](http://www.sublimetext.com/) snippets from a directory of [Knyle Style Sheets](https://github.com/kneath/kss) (KSS), "a documentation syntax for CSS".

## Example

By running the kss-sublime command with default option this KSS comment:

```css
// Label/Textbox Pairs
//
// All labelled textboxes should be included in a wrapper `<div>` element for both layout
// convenience and specific styling.
//
// Markup:
// <div class="mod-input text {$modifiers}">
//     <label>Text Label</label>
//     <input type="text" value="Text Input"/>
// </div>
//
// .disabled  - To be used when the text input inside is expected to be disabled.
// .invalid   - To be used if the input has failed a validation check.
// .valid     - To be used if the input has passed a validation check (intended for live validation in particular).
//
// Styleguide 2.1.2
```

will be converted into a sublime snippet file named kss_labeltextbox_pairs.sublime-snippet

```xml
<snippet>
  <content><![CDATA[<div class="mod-input text ${1:disabled},${2:invalid},${3:valid}">
    <label>Text Label</label>
    <input type="text" value="Text Input"/>
</div>]]></content>
  <tabTrigger>kss_labeltextbox_pairs</tabTrigger>
  <description>Label/Textbox Pairs</description>
  <scope>text.html</scope>
</snippet>
```

You can expand this snippet in Sublime in two ways:

- type `kss` (the configurable prefix) and `Ctrl + Space` to select one of the generate snippets.
- type `kss_labeltextbox_pairs` + `tab`

## Installation

npm install -g kss-sublime

## Usage

```
kss-sublime -i sourcedir -o destdir -p prefix

Options:
  -i, --input dir   Styleguide directory        [required]
  -o, --output dir  Output directory            [default: "~/Library/Application Support/Sublime Text 2/Packages/{prefix}"]
  -p, --prefix      Snippet tab trigger prefix  [default: "kss"]
```

