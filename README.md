
# Basic Linux Commands

[Grep Command](https://github.com/nambinayagan/rhcsa_exam/blob/main/README.md#grep-command)
[Cut Command](https://github.com/nambinayagan/rhcsa_exam#cut-command-in-linux-cheatsheet "Cut Command")

### Grep Command
 Grep is a filter command, it is used to search a string in a given file.
 
 
 **Syntax:**
 
- grep [options] “string/pattern” file/files
	
- cat file | grep [options] “string/pattern”
	
- echo “some text” | grep [options] “string/pattern”
	

 **Basic options:** ```-i -w -v -o -n -c -A -B -C -r -l -h```

 
 ``` -i To ignore case for matching/searching
 
 -w To match a whole word
  
 -v To display the lines which are not having given string or text
 
 -o To print/display only matched parts from matched lines
 
 -n To display the matched line numbers
 
 -c To display matched number of lines
 
 -A To display N lines after match (grep –A 3 “string” file)
 
 -B To display N lines before match
 
 -C To display N lines around match
 
 -r To search under current directory and its sub-directory
 
 -l To display only file names
 
 -h To hide file names
 
 
 ```

 
 **Advanced Options:** -f -e and –E
 
 ```
 -f Takes search string/pattern from a file, one per line
 -e To search multiple strings/patterns 
 -E To work with patterns
 ```
 
 grep -E[options] “pattern” file/files
 
**Rules to create patterns:**

	 xy|pq Matches for xy or pq

	 ^xyz Matches for the lines which are starting with “xyz”

	 xyz$ Matches for the lines which are ending with “xyz”

	 ^$ Matches for the lines which are empty

	 \ To remove the special purpose of any symbol. Ex: \^ \$

	 . Matches any one character

	 \. Matches exactly with .

	 \b Match the empty string at the edge of word

	 ? The preceding character is optional and will be matched, at most, once.

	 * The preceding character will be matched zero or more times
	 * 
	 + The preceding character will be matched one or more times
	 + 
	 [xyz] Matches for the lines which are having x or y or z

	 [a-d] is equal to [abcd] Matched for the lines which are having a/b/b/d

	 [a-ds-z] is eqal to [abcdstuvwxyz]

	 ^[abc] Matches for the lines which are starting with a/b/c

	 [^abc] Matches for the lines which are not starting with a/b/c

	 {N} The preceding string matched exactly N times

	 {N,} The preceding string matched N or more times

	 {N,M} The preceding string matched at least N times but not more than M times

	[[:alnum:]] – Alphanumeric characters.

	[[:alpha:]] – Alphabetic characters

	[[:blank:]] – Blank characters: space and tab.


	[[:digit:]] – Digits: ‘0 1 2 3 4 5 6 7 8 9’.

	[[:lower:]] – Lower-case letters: ‘a b c d e f g h i j k l m n o p q r s t u v w x y z’.

	[[:space:]] – Space characters: tab, newline, vertical tab, form feed, carriage return, and space.

	[[:upper:]] – Upper-case letters: ‘A B C D E F G H I J K L M N O P Q R S T U V W X Y Z’.


___


### Cut Command

CUT command can be differentiated in three ways

- Based on [**BYTE**](https://github.com/nambinayagan/rhcsa_exam/blob/main/README.md#1byte-position) position   `         cut -b "byte"`

- Based on [**COLUMN**](https://github.com/nambinayagan/rhcsa_exam/blob/main/README.md#2column-position) position          `cut -c "column"`

- Based on [**FIELDS & DELIMETER**](https://github.com/nambinayagan/rhcsa_exam/blob/main/README.md#3field-based)        `cut -d "delimeter" -f "field"`



### 1)BYTE position

_Syntax:_

        cut -b 1                                #First byte

        cut -b 1,2                              #First and Second byte

        cut -b 1-                               #Display all bytes after first

        cut -b -3                               #Display all bytes before third


### 2)COLUMN position


_Syntax:_

        cut -c 1                                #First column

        cut -c 1,2                              #First and second column

        cut -c 1-                               #Display all columns after first

        cut -c -3                               #Display all columns before third



### 3)FIELD based


_Syntax:_

        cut -f 1                                #If there is no delimeter given then by default delimeter is taken as "tab"

        cut -d ":" -f 1                         #The fields will be seperated on basis of "colon :" and displays first field

        cut -d ":" -f 1,2

        cut -d ":" -f -3                        #The fields will be seperated on basis of "colon :" and displays all fields before third

        cut -d ":" -f 1 -s                      #In above cases if any lines which does not have that delimter thn it is by default displayed. However if we used -s then this can be avoided

[Go to TOP](https://github.com/nambinayagan/rhcsa_exam#cut-command-in-linux-cheatsheet "Cut Command")
