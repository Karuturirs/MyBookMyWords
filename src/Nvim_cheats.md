## NeoVim editor tips:

* To start Neovim, run `nvim` 

  ##### Lesson 1 SUMMARY

     1. The cursor is moved using either the arrow keys or the hjkl keys.
         h (left)   j (down)       k (up)       l (right)

     2. To start Vim from the shell prompt type:

  ~~~ sh
        $ vim FILENAME
  ~~~

     3. To exit Vim type: `<Esc>` `:q!` `<Enter>` to trash
        all changes.
                  OR type: `<Esc>` `:wq` `<Enter>` to save
        the changes.
     4. To delete the character at the cursor type: `x`
     5. To insert or append text type:
        `i` insert text `<Esc>`     insert before the cursor.
        `A` append text `<Esc>`     append after the line.

  #####  Lesson 2 SUMMARY

     1. To delete from the cursor up to the next word type:    `dw`
     2. To delete from the cursor to the end of a line type:   `d$`
     3. To delete a whole line type:                           `dd`
     4. To repeat a motion prepend it with a number:    `2w`
        5. The format for a change command is:
          operator   [number]   motion
        where:
           operator -   is what to do, such as d for delete
           [number] -   is an optional count to repeat the motion
           motion   -   moves over the text to operate on, such as:
                            w (word),
                            $ (to the end of line), etc.
        6. To move to the start of the line use a zero: 0
        7. To undo previous actions, type:            `u`  (lowercase u)
        To undo all the changes on a line, type:   `U`  (capital U)
        To undo the undo's, type:                  `<C-r>`

  #####   Lesson 3 SUMMARY

     1. To put back text that has just been deleted, type p. This puts the
        deleted text AFTER the cursor (if a line was deleted it will go on the
        line below the cursor).

     2. To replace the character under the cursor, type r and then the
        character you want to have there.

     3. The change operator allows you to change from the cursor to where
        the motion takes you. Type `ce` to change from the cursor to the
        end of the word, `c$` to change to the end of a line.

     4. The format for change is:

         c   [number]   motion

  #####   Lesson 4 SUMMARY

     1. `<C-g>`     displays your location and the file status.
        `G`         moves to the end of the file.
         number `G` moves to that line number.
        `gg`        moves to the first line.
     2. Typing `/` followed by a phrase searches FORWARD for the phrase.
        Typing `?` followed by a phrase searches BACKWARD for the phrase.
        After a search type `n` to find the next occurrence in the same
        direction or `N` to search in the opposite direction.
        `<C-o>` takes you back to older positions, `<C-i>` to
        newer positions.
     3. Typing `%` while the cursor is on a (,),[,],{, or } goes to its
        match.
     4. To substitute new for the first old in a line type
    ~~~ cmd
  					:s/old/new
    ~~~
   To substitute new for all 'old's on a line type

    ~~~ cmd
            :s/old/new/g
    ~~~
   To substitute phrases between two line #'s type

    ~~~ cmd
            :#,#s/old/new/g
    ~~~
  To substitute all occurrences in the file type

    ~~~ cmd
            :%s/old/new/g
    ~~~
  To ask for confirmation each time add 'c'

    ~~~ cmd
            :%s/old/new/gc
    ~~~

  

  ##### Lesson 5 SUMMARY

  1. `:!` command executes an external command.

     Some useful examples are:
     `:!ls`              -  shows a directory listing
     `:!rm FILENAME`     -  removes file FILENAME

  2. `:w FILENAME`   writes the current Vim file to disk with
       name FILENAME.

  3. `v`  motion, select all the lines thats needed,  `:w FILENAME`   saves the Visually selected lines in file
       FILENAME.

  4. `:r FILENAME`  retrieves disk file FILENAME and puts it
       below the cursor position.

  5. `:r !dir  `     reads the output of the dir command and
       puts it below the cursor position.

  #####  Lesson 6 SUMMARY

     1. Type `o` to open a line BELOW the cursor and start Insert mode.
        Type `O` to open a line ABOVE the cursor.

     2. Type `a` to insert text AFTER the cursor.
        Type `A` to insert text after the end of the line.

     3. The `e` command moves to the end of a word.

     4. The `y` operator copies text, `p` pastes it.

     5. Typing a capital `R` enters Replace mode until `<Esc>` is
         pressed.

     6. Typing ":set xxx" sets the option "xxx". Some options are:

            'ic' 'ignorecase'   ignore upper/lower case when searching
            'is' 'incsearch'    show partial matches for a search phrase
            'hls' 'hlsearch'    highlight all matching phrases

         You can either use the long or the short option name.

     7. Prepend "no" to switch an option off:
    ~~~ cmd
            :set noic
    ~~~
     8. Prepend "inv" to toggle an option:
    ~~~ cmd
            :set invic
    ~~~

  9. If you want to ignore case for just one search command, use \c
             in the phrase:

      ```/ignore\c <Enter>```

  #####  Lesson 7 SUMMARY

     1. Type `:help`
        or press `<F1>` or `<Help>` to open a help window.

     2. Type `:help TOPIC` to find help on TOPIC.

     3. Type `<C-w><C-w>` to jump to another window

     4. Type `:q` to close the help window

     5. Create a vimrc startup script to keep your preferred settings.

     6. While in command mode, press `<C-d>` to see possible completions.
         Press `<Tab>` to use one completion.
         
         

  ##### CONCLUSION

    This was intended to give a brief overview of the Vim editor, just enough to
    allow you to use the editor fairly easily. It is far from complete as Vim has
    many many more commands. Consult the help often.

    There are many resources online to learn more about vim. Here's a bunch of
    them:

    - Learn Vim Progressively: http://yannesposito.com/Scratch/en/blog/Learn-Vim-Progressively/
    - Learning Vim in 2014: http://benmccormick.org/learning-vim-in-2014/
    - Vimcasts: http://vimcasts.org/
    - Vim Video-Tutorials by Derek Wyatt: http://derekwyatt.org/vim/tutorials/
    - Learn Vimscript the Hard Way: http://learnvimscriptthehardway.stevelosh.com/
    - 7 Habits of Effective Text Editing: http://www.moolenaar.net/habits.html
    - vim-galore: https://github.com/mhinz/vim-galore
