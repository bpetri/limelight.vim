limelight.vim
=============

Hyperfocus (clojure) programming in Vim.

A adapted fork of [junegunn/limelight.vim][k] to allow highlighting based on
parentheses.

(https://raw.github.com/bpetri/limelight.vim/master/limelight.gif://raw.github.com/bpetri/limelight.vim/master/limelight.gif)
![](https://raw.github.com/bpetri/limelight.vim/master/limelight.gif)

Usage
-----

- `Limelight [0.0 ~ 1.0]`
    - Turn Limelight on
- `Limelight!`
    - Turn Limelight off
- `Limelight!! [0.0 ~ 1.0]`
    - Toggle Limelight

### Limelight for a selected range

You can invoke `:Limelight` for a visual range. There are also `<Plug>`
mappings for normal and visual mode for the purpose.

```vim
nmap <Leader>l <Plug>(Limelight)
xmap <Leader>l <Plug>(Limelight)
```

### Options

For some color schemes, Limelight may not be able to calculate the color for
dimming down the surrounding paragraphs. In that case, you need to define
`g:limelight_conceal_ctermfg` or `g:limelight_conceal_guifg`.

```vim
" Color name (:help cterm-colors) or ANSI code
let g:limelight_conceal_ctermfg = 'gray'
let g:limelight_conceal_ctermfg = 240

" Color name (:help gui-colors) or RGB color
let g:limelight_conceal_guifg = 'DarkGray'
let g:limelight_conceal_guifg = '#777777'

" Default: 0.5
let g:limelight_default_coefficient = 0.7

" Number of nested parentheses pairs to include (default: 0)
let g:limelight_paragraph_span = 1

" Specify pair
let g:limelight_bop = '('
let g:limelight_eop = ')'

" Highlighting priority (default: 10)
"   Set it to -1 not to overrule hlsearch
let g:limelight_priority = -1
```

Goyo.vim integration
--------------------

```vim
autocmd! User GoyoEnter Limelight
autocmd! User GoyoLeave Limelight!
```

Acknowledgement
---------------

Thanks to [@Cutuchiqueno](https://github.com/Cutuchiqueno) for [suggesting
the idea](https://github.com/junegunn/goyo.vim/issues/34).

License
-------

MIT
