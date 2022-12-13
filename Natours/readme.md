# Natours

Udemy 線上課程 (Advanced CSS and Sass: Flexbox, Grid, Animations and More! by Jonas Schmedtmann) 中的第一份教材，使用較舊的 float 語法與自訂的網格系統進行排版。

參考這份專案時可以參考檔案分類架構，排版語法可以使用 flexbox / grid 進行改寫。

## 語法筆記

**選擇第一個子元素 :**

```scss
.section-features {
  // .section-features > *
  & > * {
    // Some properties
  }
}
```

**漸層色背景 :**

```scss
.book {
  background-image: linear-gradient(
      105deg,
      rgba($color-white, 0.9) 0%,
      rgba($color-white, 0.9) 50%,
      transparent 50%
    ), url(../img/nat-10.jpg);
}
```

[MDN - linear-gradient()](<[https://developer.mozilla.org/en-US/docs/Web/CSS/gradient/linear-gradient](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient/linear-gradient)>)

**Object-fit 屬性 :**

設定置換元素(replaced element)的內容大小、在其容器中如何呈現。

```scss
.bg-video {
  &__content {
    height: 100%;
    width: 100%;

    // element will fill all parent element but maintain ratio
    object-fit: cover;
  }
}
```

**Clip-path 屬性 :**

使用裁剪方式創建元素的顯示區域(做出不規則形狀的容器)

```scss
clip-path: polygon(0 0, 100% 0, 100% 80%, 0 100%);
```

**:not() 選擇器 :**

偽元素選擇器，選出不符合條件的元素

```scss
// 選擇最後一個子元素外的其他子元素
&:not(:last-child) {
  margin-bottom: $gutter-vertical;
}
```

**calc() :**

CSS function，允許開發人員計算特定 CSS 屬性，方便強大的功能，要能妥善使用必須參考 MDN 手冊

```scss
.col-1-of-2 {
  width: calc((100% - #{$gutter-horizontal}) / 2);
}
```

[MDN - calc()](<[https://developer.mozilla.org/en-US/docs/Web/CSS/calc](https://developer.mozilla.org/en-US/docs/Web/CSS/calc)>)

P**seudo element :**

CSS 偽元素語法加在選擇器後面，讓開發人員對被選擇元素的特殊位置撰寫樣式，例如做漢堡按鈕的上下兩條平行線。

```scss
&::after {
  content: "";
  display: inline-block;
  height: 100%;
  width: 100%;
  position: absolute;
  top: 0;
  left: 0;
}
```

[MDN - Pseudo-elements](<[https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)>)

**Sibling selector :**

分開兩個選擇元素，並只有在第二個選擇元素緊隨第一個元素，並且兩個元素皆在同一個父元素之下

```scss
&__input:placeholder-shown + &__label {
  // Some properties
}
```

**perspective :**

屬性  perspective  指定了觀察者與 z=0 平面的距離，使具有三維位置變換的元素產生透視效果。 z>0 的三維元素比正常大，而 z<0 時則比正常小，大小程度由該屬性的值決定。

```scss
perspective: 150rem;
```
