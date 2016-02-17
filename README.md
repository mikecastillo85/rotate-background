# Rotate Background Behind Text
A simple background text with css rotate transform.

#Version 
1.0

#Code Example
- HTML

```html
  <h3>
     Text before background 
     <span class="rect">text on background</span>
     <span class="rotate"></span>
  </h3>
```
- CSS

```css
  h3 span {
    position: relative;
  }
  
  h3 span.rotate:before {
    content: attr(data-title);
    background: orange;
    padding: 4px;
    position:absolute;
    z-index: -1;
    color: transparent;
    right:-5px;
    margin-top: -4px;
    transform: rotate(-2deg)
  }
```
- JS

```js
$('span.rect').each(function(){
		var backText = $(this).text();
		$(this).next('span.rotate').attr('data-title',backText);
});
```
#Live Demo

[Background Demo]:(https://jsfiddle.net/mikecastillo85/7vabunqs/5/)
