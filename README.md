# Universal Style Guide

This is a style guide which I follow across almost all my projects and for all languages. It's not a strict guideline, but serves to provide a general guideline for how to write code that requires a minimum number of subjective decisions in order to write, and is easily readable in a variety of different contexts.

## Motivation

I've been writing code for well over 20 years. I've seen a lot of different styles, and for my own code I wanted something which I could use across all languages. While most languages (and/or projects) have unique and different style guides, I tend to follow this universal style guide by default.

In addition, I'm aware of the wide spectrum of programmers and I prefer choices which make it both easy to read and write consistently across a wide range of languages. I've personally taught blind programmers, and work regularly with people who's native language is not English.

## General Code

### Indentation

Use tabs everywhere except when the language/system doesn't support it (e.g. YAML). It can be configured to your personal preference, it works correctly in every editor without any changes, and is uniform over all programming languages.

*Accessibility*: Screen-readers can read off the number of tabs at the start of the line which translates directly to indentation level. As visually impaired programmers navigate up and down lines, they can follow the indentation level very easily.

#### Trailing Whitespace

Trailing whitespace on empty lines is fine, i.e. blank likes with indentation for the current scope. Generally avoid trailing whitespace on the end of lines of code.

#### Terminals

Use the tabs command to configure your preferred tab width in a terminal:

```bash
tabs -4
```

#### Websites

Use responsive `tab-width` so that code width is minimized on mobile devices.

### Alignment

Don't. Aligning code causes edit-amplification and is hugely subjective. Use hard wrapping and indentation to make code readable.

```ruby
# Prefer:
invoke_method(
	some + complicated + expression,
	->(x){x * 10}
)

# Rather than:
invoke_method(some + complicated + expression,,
              ->(x){x * 10}
             )
```

*Accessibility*: Screen-readers can read off one line at a time, so putting arguments on separate lines can make it easier to navigate and understand code.

#### Hard Wrapping

Indenting data structures across multiple lines for readability is fine. Use tab indentation for nested scopes.

```ruby
user = {
	name: "Samuel",
	country: "New Zealand",
}
```

Prefer trailing commas where possible. It makes it easier to move lines around.

### Abbreviations

Don't. It's difficult for non-native speakers and everyone abbreviates things differently which makes code hard to read.

### Constants

Use title-case or upper-case where appropriate.

#### Function Names

Use snake-case.

#### Variable Names

Use snake-case.

### Scopes

#### Brackets

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

#### Braces

##### Control Flow

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

##### Namespaces

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

### Comments

Use annotations if possible.

#### Hard Wrapping

Don't hard wrap comment paragraphs.

*Accessibility*: Screen-readers don't always correctly handle paragraphs with hard wrapped lines.

#### Definitions

Annotations for general namespaces, classes, functions, etc should be full paragraphs.

#### Implementations

Annotations for implementation behavior should be short statements ending in a colon.

```c++
int main(int argc, char ** argv) {
	// Greet the user:
	std::string name;
	std::cout << "What is your name? ";
	std::getline(std::cin, name);
	std::cout << "Hello " << name << ", nice to meet you." << std::endl;
	
	// If the user's name is too short, we fail:
	if (name.size() < 4) {
		return -1;
	}
	
	return 0;
}
```

Group lines which logically form sub-programs within a function, and consider adding an annotation before each one.

*Accessibility*: As users move between different segments of a function, it can be helpful to know what are the high level process.