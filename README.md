
# Basic Linux Commands

[Grep Command](https://github.com/nambinayagan/rhcsa_exam/blob/main/README.md#grep-command "Grep Command")

[Cut Command](https://github.com/nambinayagan/rhcsa_exam/blob/main/README.md#cut-command "Cut Command")

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

### FIND command

Syntax: find <location> <options>.. <-exec=>
	
 ==============To list files which are matching criteria=======================
 ```

find .          	        #to list all file and directories including subdirectories in current location

find <location>       		  #to list all files and directories inside the specified directory
	
find . -type f		          #to list all files in current location

find . -type d		          #to list all directories and subdirectories in current location

find . -type d -maxdepth 1	  #to list all directories and not the subdirectories

find . -name "nambi"	          #to list all files with exact same name

find . -iname "nambi"	        	#to list all files with exact same name but case insensitive

find . -iname "*nambi*"	        	#to list all files having nambi in their name eg: nambi.txt, rnambi.jpg

find . type -f -user "nambi"		#to list all files onwned by user nambi

fine . -empty				#to list all empty files
```

		According to Time

find . -type f -mmin -10		#list all files modified in last 10minutes
find . -type f -mmin +10                #list all files modified in before last 10minutes
find . -type f -mmin +5 -mmin -10	#list all files which were modified before 5 mins but in last 10mins
find . -type file -mtime -10		#list all files modified in last 10 days
find . -type file -mtime +10		#list all files modified before 10 days
					#mmin >> Modified time in minutes
					#mtime >> Modified time in days
					#cmin >> Change time in minutes
					#ctime >> Change time in days
					#amin >> Access time in minutes
					#atime >> Access time in days


		According to Size

fine . -size +5M			#list all files having size higher than 5MB
find . -size -5M			#list all files having size lower than 5MB

		According to permission of files

find . -perm 777			#list all files and folders having permission 777



=============================To take acctions on files matching criteria===============


find . -type d -exec chmod 755 {} \;			#to change the permission of all directoires to 755
find . -type f -exec chmod 644 {} \;			#to change the permission of all files to 644
find . -user nambi -exec chown nambi1: {} \;		#to change owner of a files from nambi to nambi1
find . -empty -exec rm -f {} \;				#to delete all empty files
find . -user nambi -exec cp -rpf {} <location> \;	#to copy all the files owned by user nambi to the required locations





[Go to TOP](https://github.com/nambinayagan/rhcsa_exam#basic-linux-commands "Basic Linux Commands")
