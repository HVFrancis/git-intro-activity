Git Intro Activity
==================

A. Form teams
-------------

Form a 2-person team. Try to find someone who uses the same platform as you (e.g., Windows, Linux, etc.). If you can't, that's fine. If you are the odd-person-out, join a team of 2.

Assign the following roles to the members of your team. If you are in a
team of 2, assign the recorder and navigator roles to the same person.

Roles:

-   Driver: Creates and maintains a local git repository.

-   Navigator: Reads instructions and records answers.

3rd person role (if you have a 3-person team):

-   Quality Assurance Person: Ensures instructions are being carried out correctly, answers are clear, and looks for ways for the team to work together more effectively.

You will be rotating roles. Your instructor will let you know when to switch roles. Switching roles requires switching computers. So plan accordingly.


B. Objectives
-------------

After completing this tutorial you will be able to...

-   Configure git.

-   Make and commit changes to a repository.

-   Add new files to a repository.

-   Remove a file from a repository.

-   Modify a file and commit the change.

-   Stage changes for commit.

-   Unstage changes for commit.

-   Explain the purpose of the stage/cache/index.

-   Inspect the state of a repository.

-   Undo a commit.

Throughout the tutorial you will be asked many questions. The goal is to
become familiar with basic git commands and to produce notes that you
can refer back to later. Don’t worry too much about accuracy, for each
question, provide your best answer and move on to the next question.

C. Download and install Git
---------------------------

Download and install git for your operating system:

-   <https://git-scm.com/downloads>

Starting a terminal:

-   **Windows**:

    -   git-bash.exe (Linux style commands)

    -   git-cmd.exe (Windows style commands)

-   **Mac OSX:** Finder -&gt; Applications -&gt; Utilities -&gt;
    Terminal.app

-   **Linux:** will vary depending on your window manager

D. Getting help
---------------

Run the following commands.

    git help
    git help -ag
    git help init

1.  What does `git help` do?

    ```
    lists and explains commands that git uses

    ```

2.  What does `-ag` cause `git help` to do?

    ```
    provides subcommands and some concepts guides (a = all, g = guides)


    ```

E. Identify yourself
--------------------

Run the following commands, replacing BOGUS NAME and BOGUS@EMAIL with
your name and email.

    git config --global user.name 'BOGUS NAME'
    git config --global user.email 'BOGUS@EMAIL'

WARNING: The name and email you give will be listed on each commit you make.
If this repository is ever published, your name and email on every commit
will be too. Also, if you are working on a shared computer, you should
consider changing this configuration before you walk away.


1.  What are these commands doing?

    ```
   assigning identifying information to a config file (but how would a student know?)

    ```

2.  What is the purpose of `--global`?

    ```
    assigns the change to the global config file



    ```

F. Create a repository
----------------------

From the command line, run the following commands.

```
mkdir first_project
cd first_project
```

1.  By default any file that starts with `.` is hidden. How do you
    display a hidden file?

    ```
    ls -a    

    ```

2. Run this command to show the hidden files in the current directory. Are there any?

    ```
    it shows . (current directory) and .. (parent directory)


    ```

3. Now run the following command.

    ```
    git init
    ```


4. Check for hidden files again.  What was created by `git init`?

    ```
    .git



    ```


5.  What do you think would happen if you delete `.git`?

    ```
    It wouldn't be a git repository any more.


    ```

6.  Using your observations to the previous questions, answer the following.
    You find an old project on your hard drive. You do not remember if
    it is a under version control. What could you look for to determine
    if the project is being managed using git?

    ```
    do ls -a and see if .git is there


    ```

G. Basic commands
-----------------

Use a plain text editor to create `names.txt` inside the `first_project`
folder. Put the names of your team in the file. Save and exit.

Run `git status` before and after each of these commands.

    git add names.txt
    git commit –m “Add our names.”
    git log

1.  What kind of information does `git status` report?

    ```
    it shows us what files have been changed and/or added for consideration for staging


    ```

2.  What does `git add names.txt` do?

    ```
    tells git it's a file i would to add to the repository



    ```

3.  What does `git commit -m "Add our names."` do?

    ```
    makes the change official


    ```

Use a plain text editor to create the following files:

-   `birthdays.txt` - Put your birthdays in this file.

-   `movies.txt` - Put the last movie each of you watched in alphabetical order.

Run `git status` before and after each of these commands.

    git add .
    git commit		Note:  Commit will open the vim editor; write a multi-line commit
						   message, save and quit (press esc and then type :wq).
    git log

4.  What does `git add .` do? What do you think `.` means?

    ```
    it added all the changed files for staging


    ```

5.  What does `git commit` (without -m) do?

    ```
    opens a window for typing in the message



    ```

6.  If you want to write a more detailed commit message (which is
    good practice) what command would you use?

    ```
    git commit (and type the message in the editor window)


    ```

7.  What does `git log do`?

    ```
    shows a history of all the commits


    ```


H. Stage/Cache/Index
--------------------

Do the following:

-   Modify `names.txt` so that names are listed in *Last, First* format,
    one per line.

-   Modify `movies.txt` so they are in reverse alphabetical order
    by title.

-   Create a new file `foods.txt` that contains your favorite foods (one
    for each team member).

Run the following commands:

    git add names.txt
    git status

1.  Below write each file name under the state that its changes are
    currently in. Compose a definition for each state.

    **Staged**

    ```

    names.txt

    ```

    **Unstaged**

    ```
    movies.txt



    ```

    **Untracked**

    ```

    foods.txt

    ```

1.  If you run `git commit` what changes will be committed (***don't do
    it***)?

    ```

    just the one for names.txt

    ```

2.  What command do you run to stage changes?

    ```

    git add

    ```

3.  What command do you run to unstage changes?

    ```
    git reset


    ```

Run the following commands:

    git diff
    git diff --cached

1.  What does `git diff` display?

    ```
    it shows the differences in files that have not been staged


    ```

2.  What does `git diff --cached` display?

    ```
    shows the differences in files that are staged


    ```

3.  Formulate a sequence of commands to unstage changes to `names.txt`,
    and stage the changes to `movies.txt`. Execute your commands and
    confirm they worked.

    ```
    git rm names.txt
    git add movies.txt


    ```

4.  Edit `movies.txt`, change any one of the movies, and save it. Then
    run `git status`. What do you observe? Explain what you think is
    going on.

    ```
    the previous change is still there, but now there's a new change to stage


    ```

5.  Delete `names.txt`. Then run `git status`. What do you observe?
    Explain what you think is going on.

    ```
    I haven't staged the the fact that names.txt is gone


    ```

6.  Rename `movies.txt` to `last-movies`. Run `git status`. Observe
    and explain.

    ```
    it doesn't see movies.txt, so it assumes it's deleted, and last-movies.txt is a new file not being tracked


    ```

7.  Formulate a sequence of commands to stage all changes including the
    untracked file and commit (with any reasonable message you like).
    Execute them.

    ```
    git add foods.txt
    git add last-movies.txt
    git rm movies.txt
    git rm names.txt
    git commit -m"seeing the result of adding/moving/deleting files"


    ```

8.  In git vernacular, `index`, `cache`, and `stage` all refer to the
    same thing. What does it hold?

    ```
    files that we have changed and want to have modified in the repository


    ```

9.  Why have a `stage`? Why not just commit all changes since the last
    commit?

    ```
    some of the files changed might have been for internal use/testing/etc and not a real change to the project


    ```

I. Undo
-------

Run the following commands:

    git log
    git status
    git reset --soft "HEAD^"
    git log
    git status

1.  What does `git reset --soft ``"HEAD^" `do?

    ```
   removed some of the commits (not sure how it decided what "HEAD^" is)


    ```

Run the following commands:

    git commit –m "Redo."
    git log
    git status
    git reset --hard "HEAD^"
    git log
    git status

1.  What does `git reset --hard ``"HEAD^"`` `do?

    ```
    


    ```

2.  What is the difference between `--hard` and `--soft`?

    ```



    ```

3.  What do you think `HEAD` means?

    ```


    ```

4.  What do you think `HEAD^` means?

    ```


    ```

J. Helpful resources
--------------------

-   <https://git-scm.com/doc>

-   <https://www.atlassian.com/git/tutorials/>

-   <https://training.github.com/kit/downloads/github-git-cheat-sheet.pdf>

K. Copyright and Licensing
--------------------------

Copyright 2016, Darci Burdge and Stoney Jackson SOME RIGHTS RESERVED

This work is licensed under the Creative Commons Attribution-ShareAlike
4.0 International License. To view a copy of this license, visit
<http://creativecommons.org/licenses/by-sa/4.0/> .
