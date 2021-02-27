
# Basic Linux Commands

[Cut Command in Linux Cheatsheet](https://github.com/nambinayagan/rhcsa_exam#cut-command-in-linux-cheatsheet "Cut Command")


### Cut Command in Linux Cheatsheet

CUT command can be differentiated in three ways

- **BYTE** based   `         cut -b "byte"`

- **COLUMN** based          `cut -c "column"`

- **DELIMETER** based       `cut -d "delimeter" -f "field"`



### 1)BYTE based

_Syntax:_

        cut -b 1                                #First byte

        cut -b 1,2                              #First and Second byte

        cut -b 1-                               #Display all bytes after first

        cut -b -3                               #Display all bytes before third


### 2)COLUMN based


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

[Go to TOP](https://github.com/nambinayagan/rhcsa_exam/tree/main/practice#cut-command-in-linux-cheatsheet "Cut Command")
