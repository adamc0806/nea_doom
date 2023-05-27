# DOOM re-write coding style


This is a short document that details the coding style for this DOOM ripoff/rewrite/improvement(?).
Coding style differs between people, but I prefer the following, to make it easy to maintain.


# 1 - Indentation


Tabs are 8 characters; indentations are also 8 characters. This is a new change to my style, I chose to move from 4 to 8 for the following reasons:
	- Blocks of control are defined clearly (start and end)
		- You might say that it's difficult to see on smaller screens
			- However, if you have that many indentations then either you're writing AI, or your code needs fixing.


Nested code blocks should be as follows:

```c
	if (expression) {
		do_thing();
		do_other_thing();
		if (other_expression){
			do_another_thing();
			// insert comment
		}
	}
```

A maximum of 2 statements should be on a single line, any more should be on seperate lines:

```c
	if (expression) do_this(); do_that;
			do_thing(); // third expression is on new line
```

Alternatively, multiple statements after a condition that contain more than 5 statements should ideally be included inside curly braces {}.

This is consistent for the following:
	- if/switch statements
	- loops
	
If a function or procedure is declared, always include a maximum of 1 newline in between the declaration and statements. For example:

```c
	void function(){
	
		do_this();
		do_that();
		if (expression){
			function(); // Comment thing 
		}
	}
```

If an Object-Oriented language is used in the project, classes should also follow the same conventions as functions/procedures.


# 2 - Comments

Comments should be used where required, and not on every line. My GCSE project required us to comment every single line. For whatever reason, AQA said so. I argued that it was total bullsh*t and there was no programmer with half a brain who does that, but that didn't work.
Comments should be formatted with a space after whatever character(s) is/are used to denote a comment.
Comments that require multiple lines should be formatted as follows

```c
	// Single line comment
	/*
	 Multi-line
	 Comment
	 */
```

At the beginning of a file, there should be a short, multi-line comment block that denotes the following:
	- Author/Authors
	- Required license(s) for the file/project
	- Time & Date of creation
	- Time & Date of most recent edit
	- What the file does and where it is used

Classes & Functions/Procedures should contain a short, single, or, if required, a shrot multi-line comment detailing what the function is used for.

Where new code needs writing, a comment should be used, starting with TODO: 
Where there is a code bug or broken code, a comment should be used, starting with FIX:
Where the performance of a block or piece of code is as high as possible, a comment using PERF: should be used.
Where a piece of code looks poorly written, or written just to compile the code with no errors, use HACK: 
Where a note to other developers is required, use NOTE: 
To denote a warning, use WARNING: 



# 3 - Variable, constant and function naming conventions

The preferred naming convention for variables is as follows:
	- Keep names concise, a variable like TemporaryCounter should be shortened to tmp, at a minimum temp_count.
	- Use SNAKE CASE. I don't know why, but I prefer it and use everywhere.
	- global variables and functions should be named in a descriptive way.

At the beginning of a function/procedure, variables and constants should be defined, constants first, variables after, leave a blank line between constants and variables for increased clarity between what changes and what doesn't.
If it is not clear what is a constant and what is not, the keyword `const` will tell you.


# End Comments

This is the end of this document, when contributing to code in projects that contain specified coding styles, please follow the formats specified.
Segmentation Fault (Core Dumped) :)
