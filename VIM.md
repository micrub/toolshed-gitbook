# Wrapping text

You can set the text width for automatic word wrapping using `:set textwidth=n`
(or `:set tw=n`) where n is a positive integer, for example:

`:set tw=79`

That will automatically wrap text as close to 79 characters as white space
allows without exceeding the 79 character limit. This option wraps at word
boundaries.

To disable word wrapping:
`:set tw=0`


# Spell check

Support for spell checking was added in Vim 7.

`:set spell spelllang=en_us`

or only in local buffer :
`:setlocal spell spelllang=en_us`

To disable:
`:set nospell`

To move to a misspelled word, use `]s` and `[s`. The `]s` command will move the cursor
to the next misspelled word, the `[s` command will move the cursor back through
the buffer to previous misspelled words.

Once the cursor is on the word, use `z=`, and Vim will suggest a list of
alternatives that it thinks may be correct. For instance, if I highlight
autocompletion and then use `z=`.

`zg` Add word under the cursor as a good word to the first
namee in `spellfile`.  A count may precede the command
to indicate the examplentry in `spellfile` to be used.  A
count of two uses the second entry.
Name of the word list file where words are added for the `zg` and `zw`
commands.  It must end in ".{encoding}.add".  You need to include the
path, otherwise the file is placed in the current directory.

`zG` Like `zg` but add the word to the internal word list The internal word list
is used for all buffers where `spell` is set.  It is
not stored, it is lost when you exit Vim.  It is also cleared when `encoding`
is set.

# Vim should not highlight strings between quotes in Markdown files

```
au BufRead,BufNewFile *.md set filetype=markdown
```

# Using Vim with Syntastic and ESLint

Install [ Syntastic ](http://vimawesome.com/plugin/syntastic) if you haven’t already.
I use [ Vundle ](https://github.com/VundleVim/Vundle.vim) as my Vim plugin manager.

```
Plugin 'vim-syntastic/syntastic'
```

Install/update plugins:

```
vim +PluginUpdate
```

Install `eslint` globally.

```
npm install eslint --global
```

Add `eslint` as **checker** for Javascript files.

```
let g:syntastic_javascript_checkers=['eslint']
```

## Reference

* [Using Vim with Syntastic and ESLint](http://remarkablemark.org/blog/2016/09/28/vim-syntastic-eslint/)
