# Configuration

docsify supports two ways to configure. You can configure the `window.$docsify` or write configuration on the script tag via `data-*` attributes.

```html
<!-- by $docsify -->
<script>
  window.$docsify = {
    repo: 'QingWei-Li/docsify',
    maxLevel: 3,
    coverpage: true
  }
</script>

<!-- or data-* -->
<script
  src="//unpkg.com/docsify"
  data-repo="QingWei-Li/docsify"
  data-max-level="3"
  data-coverpage>
</script>
```

Both ways are compatible. However, the first way is recommended. It is clear and can be configured in a separate file.

!> In `window.$docsfiy`, the options should be written by camelCase.

## el

- Type: `String`
- Default: `#app`

The DOM element to be mounted on initialization. It can be a CSS selector string or an actual HTMLElement.

```js
window.$docsify = {
  el: '#app'
}
```

## repo

- Type: `String`
- Default: `null`

Configure the repository url or a string of `username/repo` can add the [GitHub Corner](http://tholman.com/github-corners/) widget in the top right corner of the site.

```js
window.$docsify = {
  repo: 'QingWei-Li/docsify',
  // or
  repo: 'https://github.com/QingWei-Li/docsify/'
}
```


## max-level

- Type: `Number`
- Default: `6`

Maximum Table of content level.

```js
window.$docsify = {
  maxLevel: 4
}
```

## load-navbar

- Type: `Boolean|String`
- Default: `false`

Load navbar from Markdown file. If **true** it will be loaded from `_navbar.md`.

```js
window.$docsify = {
  // load from _navbar.md
  loadNavbar: true,

  // load from nav.md
  loadNavbar: 'nav.md'
}
```

## load-sidebar

- Type: `Boolean|String`
- Default: `false`


Load sidebar from Markdown file. If **true** it will be loaded from `_sidebar.md`.

```js
window.$docsify = {
  // load from _sidebar.md
  loadSidebar: true,

  // load from summary.md
  loadSidebar: 'summary.md'
}
```

## sub-max-level

- Type: `Number`
- Default: `0`

Add TOC in custom sidebar.

```js
window.$docsify = {
  subMaxLevel: 2
}
```


## auto2top

- Type: `Boolean`
- Default: `false`


Scrolls to the top of the screen when the route is changed.

```js
window.$docsify = {
  auto2top: true
}
```


## homepage

- Type: `String`
- Default: `README.md`


`README.md` in your docs folder will be treated as homepage for your website, but sometimes you may need to serve another file as your homepage.

```js
window.$docsify = {
  // Change to /home.md
  homepage: 'home.md',

  // Or use the readme in your repo
  homepage: 'https://raw.githubusercontent.com/QingWei-Li/docsify/master/README.md'
}
```

## base-path

- Type: `String`

Base path of the website. You can set it to another directory or another domain name.

```js
window.$docsify = {
  basePath: '/path/',

  // Load the files from another site
  basePath: 'https://docsify.js.org/',

  // Even can load files from other repo
  basePath: 'https://raw.githubusercontent.com/ryanmcdermott/clean-code-javascript/master/'
}
```


## coverpage

- Type: `Boolean|String`
- Default: `false`

Activate the [cover feature](/cover). If ture, it will load from `_coverpage.md`.

```js
window.$docsify = {
  coverpage: true,

  // Custom file name
  coverpage: 'cover.md'
}
```

## name

- Type: `String`


Website name appears in the sidebar.

```js
window.$docsify = {
  name: 'docsify'
}
```

## name-link

- Type: `String`
- Default: `window.location.pathname`

The name of the link.

```js
window.$docsify = {
  nameLink: '/',

  // For each route
  nameLink: {
    '/zh-cn/': '/zh-cn/',
    '/': '/'
  }
}
```

## markdown

- Type: `Function`

See [Markdown configuration](/markdown).


```js
window.$docsify = {
  // object
  markdown: {
    smartypants: true,
    renderer: {
      link: function() {
        // ...
      }
    }
  },

  // function
  markdown: function (marked, renderer) {
    // ...
    return marked
  }
}
```

## theme-color

- Type: `String`

Customize the theme color.
Use [CSS3 variables](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_variables) feature and polyfill in old browser.

```js
window.$docsify = {
  themeColor: '#3F51B5'
}
```

## alias

- Type: `Object`


Set the route alias. You can freely manage routing rules.

```js
window.$docsify = {
  alias: {
    '/zh-cn/changelog': '/changelog',
    '/changelog': 'https://raw.githubusercontent.com/QingWei-Li/docsify/master/CHANGELOG'
  }
}
```

## auto-header

- type: `Boolean`

If `loadSidebar` and `autoHeader` are both enabled, for each link in _sidebar.md, prepend a header to the page before converting it to html. [#78](https://github.com/QingWei-Li/docsify/issues/78)

```js
window.$docsify = {
  loadSidebar: true,
  autoHeader: true
}
```

## execute-script

- type: `Boolean`

Execute the script on the page. Only parse the first script tag([demo](themes)).  If Vue is present, it is turned on by default.

```js
window.$docsify = {
  executeScript: true
}
```

```markdown
## This is test

<script>
  console.log(2333)
</script>

```

