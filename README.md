MooColorPicker
==============

A MooTools plugin for choosing a color from a list of square boxes.

![Screenshot](http://github.com/lorenzos/MooColorPicker/raw/master/Graphics/logo.png)


How to use
----------

JS sample:

	// Create the color picker with some colors
	var cp = new MooColorPicker($('cp'), {
		colors: [
			"#001B2E", "#479096", "#4A7390",
			"#036564", "#4F2634", "#B6BFAD", "#2D0D10"],
		defaultColor: 3 // Select #4A7390
	});

	// Display current color
	$('current_color').set('html', 'Current color is: ' + cp.getCurrentColor());
	cp.addEvent('change', function(col, box) {
		$('current_color').set('html', 'Current color is: ' + col);
	});
	
HTML code:

	<div id="cp">Color picker container</div>
	<div id="current_color">No color selected</div>
	
CSS rules:
	
	div.moocolorcheckbox {
		width: 24px;
		height: 24px;
		margin: 4px 2px 4px 0px;
		border: 1px solid white;
		border-radius: 4px;
		-moz-border-radius: 4px;
		-moz-box-shadow: 1px 1px 5px #cccccc;
		overflow: hidden; }

	div.moocolorcheckbox_selected {
		width: 32px;
		height: 32px;
		margin: 0px 2px 0px 0px;
	}


Docs
----------

Implements:
	Options, Events

Syntax and options:
	var cp = new MooColorPicker(container, options);
	container: The <div> container (will be empty).
	options - (object, optional) Initial options for the class.
		colors: An array of strings, like ["#0123456", "#789ABC"].
		defaultColor: Index of preselected color (default -1, none).

Events:
	change(color, item): 
		Fires when selcted color is changed. Color is selected color, item is the selected color <div> box.
	mouseenter(div), mouseleave(div):
		Fires when mouse over a color <div> box.