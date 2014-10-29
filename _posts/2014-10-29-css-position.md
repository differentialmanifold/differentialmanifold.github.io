---
layout: post
title: "CSS position"
description: ""
category: css 
tags: [css,position]
---
{% include JB/setup %}

## HTML element: content/padding/border/margin

If we take an HTML element with a special width and set it's margin to auto,thistells the documents to automatically put equal left and right margins on our element,centering it on the page.

You can also set an element's margins all at once: you just start from top margin and go around clockwise.

    margin: 1px 2px 3px 4px;

If you want to move an element in the another direction, you can give CSS a negative value: `margin-left: -20px` will move the element twenty pixels to the left.

The background color is the same for content and padding.

## display: block/inline-block/inline/none

- block: This makes the element a block box. It won't let anything sit next to it on the page.It takes up the full width.
- inline-block: This make the element a block box, but will allow other elements to sit next to it on the same lines.
- inline: This make the element sit on the same line as another element, but without formatting it like a block. It only takes up as much width as it needs.
- none: This make the element and its content disappear from the page entirely.

    <body>
	    <div>1</div>
		<div>2</div>
		<div>3</div>
	</body>

	div {
        height:50px;
		width:50px;
		border:1px solid black;
		display:inline-block;
	}

You can change the display parameter to see the effect.

## float:left/right clear:both/left/right

If you have several elements all floating, they all know the others are there and don't land on top of each other.

We can use floated elements to naturally divide our pages into different sections.

If you tell an element to `clear:left`, it will immediately move below any floating elements on the left side of the page; it can also clear element on the right. If you tell it to `clear:both`, it will get out of the way of the elements floating on the left and right.

    <body>
	    <div class=left></div>
		<div class=left></div>
		<div class=right></div>
		<div class=bottom></div>
	</body>

	div {
        height:50px;
		width:50px;
		border:1px solid black;
	}
	.left {
		float:left;
	}
    .right {
        float:right;
		height:200px;
	}
    .bottom {
        clear:both;
		width:200px;
	}

Try the code upside, and you will understand what float and clear mean.

## postion: static/absolute/relative/fixed

- static: static does nothing, it's the default value.
- absolute: When an element is set to `position:absolute`, it's then positioned in relation to the first parent element it has that doesn't have `postion:static`. If there's no such element, the element with `position:absolute`,gets positioned relative to <html>.
- relative: It tells the element to move relative to where it would have landed if it just had the default static positioning.
- fixed: Fixed positioning anchors an element to the brower window - you can think of it as gluing the element to the screen.

    <body>
	    <div class="outer"><div class="inner"></div></div>
	</body>

	.outer {
        height:200px;
		width:200px;
	    border:1px solid black;
		margin:200px;
		background-color:blue;
        position:absolute;
	}
    .inner {
        height:50px;
		width:50px;
		border:1px solid black;
		background-color:red;
        position:absolute;
		top:100px;
		left:100px;
	}

You can change the outer's position to static to see the effection.

## some more

max-width:none/length/%, when a img is inside a block, you can use `max-width:100%` on the img to let it full filled in the block.

list-style:none, delete the icon before the list.

test-decoration:none, delete the underline of the link.

cursor:pointer, let the mouse behave like you can click.
