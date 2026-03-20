# RTML Learn

RTML stands for `Roblox Text Markup Language`.

It is a markup language for building Roblox UI with:

- HTML-like structure
- CSS-like styling
- Luau scripting for interaction

This document is meant to teach the language itself quickly.

## What RTML Can Do

With RTML you can:

- build Roblox UI using tags
- style UI with `<style>`
- create layouts with stacks
- make responsive windows
- create tabs
- attach behavior with `onclick`
- write larger Luau logic with `<script>`
- use built-in high-level components like dropdowns, sliders, modals, tables, and more

## Basic Structure

Minimal example:

```html
<screenui resetonspawn="false" ignoreguiinset="false">
	<frame size="1,0,1,0" backgroundcolor="#0f172a">
		<textlabel
			size="1,0,0,48"
			backgroundtransparency="1"
			textcolor="#ffffff"
			font="GothamBold"
			fontsize="24"
			text="Hello RTML"
		/>
	</frame>
</screenui>
```

## Core Tags

RTML supports these base tags:

- `screenui`
- `frame`
- `card`
- `tabs`
- `vstack`
- `hstack`
- `text`
- `label`
- `textlabel`
- `button`
- `textbutton`
- `tabbutton`
- `input`
- `textbox`
- `image`
- `imagelabel`
- `imagebutton`
- `scroll`
- `scrollingframe`
- `tabpanel`
- `gradient`
- `uilistlayout`
- `uigridlayout`
- `uipagelayout`
- `uipadding`
- `uicorner`
- `uistroke`
- `uiscale`
- `uiaspectratioconstraint`
- `uisizeconstraint`
- `style`
- `script`

Useful aliases:

- `card` is a styled `Frame`
- `vstack` is a vertical stack container
- `hstack` is a horizontal stack container
- `input` is a `TextBox`
- `button` is a `TextButton`
- `scroll` is a `ScrollingFrame`

## Built-In Components

RTML also supports high-level components:

- `window`
- `section`
- `toggle`
- `slider`
- `dropdown`
- `colorpicker`
- `keybindinput`
- `searchablecombobox`
- `combobox`
- `datatable`
- `datagrid`
- `modal`
- `dialog`
- `tooltip`
- `popover`
- `circularprogress`
- `progresscircle`
- `virtuallist`
- `virtualizedlist`

These are the fastest way to build modern menus.

## Quick Example

```html
<screenui resetonspawn="false" ignoreguiinset="false">
	<window
		id="mainWindow"
		title="RTML Demo"
		subtitle="Fast Roblox UI"
	>
		<section title="Welcome" description="A simple first panel.">
			<input id="nameInput" preset="input" size="1,0,0,46" placeholder="Type here..." />
			<button id="helloButton" preset="primary" size="0,180,0,44" text="Say hello" />
		</section>

		<script>
local input = context.get("nameInput")
local button = context.get("helloButton")

button.MouseButton1Click:Connect(function()
	print("Hello", input.Text)
end)
		</script>
	</window>
</screenui>
```

## Styling with `<style>`

RTML includes a stylesheet system.

Example:

```html
<style>
button {
	font: GothamBold;
	fontSize: 16;
}

.primary {
	backgroundColor: #2563eb;
	textColor: #ffffff;
	cornerRadius: 0,14;
}

#title {
	textColor: #ffffff;
	fontSize: 30;
}

.primary:hover {
	backgroundTransparency: 0.08;
}
</style>
```

### Supported Selectors

- tag selector: `button`
- class selector: `.primary`
- id selector: `#title`
- universal selector: `*`
- hover state: `button:hover`, `.primary:hover`, `#saveButton:hover`

### What the Stylesheet Does Not Support

RTML styles do not currently support:

- descendant selectors
- child selectors
- advanced chained selectors
- pseudo states other than `:hover`

Good:

- `button`
- `.card`
- `#header`
- `.primary:hover`

Not supported:

- `.sidebar button`
- `frame > textlabel`

## `class` and `id`

You can use classes and ids like this:

```html
<textlabel id="title" class="heading whiteText" text="Dashboard" />
```

Multiple classes are allowed:

```html
class="card large primary"
```

## Inline `style`

You can add inline style directly on an element:

```html
<button
	text="Click"
	style="backgroundcolor:#2563eb; textcolor:#ffffff; cornerradius:0,14;"
/>
```

## Hover Styles

Hover works in two ways.

Stylesheet hover:

```html
<style>
.menuButton:hover {
	backgroundTransparency: 0;
}
</style>
```

Inline hover:

```html
<button
	class="menuButton"
	hoverstyle="backgroundcolor:#1d4ed8; textcolor:#ffffff;"
	text="Hover me"
/>
```

## Visual Presets

Available presets:

- `card`
- `surface`
- `glass`
- `hero`
- `primary`
- `accent`
- `ghost`
- `input`
- `pill`
- `window`

Examples:

```html
<card preset="hero">
	<textlabel text="Hero Card" />
</card>
```

```html
<button preset="primary" text="Save" />
```

```html
<input preset="input" placeholder="Search..." />
```

## Common Attributes

### Layout and position

- `size="sx,ox,sy,oy"`
- `position="sx,ox,sy,oy"`
- `anchorpoint="x,y"`
- `rotation="number"`
- `zindex="number"`
- `layoutorder="number"`
- `visible="true/false"`
- `active="true/false"`
- `clipsdescendants="true/false"`

### ScreenGui attributes

- `resetonspawn`
- `ignoreguiinset`
- `displayorder`
- `enabled`

### Text attributes

- `text`
- `value`
- `textcolor`
- `textcolor3`
- `texttransparency`
- `textscaled`
- `textwrapped`
- `richtext`
- `fontsize`
- `font`
- `textxalignment`
- `textyalignment`
- `lineheight`
- `placeholdertext`
- `placeholder`
- `placeholdercolor`
- `cleartextonfocus`
- `multiline`
- `texteditable`
- `cursorposition`

### Image attributes

- `image`
- `imagecolor`
- `imagecolor3`
- `imagetransparency`
- `scaletype`
- `slicecenter`

### Layout attributes

- `filldirection`
- `filldirectionmaxcells`
- `horizontalalignment`
- `verticalalignment`
- `horizontalflex`
- `verticalflex`
- `itemlinealignment`
- `sortorder`
- `padding`
- `paddingtop`
- `paddingbottom`
- `paddingleft`
- `paddingright`
- `gap`

### Stroke, corners, gradients, constraints

- `cornerradius`
- `thickness`
- `strokecolor`
- `stroketransparency`
- `strokeapplymode`
- `gradientcolor`
- `gradienttransparency`
- `gradientrotation`
- `gradientoffset`
- `aspectratio`
- `aspecttype`
- `dominantaxis`
- `minsize`
- `maxsize`

### Scrolling attributes

- `scrollingdirection`
- `scrollbarthickness`
- `scrollbarcolor`
- `scrollbartransparency`
- `canvassize`
- `canvasposition`
- `canvasautomaticsize`
- `elasticbehavior`
- `verticalscrollbarposition`

### Misc attributes

- `backgroundcolor`
- `backgroundtransparency`
- `bordercolor`
- `borderpixelsize`
- `autobuttoncolor`
- `animated`
- `circular`
- `easingdirection`
- `easingstyle`
- `tweentime`
- `scale`
- `props`

## Value Formats

### Boolean

Accepted values:

- `true`
- `false`
- `1`
- `0`
- `yes`
- `no`

### Color

Accepted formats:

- hex: `#2563eb`
- simple names: `white`, `black`, `red`, `blue`, `green`, `gray`, `grey`, `orange`, `purple`, `yellow`
- rgb: `255,255,255`

### UDim

```html
padding="0,12"
```

### UDim2

```html
size="1,-24,0,48"
position="0.5,-200,0.5,-120"
```

### Vector2

```html
anchorpoint="0.5,0.5"
gradientoffset="0,0"
```

### Rect

```html
slicecenter="10,10,90,90"
```

### ColorSequence

```html
gradientcolor="0:#0f172a|1:#2563eb"
```

### NumberSequence

```html
gradienttransparency="0:0|1:0.4"
```

## Fonts

Examples:

- `font="Gotham"`
- `font="GothamBold"`
- `font="GothamMedium"`

Accepted aliases:

- `GothamSemibold`
- `Semibold`

## `props`

Use `props` to pass direct Roblox-style properties in a compact format.

```html
<input
	props="TextWrapped:true; ClearTextOnFocus:false; TextXAlignment:Left"
/>
```

Use `props` when:

- you want a property not covered by a short alias
- you want to set several exact properties quickly

## Responsive UI

RTML supports responsive sizing and centered windows.

Useful attributes:

- `center="true"`
- `centeroffset="x,y"`
- `autosizewindow="true"`
- `desktopsize`
- `tabletsize`
- `mobilesize`
- `breakpointmobile`
- `breakpointtablet`
- `fitcontent`
- `contentfit`
- `scrolltofit`
- `minsize`
- `maxsize`

Example:

```html
<window
	center="true"
	autosizewindow="true"
	desktopsize="0,960,0,620"
	tabletsize="0,820,0,560"
	mobilesize="1,-18,1,-18"
	maxsize="1120,760"
	minsize="420,420"
/>
```

### `fitcontent`

Accepted values:

- `true`
- `both`
- `xy`
- `x`
- `y`

Example:

```rtml
<vstack size="1,0,0,0" fitcontent="y" gap="0,12">
```

## Dragging

Make a window or element draggable with:

- `dragging="true"`

Mark a specific area as a drag handle with:

- `draghandle="true"`
- `draghitbox="true"`

## Tabs

RTML has a built-in tab system.

Use:

- `tabbutton`
- `tabpanel`

Supported tab attributes:

- `tabgroup`
- `tabvalue`
- `tab`
- `default="true"`
- `defaulttab`
- `activestyle`
- `inactivestyle`

Example:

```html
<tabbutton
	tabgroup="main"
	tabvalue="settings"
	default="true"
	text="Settings"
	activestyle="backgroundcolor:#2563eb; textcolor:#ffffff;"
	inactivestyle="backgroundcolor:#111827; textcolor:#d7e3f7;"
/>

<tabpanel tabgroup="main" tabvalue="settings">
	<section title="Settings">
		<textlabel text="This panel is active." />
	</section>
</tabpanel>
```

## `onclick`

You can attach Luau directly to clickable elements:

```html
<button
	text="Click me"
	onclick="
context.state.clicks = (context.state.clicks or 0) + 1
instance.Text = 'Clicks: ' .. context.state.clicks
print('Clicked', instance.Name)
	"
/>
```

Inside `onclick`, you can use:

- `instance`
- `self`
- `context`

## `<script>`

Use `<script>` for larger logic.

Example:

```html
<script>
local input = context.get("nameInput")
local label = context.get("nameLabel")

input:GetPropertyChangedSignal("Text"):Connect(function()
	label.Text = input.Text
end)
</script>
```

Inside `<script>`, you can use:

- `context`

## `context`

RTML scripts expose a shared `context` object.

Useful helpers:

- `context.get(id)`
- `context.findClass(className)`
- `context.set(id, props)`
- `context.show(id)`
- `context.hide(id)`
- `context.setTab(group, value)`
- `context.getTab(group)`
- `context.state`

Examples:

```lua
local button = context.get("saveButton")
button.Text = "Saved"
```

```lua
context.set("title", {
	Text = "Updated",
	TextColor3 = Color3.fromRGB(255, 255, 255),
})
```

```lua
context.state.counter = (context.state.counter or 0) + 1
```

## Built-In Components Reference

### `window`

A modern window container.

Common attributes:

- `title`
- `subtitle`
- `description`
- `gap`
- `headergap`
- `bodytopgap`

Example:

```html
<window
	id="mainWindow"
	title="My Window"
	subtitle="Fast to build"
	desktopsize="0,960,0,620"
	tabletsize="0,820,0,560"
	mobilesize="1,-18,1,-18"
/>
```

### `section`

A grouped content block.

Common attributes:

- `title`
- `description`
- `subtitle`
- `gap`

Example:

```html
<section title="Audio" description="Sound controls">
	<slider id="volume" label="Volume" min="0" max="100" value="80" />
</section>
```

### `toggle`

Attributes:

- `id`
- `label`
- `value`
- `checked`
- `texton`
- `textoff`
- `onchanged`

Example:

```html
<toggle
	id="blurToggle"
	label="Enable Blur"
	value="false"
	texton="Enabled"
	textoff="Disabled"
	onchanged="
print('Toggle value:', value)
	"
/>
```

### `slider`

Attributes:

- `id`
- `label`
- `min`
- `max`
- `step`
- `value`
- `onchanged`

Example:

```html
<slider
	id="opacitySlider"
	label="Opacity"
	min="0"
	max="100"
	step="5"
	value="75"
	onchanged="
print('Slider:', currentValue)
	"
/>
```

### `dropdown`

Attributes:

- `id`
- `label`
- `options="A|B|C"`
- `value`
- `onchanged`

Example:

```html
<dropdown
	id="themeDropdown"
	label="Theme"
	options="Aurora|Ember|Emerald"
	value="Aurora"
	onchanged="
print('Theme:', currentValue)
	"
/>
```

### `colorpicker`

Attributes:

- `id`
- `label`
- `colors="#2563eb|#10b981|#ef4444"`
- `value`
- `onchanged`

Example:

```html
<colorpicker
	id="accentPicker"
	label="Accent"
	colors="#2563eb|#38bdf8|#8b5cf6|#10b981"
	value="#2563eb"
	onchanged="
print('Accent:', currentValue)
	"
/>
```

### `keybindinput`

Attributes:

- `id`
- `label`
- `value`
- `default`
- `onchanged`

Example:

```html
<keybindinput
	id="menuKey"
	label="Open Menu"
	value="RightShift"
	onchanged="
print('Keybind:', currentValue)
	"
/>
```

### `searchablecombobox` / `combobox`

Attributes:

- `id`
- `label`
- `options`
- `value`
- `placeholder`
- `listheight`
- `onchanged`

Example:

```html
<searchablecombobox
	id="weaponPicker"
	label="Weapon"
	options="Sword|Bow|Axe|Staff|Dagger"
	value="Sword"
	placeholder="Search..."
	onchanged="
print('Selected:', currentValue)
	"
/>
```

### `datatable` / `datagrid`

Attributes:

- `id`
- `title`
- `label`
- `columns="Player|Wins|Rating"`
- `rows="Nova,128,2440|Kairo,114,2315"`
- `rowheight`

Example:

```html
<datatable
	id="scoreTable"
	title="Arena Results"
	columns="Player|Wins|Rating"
	rows="Nova,128,2440|Kairo,114,2315|Lyra,101,2242"
/>
```

### `modal` / `dialog`

Attributes:

- `id`
- `title`
- `description`
- `subtitle`
- `visible`
- `panelsize`

Example:

```html
<modal
	id="confirmModal"
	title="Confirm"
	description="Are you sure?"
	visible="false"
>
	<button id="confirmYes" text="Yes" />
</modal>
```

### `tooltip`

Attributes:

- `id`
- `for`
- `target`
- `text`

Example:

```html
<tooltip
	id="saveTip"
	for="saveButton"
	text="Saves your changes."
/>
```

### `popover`

Attributes:

- `id`
- `for`
- `target`
- `title`
- `text`
- `description`

Example:

```html
<popover
	id="moreInfo"
	for="detailsButton"
	title="Details"
	text="Extra contextual information."
/>
```

### `circularprogress` / `progresscircle`

Attributes:

- `id`
- `label`
- `title`
- `min`
- `max`
- `value`

Example:

```html
<circularprogress
	id="progressCircle"
	label="Completion"
	min="0"
	max="100"
	value="78"
/>
```

### `virtuallist` / `virtualizedlist`

Built for larger lists.

Attributes:

- `id`
- `title`
- `label`
- `items`
- `rows`
- `rowheight`
- `overscan`

Example:

```html
<virtuallist
	id="leaderboard"
	title="Leaderboard"
	items="Player 1 - 5000|Player 2 - 4980|Player 3 - 4920"
	rowheight="34"
	overscan="4"
/>
```

## Direct Roblox UI Tags

You can also use Roblox-style helper tags directly:

```html
<frame size="0,220,0,64" backgroundcolor="#111827" borderpixelsize="0">
	<uicorner cornerradius="0,14" />
	<uistroke strokecolor="#38bdf8" stroketransparency="0.4" thickness="1" />
	<uipadding padding="0,12" />
	<textlabel size="1,0,1,0" backgroundtransparency="1" text="Styled frame" />
</frame>
```

You can also create these automatically through attributes on the parent element:

```html
<button
	text="Auto Styled"
	cornerradius="0,14"
	strokecolor="#38bdf8"
	stroketransparency="0.5"
	thickness="1"
	gradientcolor="0:#1e293b|1:#2563eb"
	gradientrotation="90"
/>
```

## Best Practices

### 1. Give ids to anything scripts need

```html
<button id="saveButton" text="Save" />
```

### 2. Use classes for reusable appearance

```html
<button class="primaryButton" text="Save" />
<button class="primaryButton" text="Confirm" />
```

### 3. Use `section` to group controls

```html
<section title="Audio">
	<slider id="music" label="Music" />
</section>
```

### 4. Use `<script>` for larger logic

`onclick` is best for small actions.

`<script>` is better for:

- multiple elements
- event wiring
- tab logic
- theme logic
- shared state

### 5. Use `fitcontent="y"` for content stacks

```html
<vstack size="1,0,0,0" fitcontent="y" gap="0,12">
```

## Full Menu Example

```html
<style>
.tabButton {
	size: 1,0,0,46;
	backgroundColor: #111827;
	textColor: #ffffff;
	font: GothamBold;
	fontSize: 16;
	cornerRadius: 0,14;
	paddingLeft: 0,14;
	textXAlignment: Left;
}
</style>

<screenui resetonspawn="false" ignoreguiinset="false">
	<window
		id="menu"
		title="RTML Menu"
		subtitle="A modern settings window"
		desktopsize="0,980,0,620"
		tabletsize="0,860,0,560"
		mobilesize="1,-18,1,-18"
	>
		<hstack size="1,0,1,0" gap="0,18">
			<vstack size="0,200,1,0" gap="0,10">
				<tabbutton class="tabButton" tabgroup="main" tabvalue="general" default="true" text="General" />
				<tabbutton class="tabButton" tabgroup="main" tabvalue="visual" text="Visual" />
			</vstack>

			<frame size="1,-218,1,0" backgroundtransparency="1">
				<tabpanel tabgroup="main" tabvalue="general">
					<section title="General">
						<toggle id="blurToggle" label="Enable Blur" value="true" />
						<keybindinput id="menuKey" label="Open Menu" value="RightShift" />
					</section>
				</tabpanel>

				<tabpanel tabgroup="main" tabvalue="visual">
					<section title="Visual">
						<dropdown id="theme" label="Theme" options="Aurora|Ember|Emerald" value="Aurora" />
						<colorpicker id="accent" label="Accent" value="#60a5fa" />
					</section>
				</tabpanel>
			</frame>
		</hstack>

		<script>
local theme = context.get("theme")
local accent = context.get("accent")

print("Theme value:", theme:GetAttribute("Value"))
print("Accent value:", accent:GetAttribute("Value"))
		</script>
	</window>
</screenui>
```

## Learn Faster

If you are new to RTML, start in this order:

1. Learn the basic tags.
2. Learn `<style>`.
3. Learn `window`, `section`, `dropdown`, `slider`, and `toggle`.
4. Learn `onclick`.
5. Learn `<script>` and `context`.
6. Learn tabs and responsive sizing.
7. Have a looot of fun!
