# CSS-ratingbar

HTML standards-compliant ratingbar with CSS. (complete unchecking via JS)  

screenshot:  
![screenshot][image]

check live sample here http://codepen.io/jkallunki/pen/ORRbwZ

[image]: https://raw.githubusercontent.com/J-Kallunki/css-ratingbar/master/Screen%20Shot%202016-09-19%20at%2009.55.57.png

Stylus (css):
```stylus
.nakkebar
  max-width $iconSize * 4
  unicode-bidi bidi-override
  direction rtl
  white-space nowrap
  white-space-collapsing discard
  font-size 0
  .nakkelabel
    display inline-block
    position relative
    width $iconSize
    height $iconSize
    overflow hidden
    cursor pointer
    &:before,
    &:after
      position absolute
      top 0
      left 0
      bottom 0
      right 0
      content ''
    &:after
      smallerSize()
      iconImage(1)
  .nakkeradio
    position absolute
    margin-left -9999px
    visibility hidden
  // Styles for checked and hovered items
  &:not(:hover) .nakkeradio:checked ~ .nakkelabel:after,
  .nakkelabel:hover:after,
  .nakkelabel:hover ~ .nakkelabel:after
    width $iconSize
    height $iconSize
    iconImage(3)
  &:not(:hover) .nakkeradio:checked ~ .nakkelabel:before,
  .nakkelabel:hover:before,
  .nakkelabel:hover ~ .nakkelabel:before
    iconImage(2)
```
HTML:
```html
<form class="nakkebar">
    <input type="radio" name="nakkerating" value="0" id="value-4" class="nakkeradio nakkeradio-4"><label for="value-4" class="nakkelabel">0</label>
    <input type="radio" name="nakkerating" value="3" id="value-3" class="nakkeradio nakkeradio-3"><label for="value-3" class="nakkelabel">3</label>
    <input type="radio" name="nakkerating" value="2" id="value-2" class="nakkeradio nakkeradio-2"><label for="value-2" class="nakkelabel">2</label>
    <input type="radio" name="nakkerating" value="1" id="value-1" class="nakkeradio nakkeradio-1"><label for="value-1" class="nakkelabel">1</label>
</form>
```
