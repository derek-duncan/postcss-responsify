# postcss-responsify
[PostCSS](https://github.com/postcss/postcss) plugin to create responsive classes with the `@responsive` rule.

```javascript
const postcss = require('postcss');
const responsify = require('postcss-responsify');

const breakpoints = [
  { prefix: 'sm-', mediaQuery: '(min-width: 40em)' },
  { prefix: 'md-', mediaQuery: '(min-width: 52em)' },
]
postcss()
  .use(responsify()({
    breakpoints
  }));
```

**PostCSS**
```css
@responsive {
  .col { float: left; box-sizing: border-box; }
  .col-1 { width: calc(1/12 * 100%); }
  .col-2 { width: calc(2/12 * 100%); }
  .col-3 { width: calc(2/12 * 100%); }
}
```

**CSS**
```css
.col { float: left; box-sizing: border-box; }
.col-1 { width: calc(1/12 * 100%); }
.col-2 { width: calc(2/12 * 100%); }
.col-3 { width: calc(2/12 * 100%); }

@media (min-width: 40em) {
  .sm-col { float: left; box-sizing: border-box; }
  .sm-col-1 { width: calc(1/12 * 100%); }
  .sm-col-2 { width: calc(2/12 * 100%); }
  .sm-col-3 { width: calc(2/12 * 100%); }
}

@media (min-width: 52em) {
  .md-col { float: left; box-sizing: border-box; }
  .md-col-1 { width: calc(1/12 * 100%); }
  .md-col-2 { width: calc(2/12 * 100%); }
  .md-col-3 { width: calc(2/12 * 100%); }
}
```
