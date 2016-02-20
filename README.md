# Rotate Background Behind Text
A simple background text with css rotate transform.
[**Code Example**](#code-example) | [**Demo**](#live-demo)

#Version 
1.1

#Code Example
- HTML

```html
  <h3>
     Text before background 
     <span class="rect">text on background</span>
     <span class="rotate"></span>
  </h3>
```
Just only last word (additional JS)
```html
  <h3 class="last-word">
     Text before background text on background
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
- Additional JS for Last Word
```js
$('h3.last-word').each(function() {
	    var $this = $(this);
	    $this.html($this.html().replace(/(\S+)\s*$/, '<span class="rect">$1</span><span class="rotate"></span>'));
	});

$('span.rect').each(function(){
		var backText = $(this).text();
		$(this).next('span.rotate').attr('data-title',backText);
});
```

#Live Demo

[**Background Text Demo on JSFiddle**](https://jsfiddle.net/mikecastillo85/7vabunqs/5/)
