# CoffeeScript

The main aim of this style-guide is to get the best possible readability
(and not writability).

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](http://pretty-rfc.herokuapp.com/RFC2119).


## Naming Conventions

- Names SHOULD be descriptive
- camelCase MUST be used for naming objects, functions, and instances
- PascalCase MUST be used for classes and constructor names


## Whitespace

- Tabs MUST be used for indentation
- It's RECOMMENDED to equal the indentation of a tab to 4 spaces
- You MAY use, however, a different number while working on the code to match your style preferences. Other common numbers of spaces are 2 and 8.
- There MUST be no trailing whitespace characters
- An empty newline MUST be placed at the end of a file
- Invisibles SHOULD be displayed during coding to reduce the likelihood of whitespace mistakes
- Tabs and spaces MUST NOT be mixed


## Multi-line Statements

- Lines MUST not me longer than 80 characters (counting tabs as 4 spaces)
- When a statement is too long to fit on one line,
	line breaks MUST occur after an operator


## Commas

- Commas SHOULD be omitted were possible

		foo =
			bar: 1
			baz: 2

	instead of

		foo =
			bar: 1,
			baz: 2

	and

		fruits = [
			apple
			melon
			pear
		]

	instead of

		fruits = [
			apple,
			melon,
			pear
		]

- Inline commas MUST be followed by one space character

		colors = ['green', 'yellow', 'red']

	instead of

		colors = ['green','yellow','red']


## Relational Operators

- `is` MUST be used over `==`
- `isnt` MUST be used over `!=`
- `or` MUST be used over `||`
- `and` MUST be used over `&&`


## Comments

- There MUST be a space between `#` and the first character of the comment
- The first character of the comment MUST be uppercase
- Single line comments MUST be placed on a newline above the subject of the comment
- One empty line SHOULD be put before a single line comment
- Obscure code SHOULD be commented but not obvious things
- `# FIXME: ` MAY be used to annotate problems
- `# TODO:` MAY be used to capture issues which need to get solved


## Strings

- Single Quotes MUST be used for simple strings except
	the string contains an interpolation (e.g. `"#{name}"`)

		test = 'foo'

	instead of

		test = "foo"



## Functions

- Parentheses for an empty argument list MUST be omitted

		logTest = ->
			console.log 'test'

	instead of

		logTest = () ->
			console.log 'test'

- Fat arrows MUST only be used when necessary

		logTest = ->
			console.log 'test'

	instead of

		logTest = =>
			console.log 'test'


### Chaining

- Method chains with more than 2 method calls must be wrapped and indented.

		$('#items')
			.find('.selected')
			.highlight()

	instead of

		$('#items').find('.selected').highlight()

- Sub-properties MUST not be wrapped

		person.address.country
			.toUpperCase()
			.split('')

	instead of

		person
			.address
			.country
			.toUpperCase()
			.split('')


- Methods SHOULD return `@` to enable method chaining


## Type Casting

- To string: `String(123)`
- To number: `Number('123')`
- To boolean: `Boolean(1)`


## General

You MAY (when it's absolutely necessary)
differ from any rules of this guide to increase the performance.
You MUST, however, explain the reasons for not sticking to a rule in a comment.


## Framework specific

### jQuery

- jQuery object variables MUST be prefixed with a `$`

		$form = $ '#myForm'

	instead of

		form = $ '#myForm'

- Lookups MUST be cached

		$form = $ '#form'

		$form.css {
			'background-color': 'pink'
		}

		# …

		$form.hide()

	instead of

		$('#form').css {
			'background-color': 'pink'
		}

		# …

		$('#form').hide()
