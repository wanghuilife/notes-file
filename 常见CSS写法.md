# 一、文本处理

## 1、文子溢出处理

一行溢出

```css
  overflow: hidden;
  text-overflow:ellipsis;
  white-space: nowrap;
```

指定行溢出

```css
  display: -webkit-box;
  -webkit-box-orient: vertical;
  box-orient: vertical;
  -webkit-line-clamp: 2;
  line-clamp: 2;
  overflow: hidden;
```