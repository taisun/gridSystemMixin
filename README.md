# gridSystemMixin

関数型っぽく書きたくて書いてみました。

_tool.config.scssで設定します。

**_tool.config.scss**

```css

//grid
$max-width: 1024px; //最大幅です。
$grid-cols: 12; //gridのカラム数です。

//break point　ブレークポイントのmixin参照
$break-points: (
  pc: 1024px,
  sp: (
    min: 320px,
    max: 640px
  )
);

```
- [ブレークポイントのmixin](https://github.com/taisun/media-queries-mixin)

以下のように記述します。
メディアクエリのmixinを一部使用しています。

**style.scss**

```css
%grid-base { // gridの共通部　※必須
  display: block;
  float: left;
}

@include grids(pc); // 引数にconfigで設定した名前を渡す

@include media(sp){　// メディアクエリを使用する場合はmediaqueriesのmixinを使う
  @include grids(sp);
}
```
