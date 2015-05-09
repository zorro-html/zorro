# Zorro

_Hiding Goods in the Shadow_

Zorro is a collection of web components to easily use.

## Usage

Just install, import and write

### Install Zorro

```
bower install zorro
```

### Import

```
<head>
<link rel="import" href="bower_components/z-btn/z-btn.html">
</head>
```

### Write Element

by html:

```
<body>
  <z-btn>Click!</z-btn>
</body>
```

or javascript:

```
<script>
  var element = document.createElement('z-btn');
  element.innerHTML = 'Click!';
  document.body.appendChild(element);
</script>
```

## Features

- Use free, implemented on [Polymer](https://github.com/Polymer/polymer).
- Full behavior, not only class, style or theme.
- Super easy to import and use.

## Why Zorro?

First of all, around my work, there are lots of management system need to build on the web today, and many of them were developed on [Bootstrap](http://getbootstrap.com/) or Bootstrap-like UI framework just like [SUI](http://sui.taobao.org). And when first time I saw [web components](http://w3c.github.io/webcomponents) and [Polymer](http://www.polymer-project.com/). I suddenly felt this kind of work could be super simple and stupid. So I try to re-implement all the Bootstrap components and features on [Polymer](http://www.polymer-project.com/) which name of the plan is called [JIE](https://github.com/Jinjiang/JIE). At the same time I put more and more ideas about data and interaction in it. It makes the components more friendly to form, data and interactions. Finally I gave it a better name: Zorro. That's just how Zorro came out.

## Purpose

We hope Zorro could make us better and easier to support development of management-system-liked websites all around us first. And go through to feel the benefits of declarative programming, component-oriented html5 file structure and workflows which could give us more convenience and inspirations on web development in future.

### Super Simple to Write

For each component, it's not only for the "common sence" of the dom structure + class name, but a simple and easy tag name. For example, a dialog component in Bootstrap is like below:

```
<div class="modal fade">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <button type="button" class="close" data-dismiss="modal" aria-label="Close"><span aria-hidden="true">&times;</span></button>
        <h4 class="modal-title">Modal title</h4>
      </div>
      <div class="modal-body">
        <p>One fine body&hellip;</p>
      </div>
    </div><!-- /.modal-content -->
  </div><!-- /.modal-dialog -->
</div><!-- /.modal -->
```

And the Zorro's:

```
<z-dialog label="Modal title">
  <p>One fine body&hellip;</p>
</z-dialog>
```

It hide all the repeatly-wrtten code to the shadow with a very simple tag: `<z-dialog>`

Also, it's simple to be created by JavaScript anytime just with `createElement`:

```
var element = document.createElement('z-dialog');
element.label = 'Modal title';
element.innerHTML = '<p>One fine body&hellip;</p>';
// document.body.appendChild(element);
```

### More Than Display, But Data & Interactions

When we use Bootstrap, we often need to write more JavaScript manually. Because Bootstrap almost doesn't consider how to bind data and handle data changes and user interactions. That's really boring task for web developers everyday. We put Bootstrap styles, data and actions together as a whole completely component. And hide the logic between data, event and display internal.

Take pagination for example, in Bootstrap:

```
<nav>
  <ul class="pagination">
    <li>
      <a href="#" aria-label="Previous">
        <span aria-hidden="true">&laquo;</span>
      </a>
    </li>
    <li><a href="#">1</a></li>
    <li><a href="#">2</a></li>
    <li><a href="#">3</a></li>
    <li><a href="#">4</a></li>
    <li><a href="#">5</a></li>
    <li>
      <a href="#" aria-label="Next">
        <span aria-hidden="true">&raquo;</span>
      </a>
    </li>
  </ul>
</nav>
```

In fact you should have to use template engine or JavaScript to describe the pagination details.

```
<nav>
  <ul class="pagination">
    <template repeat="{{i in pagelist}}">
      <li><a href="#" on-click="{{changeCurrentPage(i)}}">{{i + 1}}</a></li>
    </template>
  </ul>
</nav>
```

or

```
<script>
  var ul = document.querySelector('.pagination');
  // generate all li > a and append
  // bind each click event to re-render
</script>
```
And in Zorro:

```
<z-pagination value="3" max="10"></z-pagination>
```

That's it! When user click each page item, the pagination will automatically changed current page and re-render itself, and also, fire a page-changed event with the new current page number as the value.

### Re-thinking About Forms

In re-implementing common elements. We felt more uncomfortable in forms. It make us paint sometimes. We conclude that user just do two things in forms:

1. answer open question: input text, date, password, number, range, phone number ...
2. answer closed question: select, radio, checkbox ...

So we ventured to change the forms:

1. `<z-input-text type="text|password|textarea|...">`: open question for text, date or number
2. `<z-input-select flatten="auto|true|false" multi>`: closed question for a single/multiple selection, and the `[flatten]` attribute is to described how options display: `true` for `input[type="radio"]`/`input[type="checkbox"]` and `false` for `select > option`.

We think that's more directly target the purpose and easy to use.

### Make Lovely Elements As Many As Possible

- `<z-phone>` make you easy to check how a web page displayed in your phone
- `<z-rmb>` is a mostly used and hard written manually component in my job... It save my workmates a lot of time.
- `<z-progress>`'s value could be bind to any JavaScript object which supports [Progress Events](http://www.w3.org/TR/progress-events/).
- `<z-dock>` makes webapp layout much easier.

There are lots of ideas and improvements in Zorro waiting for you to discover them.

## Components Gallery

- [z-typo](https://github.com/zorro-html/z-typo)
- [z-table](https://github.com/zorro-html/z-table)
- [z-icon](https://github.com/zorro-html/z-icon)
- [z-btn](https://github.com/zorro-html/z-btn)
- [z-menu](https://github.com/zorro-html/z-menu)
- [z-dropdown](https://github.com/zorro-html/z-dropdown)
- [z-btn-group](https://github.com/zorro-html/z-btn-group)
- [z-nav](https://github.com/zorro-html/z-nav)
- [z-panel](https://github.com/zorro-html/z-panel)
- [z-breadcrumb](https://github.com/zorro-html/z-breadcrumb)
- [z-pagination](https://github.com/zorro-html/z-pagination)
- [z-dock](https://github.com/zorro-html/z-dock)
- [z-grid](https://github.com/zorro-html/z-grid)
- [z-bar](https://github.com/zorro-html/z-bar)
- [z-input](https://github.com/zorro-html/z-input)
- [z-progress](https://github.com/zorro-html/z-progress)
- [z-rmb](https://github.com/zorro-html/z-rmb)
- [z-tag](https://github.com/zorro-html/z-tag)
- [z-time](https://github.com/zorro-html/z-time)
- [z-note](https://github.com/zorro-html/z-note)
- [z-phone](https://github.com/zorro-html/z-phone)
- [z-dialog](https://github.com/zorro-html/z-dialog)
- [z-tooltip](https://github.com/zorro-html/z-tooltip)
- [z-mask](https://github.com/zorro-html/z-mask)
- [z-script](https://github.com/zorro-html/z-script)

## Notes

### Compatibilities

As the words above, Zorro development is based on Polymer. So you should have to add [webcomponents polyfill](https://github.com/webcomponents/webcomponentsjs) in browsers which is not full-supported for web components. And currently, we just make sure Zorro works fine in webkit, maybe some mistakes and bugs in gecko / trident / spartan ... in some kind of `-moz-` `-ms-` prefix issues. We believe that's easy to fixed in the future.

### Performance

Acturely, the performance of Zorro mostly depends on Polymer project. That's not very well for production yet, espacially on the mobile. So does the compatibilities. In another way that's why Zorro is focused on (internal) management system websites. Because most kind of these website are not extremely required about the rendering details but the functionality and structured component design. A good news is that the [next version of Polymer](https://www.polymer-project.org/0.8/) will make better in compatibilities and performance. Zorro has chance to follow this plan.

## What's Next?

- supports more browser vendors
- new components in pure inteactions like:
    - drag-n-drop
    - popups
    - layer manager
    - validators etc.
- easily theme changing
- more thinking for touch events
- tools for contributing, import and deployment

## Want to Contribute?

Well. If you have read here, maybe you have been interested in Zorro. It you want to join us for contribution. Please contact [any of our org members](https://github.com/orgs/zorro-html/people). Or:

- write a component with [yeoman generator: zorro](https://github.com/zorro-html/zorro-generator)
- fix a bug or support more browsers, and send pull request to us
- [write issue](https://github.com/zorro-html/zorro/issues) to report a bug or suggestion

## License

[MIT](http://opensource.org/licenses/MIT)

Copyright (c) 2015 Jinjiang
