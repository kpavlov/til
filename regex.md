[Home](../)

Useful Regexp Patterns
======================

# Wrapping text in double quotes

Adding double quotes around line. Honoring existing single/double quotes:

    Abc -> "Abc"
    "Abc" -> "Abc"
    'Abc' -> "Abc"
    'Abc" -> "Abc"
    "Abc' -> "Abc"

Regexp: `^["']?(.*[^'"])["']?$` Replacement: `"$1"`. [test it](https://regex101.com/r/5SthsI/1)

Javascript:
~~~javascript
const regex = /^["|']?(.*[^'"])["']?$/gm;
const str = `This is an sample text for demonstrating the use of this tool.
"This is an sample text for demonstrating the use of this tool.
"This is an sample text for demonstrating the use of this tool.'
'This is an sample text for demonstrating the use of this tool."
"This is an sample text for demonstrating the use of this tool."`;
const subst = `"$1"`;

// The substituted value will be contained in the result variable
const result = str.replace(regex, subst);

console.log('Substitution result: ', result);
~~~

Java:
~~~java
import java.util.regex.Matcher;
import java.util.regex.Pattern;

final String regex = "^[\"|']?(.*[^'\"])[\"']?$";
final String string = "This is an sample text for demonstrating the use of this tool.\n"
	 + "\"This is an sample text for demonstrating the use of this tool.\n"
	 + "\"This is an sample text for demonstrating the use of this tool.'\n"
	 + "'This is an sample text for demonstrating the use of this tool.\"\n"
	 + "\"This is an sample text for demonstrating the use of this tool.\"";
final String subst = "\"$1\"";

final Pattern pattern = Pattern.compile(regex, Pattern.MULTILINE);
final Matcher matcher = pattern.matcher(string);

// The substituted value will be contained in the result variable
final String result = matcher.replaceAll(subst);

System.out.println("Substitution result: " + result);
~~~
