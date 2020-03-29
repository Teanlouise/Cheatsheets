[Back to Cheatsheets](https://teanlouise.github.io/cheatsheets/)

![bash](https://user-images.githubusercontent.com/19520346/77840737-0c319880-71ce-11ea-925b-84e5f6702df3.png)

# BASICS

| Syntax            | About                             | 
| ------------------|:---------------------------------:| 
| `mkdir dir`       | create directory 'dir'            | 
| `touch file.txt`  | create new file 'file' in current |
| `clear`           | clears window of all commands     |


# NAVIGATION

| Syntax        | About                         | 
| ------------- |:-----------------------------:| 
| `cd docs`     | navigate int 'folder'         |
| `cd ..`       | navigate back 1 level         |
| `cd ../..`    | navigate back 2 levels        |
||| 
| `pwd`         | print working directory       |
| `ls`          | list of current directory     | 
| `ls -a`       | list all plus hidden          |
| `ls -l`       | lis all in long format        |
| `ls -t`       | list in order of last modified|

# MANIPULATING FILES

| Syntax                                | About                                         | 
| ------------------------------------- |:---------------------------------------------:| 
| `echo "text"`                         | print 'text'                                  |
| `echo "text" > notes.txt`             | redirect "text" to notes.txt                  |
| `echo "text" >> notes.txt`            | create 'notes' file with 'text'               |
|||
| `cat notes.txt`                       | print contents of 'notes'                     | 
| `cat note1.txt > note2.txt`           | overwrite 'note2' with contents of 'note1'    |
| `cat note1.txt >> note2.txt`          | 'note1' contents appended to 'note2'          |
| `cat notes.txt | sort > notes2.txt`   | sorts 'note1' contents & redirects to 'file2  |
| `less notes.txt`                      | similar to cat, but print one page at a time  |    
|||
| `cp note1.txt note2.txt`              | copy 'note1' into 'note2'                     |
| `cp docs1/note.txt docs2`             | copy 'note' into 'docs2'                      |
| `cp * docs`                           | copy all from current into 'docs'             |
| `cp m*.txt docs`                      | copy all files starting with 'm' into 'docs'  |
|||
| `mv notes.txt docs`                   | move 'note' to 'docs'                         |
| `mv notes.txt rename.txt`             | rename 'note'                                 |
| `mv * docs/`                          | move all files from current to 'docs'         |
|||
| `rm notes.txt`                        | remove 'notes' (permanent)                    |
| `rm -r docs`                          | remove 'docs' and all its files               |
| `rm docs/*`                           | remove all files in 'docs'                    |
|||
| `sort notes.txt`                      | sorts alphabetically                          |
| `uniq notes.txt`                      | filters out adjacent duplicates               |
| `sort notes.txt | uniq > notes2.txt`  | filter out duplicates                         |
|||
| `command1/command2`                   | output of 'command1' to input of 'command2'   |

# SEARCHING FILES

| Syntax                                | About                                                             | 
| ------------------------------------- |:-----------------------------------------------------------------:| 
| `grep Text notes.txt`                 | search for "Text" in file (case sensitive)                        |
| `grep -i text notes.txt`              | search for "text" in file (case insensitive)                      |
| `grep -R text /docs`                  | search for "text" recursive in 'docs' (case sensitive)            |
| `grep -Rl text /docs`                 | search for "text" in filenames of 'docs'                          |
|||
| `sed 'S/text/replace/' notes.txt`     | search 'notes' for "text' and "replace" (only first of each line) |
| `sed 'S/text/replace/g' notes.txt`    | same but replace "text" globally (all instances)                  |
|||
|`wc`                                   | return number of lines, word, characters                          |
| `-N`                                  | add line numbers to file                                          |

# NANO & ENVIRONMENT VARIABLES

| Syntax                        | About                                             | 
| ----------------------------- |:-------------------------------------------------:| 
| `nano notes.txt`              | open 'name' file in nano editor                   |
| `ctrl + o`                    | saves nano file (letter o)                        |
| `ctrl + x`                    | exit nano                                         |
| `nano ~/.bash-profile`        | create file to store environment variables        |
| `source ~/.bash-profile`      | activate changes made in nano for current session |
| `alias shortcut="command"`    | create 'shortcut' for "command" eg. pd = "pwd"    |
| `export VAR="value"`          | assign "value" to environment variable 'VAR'      |
| `echo $VAR`                   | return value of 'VAR' environment variable        |
| `env`                         | list of environment variables                     |
| `env | grep VAR`              | value of 'VAR' environment variable               |

**ENVIRONMENT VARIABLES**
- USER
- HOME
- PATH: stores list of directories
- PS1: style of command prompt eg. $ or >>

# SCRIPTS

- `#!/bin/bash`   :  At the start of every script file
- `variable="text"` : declare 'variable' with "text"
- `echo $variable` : print value of 'variable'
- `./script.sh` : run 'script' in terminal
- `read number`: user input to 'number' variable
- `${var[#]}`: access index '#' of 'var'

## CONDITIONALS
```
if [ $var -op # ]
then 
    _____
else 
    _____
fi
```
**Operators (-op):**

| Int | Str  | Python  | About              |   
| --- |:----:| :------:|:------------------:| 
| -eq | ==   | ==      | equals             |
| -ne | !=   | !=      | not equal          |
| -le |      | <=      | less than/equal    |
| -lt |      | <       | less than          |
| -ge |      | >=      | greater than/equal | 
| -gt |      | >       | greater than       |
| -z  |      | null    | is null            |

## LOOPS

**FOR** 

Iterate list and do each for each step of list
```
for each in $var
do
    ____
done
```
- Note: 'each' defined at top of loop so don't need $


**WHILE** 

Keep looping while condition true
```
while [ $var -op # ]
do
    ____
    var = $((var + 1))
done
```

**UNTIL**

Keep looping until condition true
```
until [ $var -op # ]
do
    ____
    var = $((var + 1))
done
```

