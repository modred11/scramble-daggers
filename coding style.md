# this file defines the coding style for this project

(some of these rules were derived from https://github.com/copycopter/style-guide)

## General

* Try to keep lines under 80 characters.
* Delete, don't comment out.
* At this stage in the project, prefer *simple* *understandable* solutions over *optimal* solutions.

## Naming conventions

* use CamelCase for multi-word identifiers
	* all identifiers should start with a lowercase character, 
	* except for entities and globals defined in core (like Sa and Rng).
	* acronyms should be lowercase (rng not RNG)
* when *declaring* a global variable, do so explicitly using `window.`
* do not use `window.` when *referencing* a global variable.
```jaavascript
window.map = window.map || {};

map.height = generateHeight( worldWidth, worldDepth );
```

## Whitespace

* two-space tabs. Tab characters, not spaces.
* opening scope brackets should be on the same line, like so:
```javascript
var x = function() {
	if (something) {
		console.log("stuff");
	}
};
```
* single line scopes should generally not have brackets,
	* both of these styles are acceptable:
```javascript
if (thing) stuff();

if (thing)
	stuff();
```
* parallel lines should be visually parallel
	* (vertically align tokens on consecutive lines, as in:)
```javascript
(function() {
	start = start.divide(h("1 block"));
	line  = line .divide(h("1 block"));
})();
```
* use spaces to do so,
* do not do so if the two lines have different indentations, as in this case:
```javascript
x(function(time, y) {
	x(function(time, y) {
		razzelTazzleMan(time, y);
	});
});
```
* Don't use an empty line at the beginning or end of methods, blocks or conditionals
* Do use one empty line *between* methods, blocks and conditionals in the same scope.
* Do not use more than one empty line anywhere.
```javascript
var rawr = prompt();

if (rawr) {
	console.log(rawr);
	
	rawr = [5, 3, 2].reduce(function(x, y) {
		return x + y*rawr;
	}, 0);
	
	console.log(rawr);
}

if (!prompt() || !rawr) 
	console.log("super rawr!");
```

## Comments

Comments come in three 'sizes':

```javascript
//-----------------------------------------------------------------------------
// Heading 1
//-----------------------------------------------------------------------------

//
// Heading 2
//

// Heading 3
```

* Do not use any other style of comment (external libraries may use alternate forms).
* Comments should always be on a line of their own.
	* (so, not on the same line as some code.)
* always put one space after the `//` and before the text.
* Heading sizes 1 and 2 should have an empty line before and after them
	* Unless they're at the beginning or end of a scope block.

Use comments to:
* group 'paragraphs' of code into 'chapters'
* explain complex, counter-intuitive, or obscure lines of code (such as the use of `Object.defineProperty()` or `RandomSource.getRandomValues()`)

Multi-line forms of heading 3 are allowable:
```javascript
// this isn't really a monkeypatch,
//   it's a utility that *enables* monkeypatching
```

The additonal lines should be indented (have not formulated opinion on whether the indentation should be with spaces or tabs, currently using 2 spaces).
