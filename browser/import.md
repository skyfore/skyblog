基础用法：

```html
//  index.html

<script type="module">
  import a from './a.js';
  a();
</script>
```

```js
//  a.js

'use strict';

function a () {
  console.log('This is a!');
}

export default a;
```

但是，假如是需要`动态引用`这种写法就会报错，所以需要修改一下 index.html 的内容

```html
//  index.html

<script>
  const path = './a.js';
  import(path).then(m => m.default()).catch(e => console.error(e));
</script>

```

> 
  - source: https://www.jianshu.com/p/386916c73dad
  - mdn: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import
