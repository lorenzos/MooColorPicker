MooColorPicker
==============

A MooTools plugin for choosing a color from a list of square boxes.

![Screenshot](http://github.com/lorenzos/MooColorPicker/raw/master/Graphics/logo.png)


How to use
----------

JS example:

	// Create the color picker with some colors
	var cp = new MooColorPicker($('cp'), {
		colors: [
			"#001B2E", "#479096", "#4A7390",
			"#036564", "#4F2634", "#B6BFAD", "#2D0D10"],
		defaultColor: 3 // Select #4A7390
	});

	// Display current color
	$('current_color').set('html', 'Current color is: ' + cp.getCurrentColor());
	$('current_color').setStyle('border-bottom-color', cp.getCurrentColor());
	cp.addEvent('change', function(col, box) {
		$('current_color').set('html', 'Current color is: ' + col);
		$('current_color').setStyle('border-bottom-color', col);
	});