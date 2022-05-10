---
layout: post
title: MustacheJS
date: 2022-05-12 2:02 +0700
categories: [TemplateEngineHTML, MustacheJS]
tags: [Javascript]
---

check stackoverflow : tag : mustache  
google search : adobe illustrator, vector, save as into html/SVG  

## Mustache[JS](https://github.com/janl/mustache.js)

> disadvantage :
- logic-less : didnt have if statements, else clauses, for loops

install : ```npm install mustache --save```

usage :
```javascript
  var Mustache = require('mustache');

  var view = {
    title: "Joe",
    calc: function () {
      return 2 + 4;
    }
  };

  var output = Mustache.render("{{title}} spends {{calc}}", view);
```

## Template

Internal templates :
```javascript
  // file: render.js
  function renderHello() {
    var template = document.getElementById('template').innerHTML;
    var rendered = Mustache.render(template, { name: 'Luke' });
    document.getElementById('target').innerHTML = rendered;

  <html>
    <body onload="renderHello()">
      <div id="target">Loading...</div>
      <script id="template" type="x-tmpl-mustache">
        Hello {{ name }}!
      </script>

      <script src="https://unpkg.com/mustache@latest"></script>
      <script src="render.js"></script>
    </body>
   </html>
```

External Template, another example using ```fetch```:
```javascript
  function renderHello() {
    fetch('template.mustache')
      .then((rensponse) => response.text())
      .then((template) => {
        var rendered = Mustache.render(template, {name: 'Luke' });
        document.getElementById('target').innerHTML = rendered;
      });
  }
```

all variables are HTML-escaped by default, if you want to render unescaped HTML, use the triple mustache: ```{{{name}}}```, you can also use ```&``` to unescape a variable.

if you would like tho change HTML-escaping behavior globally (for example, to template non-HTML formats), you can override Mustache's escape function. For example to disable all escaping: `Mustache.escape = function(text) {return text;};`.

you you want ``{{name}}`` not to be interpreted as a mustache tag, but rather to appear exactly as `{{name}}` in the output, you must change and then restore the default delimiter.
by overriding the `mustache.tags` property itself:
```javascript
  var customTags = [ '<%', '%>' ];
```

pass value into render method
```javascript
  Mustache.render(template, view, {}, customTag);
```

override tags property
```javascript
  Mustache.tags = customTags;
  // Subsequent parse() and render() calls will use customTags
```

## sections
view
```json
  {
    "person": false
  }
```

template :
```mustache
  Shown.
  {{#person}}
  Never shown!
  {{/person}}
```

## non-empty lists
if the `person` key exist and is not `null`, `undefined`, or `false`, and is not an empty list the block will be rendered one or more times.
```mustache
// view
{
  "stooges": [
    { "name": "Moe"},
    { "name": "Larry" },
    { "name": "Curly" }
  ]
}

// template

  {{#stooges}}
  <b>{{name}}</b>
  {{/stooges}}

//output

  <b>Moe</b>
  <b>Larry</b>
  <b>Curly</b>
```
> when looping over an array of strings, a `.` can be used to refer to the current item in the list.
```mustache
  // view

  {
    "musketeers": ["Athos", "Aramis", "Porthos", "D'Artagnan"]
  }

  // template

  {{#musketeers}}
  * {{.}}
  {{/musketeers}}

  // output

  * Athos
  * Aramis
  * Porthos
  * D'Artagnan
```

> if the value of a section variable is a function, it will be called in the context of the current item in the list on each iteration.
```mustache
{
  "beatles": [
    { "firstName": "John", "lastName": "Lennon" },
    { "firstName": "Paul", "lastName": "McCartney" },
    { "firstName": "Goerge", "lastName": "Harrison" },
    { "firstName": "Ringo", "lastName": "Starr" }
  ],
  "name": function () {
    return this.firstName + " " + this.lastname;
  }
}

// template

{{#beatles}}
* {{name}}
{{/beatles}}

// output

  * John Lennon
  * Paul McCartney
  * George Harrison
  * Ringo Starr
```

## functions
if the value of a section key is a function, it is called with the section's literal block of text, un-rendered, as its first argument. the second argument is a special rendering function that uses the current view as its view argument. it is called in the context of the current view object.
```mustache
// view

  {
    "name": "Tater",
    "bold": function () {
      return function (text, render) {
        return "<b>" + render(text) + "</b>;
      }
    }
  }

// template

  {{#bold}}Hi {{name}}.{{/bold}}

// output

  <b>Hi Tater.</b>
```

## inverted sections
