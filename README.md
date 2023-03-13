# Roxymus Coding-standard

Version 0.0.1

## #define Guard
All header files should have #define guards to prevent multiple inclusion. The format of the symbol name should be _<FILE>_H_.

The `#endif` should be marked with an comment of format `// _<FILE>_H_`

Example:

```C++
#ifndef _FILE_NAME_H_
#define _FILE_NAME_H_

// code

#endif  // _FILE_NAME_H_
```
## White space

Never put trailing white space at the end of a line. Ever.
Change your editor to remove trailing white space after save.

### Indent
Indent only to distinguish scopes, so after a `{`.
Indent the scopes using tabs, but for anything that you want to move more, use spaces.
This is to ensures that allignments are always kept even when changing tab lenghts in a editor.
```C++
void function(){
	unsigned int i;
	// Hey       ^ look at here. I wanted to have the arrow always at the i.
	// The white space before // are tabs, the text uses _only_ spaces.
}
```
Another thing, anyting below a label is _not_ a new scope, so no indentation needed.
Do
```C++
switch(var){
	case label1:
	//code
	break;
	case label2:
	//code
	break;
};
```
don't
```C++
switch(var){
	case label1:
		//code
		break;
	case label2:
		//code
		break;
};
```
You may put a label one tab back, which makes it more readable.
Better:
```C++
switch(var){
case label1:
	//code
	break;
case label2:
	//code
	break;
};
```
## Names
For classes, functions, variables, anything non-precompler, do not use _ for seperation of words, but use Capitialized letters.
Types start with a capital letters, eg `class Name` `enum Numerate{//...` etc.
Instances, members and functions do not start with capital letters, such that:
```C++
class MyClass{
	\\ stuff
};

// Now an instance
MyClass myClassInstance;
```
This way we know if a keword is related to a instance, or type.

### private members
A private member starts with `_`. The idea is that a user of a library rarely has to know about private members, and never can have a confict when extending members himself. Bassicly, everything below `private:` is for an maintainer 'as long as it is not relevant, I do really care what is there'.
```C++
class MyClass{
public:
	void function1();
private:
	void _function2();
};

// Now an instance
MyClass myClassInstance;
```
## And Remember
Feel free to add, change, and fix.
