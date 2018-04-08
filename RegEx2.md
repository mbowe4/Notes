# RegEx
- not all systems support flags(like case sensitivity)
- spaces matter!
- `*` = 0 or more characters
- `+` = 1 or more characters
- `(t|T)he` -> returns the or The
- ? = 0 or 1 occurences of the preceeding token
- `\b(T|t)he\b` = only returns "the" or "The" but not "there"


### Character classes
- `[abc]` = matches 'a' or 'b' or 'c'

`^\w\|\w\|\w$` = a|b|c   

`^public.+\w+\(.*\)$` = public static void()

### Quirks
- java regex escape sequences must be double escaped `\\d`
- to find backslash in java `\\\\`

### Methods and Classes
- replaceAll, replaceFirst, split and matches
- `Pattern` objects represent compled regular expressions 

```java
Pattern thePatter = Pattern.compile(regexStr);
```
   
      
- Matcher objects provide info about matching a regex on to an input

```java
Matcher m = thePattern.matcher(inputStr);
```
   
   
### Backtracking
- beware of *catastrophic backtracking*: `.*`

### Lazy quantifiers
- consume smallest possible sequence to achieve a match