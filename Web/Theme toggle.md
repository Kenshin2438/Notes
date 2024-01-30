```JavaScript
document.documentElement.setAttribute('data-theme',
  localStorage.getItem('theme') ||
  (window.matchMedia('(prefers-color-scheme: dark)').matches ? 'dark' : 'light')
);
document.getElementById("theme-toggle").addEventListener("click", () => {
  var setTheme = document.documentElement.getAttribute('data-theme') === 'light' ? 'dark' : 'light';
  document.documentElement.setAttribute('data-theme', setTheme);
  localStorage.setItem('theme', setTheme);
});
```

在 JavaScript 中可以使用 `dataset` 属性来访问和修改 HTML 元素的 `data-*` 属性。

```html
<html lang="zh-cn" data-theme="">
```

使用 `window.matchMedia()` 方法来检测用户的操作系统主题。这个方法接收一个媒体查询字符串并返回一个 `MediaQueryList` 对象，该对象表示文档当前是否匹配给定的媒体查询。

要在页面刷新后保持 `data-theme` 的值不变，则需要将其存储在浏览器的本地存储中，并在每次刷新后检查和设置。

---

- [Theme Toggles](https://toggles.dev/)
