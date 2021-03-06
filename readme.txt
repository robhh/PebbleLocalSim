[PebbleLocalSimulator]
Version: 0.2 BETA

[Overview]
This project is an extension to the PebbleSDK1.2 which allows you to build and run your pebble
applications on your computer.

[Installation and Use]
For OS specific manuals see linux.txt/windows.txt/mac.txt
The simulator has several key commands you can use:
	[Arrow up]	Pebble button: Up
	[Arrow down]	Pebble button: Down
	[Enter]		Pebble button: Select
	[Backspace]	Pebble button: Back
	[F1]		Changes the color of the drawn pebble
	[F2]		Toggles the lens effect 
	[F3]		Switches between 24H and 12H mode
	[F12]		Saves a screenshot in <simulator>\simdata\screenshots\

[Non-implemented features]
I tried to put as much from the original SDK into the first release, but there are some things
that are not implemented yet:
	PebbleAppTimerHandler		- Because I think this is a rather minor feature
	AppTimerHandle
	RotBmp(Pair)Container		- The SDK documentation marks this as "Deprecated", but
	(and their layer types)		  presumably this will be in the next release
	Dictionary			- Because this seems to be used only for mobile phone 
					  communication
	AppMessage			- Because this is hard to implement into a simulator, I
	AppSync				  would like to ask you, how this should be implemented
	Logging				- This will be in the next release
	ScrollLayer			- This will be in one of the next releases
	MenuLayer			
	SimpleMenuLayer
	NumberWindow
Except from these,  all other features should be implemented

[Compability]
The most important feature for this simulator is compability. You should be able to leave your
source code like it is for your watch, but there are a few problems:
	- Non-implemented features. Very simple. I try to implement all features left as soon
	  as possible. At the moment this simulator is my only possibility to actual code for
	  pebble, so it is in my own interest to work as quick and as best as I can.
	- Bugs. This simulator has lots of code, lots of unverified or not enough verified code
	  and there are probably lots of little bugs crawling inside of it. This is an
	  important reason why I release it now. I can not find all bugs but with your help
	  the search will be much easier.
	- Documentation. Even though there is much more than I expected, I can not make sure that
	  all functions behave like their original ones. If you find any differences, please tell
	  then to me.
	- Fonts. The fonts that are most common on the pebble are Bitham (renamed from Gotham) and
	  Gothic. I presume that they are commercial fonts which could be extracted from the firm
	  ware, but I think this would be illegal. In the case that you have these fonts (as True
	  TypeFont) you can replace them, as I filled the missing fonts up with Droid Serif and
	  Roboto which have a free license (you can find the fonts and their license text in the
	  directory local/simdata/systemFonts).
	  The problem with these fonts are, that they are wider than the original ones, so some
	  applications have graphical bugs because of this.
	  In the most sample watches, where this was a problem, it could be solved with extending
	  the layer frame with and reducing the margin.
I tested the sample watches from the SDK to detect these problems:
	big_time	[No problems]
	brains		[Doesn't work, because of RotBmpContainer)
	classio		[Minor font problem]
	drop_zone	[No problems]
	fuzzy_time	[No problems]
	just_a_bit	[No problems]
	ninety_one_dub	[No problems]
	onthebutton	[Minor font and margin problems]
	rumbletime	[No problems] [Vibrating not verified]
	segment_six	[No problems]
	simple_analog	[Minor graphic glitches with the analog part] [Text probably incorrect,
			no verification possibility for me]
	simplicity	[No problems]
	tic_tock_toe	[No problems]
Pretty good result, isn't it :)

[Compability between different operating systems]


[I want YOU!]
... to find:
	- bugs
	- suggestions
	- feedback
	- questions
and tell them to me. I will try to answer them all

[License]
The fonts are copyright by Google Inc. under Apache License, Version 2.0
The pebble pictures are copyright by Chaotic
The used libraries (see [Credits]) are copyright by their copyright holder (not me)
The actual simulator and the custom resource compiler are licensed by Helco (me) under GNU GPL v3

[Credits]
Many many thanks to:
Otto Greenslade (Chaotic) - for his pebble pictures
https://github.com/abl - for his empebble (which was original the basecode of this simulator, now
	nearly all code is rewritten)
The Pebble Team - for the amazing watch, the SDK and their long shipping procedure, which was the
	motivation to build this
Libraries that I used:
	SDL 1.2 (www.libsdl.org)
	SDL_ttf (http://www.libsdl.org/projects/SDL_ttf/)
	SDL_image (http://www.libsdl.org/projects/SDL_image/)
	SDL_gfx (http://www.ferzkopp.net/joomla/content/view/19/14/)
	JSMN (https://bitbucket.org/zserge/jsmn)
