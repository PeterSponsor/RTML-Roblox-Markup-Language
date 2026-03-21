# RTML

RTML is a markup language for building modern Roblox UI with:

- HTML-like structure
- CSS-like styling
- Luau scripting for interactivity

It is designed to make interface authoring fast, expressive, and easy to read.
The engine is maintained by me, the source is not public as of 21/03/2026
![image](/image.png)

You can use the engine which have a lua file at this repository now by running this example

´´´lua
-- Demo for the Engine, you can learn how to use it on my github
loadstring(game:HttpGet("https://raw.githubusercontent.com/PeterSponsor/RTML-Roblox-Markup-Language/refs/heads/main/Engine.lua"))()

RTML.render([[
<screenui resetonspawn="false" ignoreguiinset="true">
	<frame
		size="0,280,0,150"
		anchorpoint="0.5,0.5"
		position="0.5,0,0.5,0"
		backgroundcolor="#ffffff"
		borderpixelsize="0"
		dragging="true"
		active="true"
		strokecolor="#000000"
		stroketransparency="0.88"
		thickness="1"
		cornerradius="0,16"
	>
		<textlabel
			size="1,-40,0,34"
			position="0,20,0,22"
			backgroundtransparency="1"
			text="Hello"
			textcolor="#000000"
			font="GothamBold"
			fontsize="28"
			textxalignment="Center"
			draghandle="true"
		/>

		<button
			id="openPopupButton"
			size="1,-40,0,44"
			position="0,20,0,82"
			text="Click me"
			backgroundcolor="#000000"
			textcolor="#ffffff"
			font="GothamBold"
			fontsize="18"
			borderpixelsize="0"
			cornerradius="0,12"
			autobuttoncolor="false"
			onclick="
				context.show('helloPopup')
			"
		/>
	</frame>

	<frame
		id="helloPopup"
		size="0,260,0,220"
		anchorpoint="0.5,0.5"
		position="0.5,0,0.34,0"
		backgroundcolor="#ffffff"
		backgroundtransparency="0"
		borderpixelsize="0"
		visible="false"
		dragging="true"
		active="true"
		strokecolor="#000000"
		stroketransparency="0.88"
		thickness="1"
		cornerradius="0,14"
		zindex="20"
	>
		<textlabel
			size="1,-32,0,30"
			position="0,16,0,14"
			backgroundtransparency="1"
			text="Hello"
			textcolor="#000000"
			font="GothamBold"
			fontsize="26"
			textxalignment="Center"
			zindex="21"
			draghandle="true"
		/>

		<image
			id="popupEmoji"
			size="0,64,0,64"
			position="0.5,-32,0,58"
			url="https://raw.githubusercontent.com/twitter/twemoji/master/assets/72x72/1f60a.png"
			backgroundtransparency="1"
			scaletype="Fit"
			zindex="21"
		/>

		<button
			size="1,-32,0,40"
			position="0,16,1,-54"
			text="Close"
			backgroundcolor="#000000"
			textcolor="#ffffff"
			font="GothamBold"
			fontsize="16"
			borderpixelsize="0"
			cornerradius="0,12"
			autobuttoncolor="false"
			zindex="21"
			onclick="
				context.hide('helloPopup')
			"
		/>
	</frame>
</screenui>
]])
´´´

## Start Here

If you want to learn the language quickly, open:

- [LEARN.md](LEARN.md)

That guide covers:

- syntax
- tags
- styling
- layouts
- components
- scripting
- examples

## Language Highlights

RTML supports:

- `window`, `section`, `card`, `vstack`, `hstack`
- text, buttons, inputs, images, scrolling containers
- tabs with `tabbutton` and `tabpanel`
- built-in controls like `dropdown`, `slider`, `toggle`, `colorpicker`, `keybindinput`
- data views like `datatable` and `virtuallist`
- overlays like `modal`, `tooltip`, and `popover`
- theme-friendly styling with gradients, corners, strokes, and reusable classes
- inline logic with `onclick`
- larger Luau blocks with `<script>`

## Learning Path

Recommended order:

1. Read [LEARN.md](LEARN.md)
2. Have fun!
3. Open [MenuExample.rtml](/C:/Users/peter/Documents/RTML-Roblox/examples/MenuExample.rtml)

