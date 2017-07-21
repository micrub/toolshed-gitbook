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

## Other option is to use [standard](https://standardjs.com/) and [ale](https://github.com/w0rp/ale)

```
npm install standard --save-dev

```
After you've installed standard, you should be able to use the standard program.
The simplest use case would be checking the style of all JavaScript files in the
current working directory:

```
./node_modules/standard/bin/cmd.js
The react/jsx-space-before-closing rule is deprecated. Please use the react/jsx-tag-spacing rule with the "beforeSelfClosing" option instead.
standard: Use JavaScript Standard Style (https://standardjs.com)
standard: Run `standard --fix` to automatically fix some problems.
  /app.js:2:10: Missing space before function parentheses.
```

You can optionally pass in a directory (or directories) using the glob pattern.
Be sure to quote paths containing glob patterns so that they are expanded by
standard instead of your shell:

```
./node_modules/standard/bin/cmd.js "src/util/**/*.js" "test/**/*.js"
```

Install `standard` globally:

`npm install standard --global`

## [ Ale ](https://github.com/w0rp/ale) - <i class="fa fa-tasks" aria-hidden="true"></i>

Using [ Ale ](https://github.com/w0rp/ale) requires installed [ NeoVim ](https://neovim.io/) or
[ Vim 8 ](https://github.com/vim/vim/blob/master/runtime/doc/version8.txt).

## Reference

* [Using Vim with Syntastic and ESLint](http://remarkablemark.org/blog/2016/09/28/vim-syntastic-eslint/)
