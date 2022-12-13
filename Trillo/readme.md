# Trillo

Udemy 線上課程 (Advanced CSS and Sass: Flexbox, Grid, Animations and More! by Jonas Schmedtmann) 中的第二份教材，使用 flexbox 進行排版

## Project Specification

- flexbox layout
- CSS transition animation

## Note

**flexbox :**

提供開發人員用更有效率的方式完成一維(one dimensional)排版，因為已經有許多很棒的教學文件，所以就不再造輪子了。筆記用來紀錄比較特別的語法。

- margin auto :

使用 flexbox 排版的小技巧，使用`margin:auto` 元素會只佔據自身寬度，父元素剩餘寬度會被計算出來。

```scss
&__stars {
  display: flex;
  // powerful trick in flexbox, margin will be calculated.
  // Element only occupy what it needs.
  margin-right: auto;
}
```

- short-hand

`flex-grow`、`flex-shrink`、`flex-basis`三個屬性的簡寫

```scss
/* Three values: flex-grow | flex-shrink | flex-basis */
flex: 2 2 10%;
```

> 💡
>
> [CSS trick - A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)

**animation :**

CSS animation 設定 CSS 屬性轉換的動畫效果
animation 語法是

`animation-duration`

` animation-name`

` animation-iteration-count`

`animation-direction`

四個屬性的簡寫

```scss
&:focus {
  animation: pulsate 1s infinite;
}

@keyframes pulsate {
  0% {
    transform: scale(1);
    box-shadow: none;
  }
  50% {
    transform: scale(1.05);
    box-shadow: 0 1rem 4rem rgba(0, 0, 0, 0.25);
  }
  100% {
    transform: (1);
    box-shadow: none;
  }
}
```

> 💡
>
> [MDN - animation](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations)

**feature queries :**

用以測試瀏覽器是否支援某些屬性，並制定通過測試之後執行的 CSS 屬性

```scss
@supports (-webkit-mask-image: url()) or (mask-image: url()) {
  // properties that will run when the conditions matched
}
```

> 💡
>
> [MDN - Using feature queries](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Conditional_Rules/Using_Feature_Queries)
