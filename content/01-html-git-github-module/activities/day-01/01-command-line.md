+++
title = "01. Console Commands👩‍🎓👨‍🎓"
weight = 1
tags = ["html"] 
+++

# Bash/Terminal Commands

## Instructions:

* From the terminal/console and using only the command line, create the following:
  
  * A new folder with the name of `first_day_stuff`.
  
  * A new HTML file with the name of `first-day.html`.
  
  * Open the current folder containing the new HTML file.

### BONUS
* Create multiple directories/folders with the names `one_folder` and `second_folder` in one command.
* Create multiple files with the names `one.html` and `two.html` in one command in the first_day_stuff directory.


---
## ✅ Solutions 
{{%expand "Solutions Click Here" %}}


  * The solution breaks down the steps to meet the goal.

  1.  🔑  We use `cd` to navigate to `Desktop`:

### Mac 🍎: 

```bash
cd Desktop
```

### PC 🖼️: 

To get into Desktop you might see onedrive and that is where desktop folder might be located.
    
```bash 
cd Onedrive
cd Desktop
```

or 

```bash
cd Onedrive/Desktop
```

or 

```bash
cd Desktop
```

---

  2.  🔑 We use the `mkdir` command to create a new directory inside `Desktop` named `first_day_stuff`:

    ```bash
    mkdir first_day_stuff
    ```

  3.  🔑 We use `cd` to navigate inside the `first_day_stuff` directory that we just created:

    ```bash
    cd first_day_stuff`
    ```

  4.  🔑 We use `touch` to create a new file named `index.html` inside `first_day_stuff`:

    ```bash
    touch index.html
    ```

  5. 🔑 To test that the user's goal has been met, we use `cd ..` to navigate back to the `Desktop` and `ls` to list the contents of `Desktop`:

    ```bash
    cd ..

    ls
    ```

  * The `first_day_stuff` directory is listed among the contents of the `Desktop`.

  * To test that a file has been created in the folder, we use `cd` to navigate into the`first_day_stuff` directory:

    ```bash
    cd first_day_stuff
    ```

  * Then we use `ls` to list the contents of the directory:

    ```bash
    ls
    ```

  * We see that an `index.html` file is located inside the `first-day` directory.

  * The solution addresses all the conditions of the acceptance criteria and clearly meets the user's goal. Good work!


{{% /expand%}}


# Resources

These are the basic commands for navigating directories in a terminal or Git Bash window.

### Moving in Directories

#### Change directory:

`cd [path/to/desired/directory]`

#### Change to home directory:

`cd ~`

#### Move to one directory up:

`cd ..`

#### View folders and files in the directory:

`ls`

#### Show the current directory:

`pwd`

#### Autocomplete a file name in the current directory:

Press `tab` key once to autocomplete once you have typed a unique portion of a file name. 

### File Manipulations

#### Make new file:

`touch [name of file to create]`

#### Make new folder:

`mkdir [name of directory to create]`

#### Delete file:

`rm [name of file to remove]`

#### Delete folder:

`rm -r [name of directory to remove]`

#### Copying file:

`cp [filename1] [filename2]`

#### Move/rename file:

`mv [filename1] [filename2]`

### Mac Only

#### Open file or folder (Mac only):

`open [name of file]`

#### Open all files and folder in current directory (Mac only):

`open .`

### PC Only

#### Open file or folder (PC only):

`explorer [name of file]`

#### Open all files and folder in current directory (PC only):

`explorer .`

---


# Cheatsheet

Open Terminal/Console. Then walk and explain to students what each of the following commands does:

```bash
cd (changes directory)

cd ~ (changes to home directory)

cd .. (moves up one directory)

ls (lists files in folder)

pwd (shows current directory)

mkdir <FOLDERNAME> (creates new directory)

touch <FILENAME> (creates a file)

rm <FILENAME> (deletes file)

rm -r <FOLDERNAME> (deletes a folder, note the -r)

open . (opens the current folder—MAC SPECIFIC)

open <FILENAME> (opens a specific file—MAC SPECIFIC)

explorer <FILENAME> (opens the specific file—BASH SPECIFIC)

explorer . (opens the current folder—BASH SPECIFIC)
```



{{% notice tip %}}
`Notes`: Tabbing
Pressing the `tab key` after typing `"cd fol"` will autocomplete to `"cd foldername,"` assuming foldername is unique. (Folder/Filename Autocomplete: Show students what happens when there are unique and multiple options based on what they typed.)
{{% /notice %}}
