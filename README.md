# Fix Input

[![License GPL 3](https://img.shields.io/badge/license-GPL_3-green.svg)](http://www.gnu.org/licenses/gpl-3.0.txt)
[![MELPA](https://melpa.org/packages/fix-input-badge.svg)](https://melpa.org/#/fix-input)
[![Build Status](https://travis-ci.org/mrkkrp/fix-input.svg?branch=master)](https://travis-ci.org/mrkkrp/fix-input)

Suppose that you have switched to Dvorak or Colemak. Chances are you're
going to use that layout everywhere, not only in Emacs (the fact is, we
still need to leave Emacs sometimes and use other programs), so you setup it
on OS level or maybe you even have “hardware” Dvorak keyboard. You adapt to
this new layout and everything is OK.

Now suppose that you need to input non-Latin text and for that you naturally
need to activate an input method in Emacs. The nightmare begins: input
methods in Emacs translate Latin characters as if they are on a traditional
QWERTY layout. So now the input method you used before does not work
anymore.

One solution is to define new custom input method and call it for example
`dvorak-russian`. But that is not a general solution for the problem — we
want to be able to make any existing input method work just the same with
any Latin layout on OS level. This package generates “fixed” input methods
knowing input method that corresponds to layout on OS level and input method
you want to fix. And I want to tell you — it's a win.

## Installation

Download this package and place it somewhere, so Emacs can see it. Then put
`(require 'fix-input)` into your configuration file. Done!

To install the package via MELPA, execute: <kbd>M-x package-install RET
fix-input RET</kbd>.

## Usage

In your configuration you need to generate new “corrected” input method, for
example:

```emacs-lisp
(fix-input "english-dvorak"   ;; matches alternative layout
           "russian-computer" ;; works with QWERTY
           "dvorak-russian")  ;; name of new input method that preserves
                              ;; the same layout with Dvorak
```

Here we get new input method named `"dvorak-russian"`. With Dvorak layout,
this will let users use familiar layout when they wish to type Russian.

Once generated, the layout can be used as usual.

## License

Copyright © 2016–2017 Mark Karpov

Distributed under GNU GPL, version 3.
