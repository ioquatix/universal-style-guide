# Style Guide

This is a style guide which I follow across almost all my projects and for all languages.

## Indentation

Use tabs everywhere except when the language/system doesn't support it (e.g. YAML). It can be configured to your personal preference, it works correctly in every editor without any changes, and is uniform over all programming languages.

### Trailing Whitespace

Trailing whitespace on empty lines is fine, i.e. blank likes with indentation for the current scope. Generally avoid trailing whitespace on the end of lines of code.

### Terminals

Use the tabs command to configure your preferred tab width in a terminal:

```bash
tabs -4
```

### Websites

Use responsive `tab-width` so that code width is minimized on mobile devices.

## Alignment

Don't. Aligning code causes edit-amplification and is hugely subjective. Use hard wrapping and indentation to make code readable.

```ruby
# Prefer:
invoke_method(
	this,
	that
)

# Rather than:
invoke_method(this,
              that
             )
```

## Hard Wrapping

Indenting data structures across multiple lines for readability is fine. Use tab indentation for nested scopes.

```ruby
user = {
	name: "Samuel",
	country: "New Zealand",
}
```

Prefer trailing commas where possible.

## Abbreviations

Don't. It's difficult for non-native speakers and everyone abbreviates things differently which makes code hard to read.

## Constants

Use title-case or upper-case where appropriate.

### Function Names

Use snake-case.

### Variable Names

Use snake-case.

## Scopes

### Brackets

Don't add extra space to the inside of brackets, e.g. prefer `{x: 10}` over `{ x: 10 }`.

Generally prefer a single space between keywords and brackets, e.g.

```c++
// Prefer:
if (x < 10) {
}

// Rather than:
if(x<10){
	
}
```

### Braces

#### Control Flow

Prefer trailing braces for control flow:

```c++
// Prefer:
if (x < 10) {
}

// Rather than:
if (x < 10)
{
	
}
```

#### Namespaces

Prefer braces on next line for namespace, classes, functions, etc:

```c++
namespace X
{
	class Y
	{
	public:
		void z()
		{
			if (x < 10) {
				
			}
		}
	}
}
```
