# Fix Input

[![License GPL 3](https://img.shields.io/badge/license-GPL_3-green.svg)](http://www.gnu.org/licenses/gpl-3.0.txt)
[![MELPA](https://melpa.org/packages/fix-input-badge.svg)](https://melpa.org/#/fix-input)
![CI](https://github.com/mrkkrp/fix-input/workflows/CI/badge.svg?branch=master)

Let's suppose you have switched to an alternative keyboard layout. Chances
are you're going to use that layout everywhere, not only in Emacs, so you
set it up on the OS level or maybe you even get a special keyboard that uses
that layout. Now suppose that you need to use an input method in Emacs. The
nightmare begins: the input methods in Emacs translate Latin characters
assuming the traditional QWERTY layout. With an alternative keyboard layout,
the input methods do not work anymore.

One solution is to define a new custom input method and call it for example
`dvorak-russian`. But that is not a general solution to the problem—we want
to be able to make any existing input method work with any Latin layout on
the OS level. This package generates input methods knowing the input method
that corresponds to the layout on the OS level and the input method you want
to fix.

## Installation

The package is available via MELPA, so you can just type `M-x
package-install RET fix-input RET`.

If you would like to install the package manually, download or clone it and
put on Emacs' `load-path`. Then you can require it in your init file like
this:

```emacs-lisp
(require 'fix-input)
```

## Usage

In your configuration you need to generate a new “corrected” input method,
for example:

```emacs-lisp
(fix-input "english-dvorak"   ;; matches alternative layout
           "russian-computer" ;; works with QWERTY
           "dvorak-russian")  ;; name of new input method that preserves
                              ;; the same layout with Dvorak
```

Here the new input method is named `"dvorak-russian"`. With Dvorak layout,
this will let users to use the familiar layout when they wish to type
Russian.

Once generated, the layout can be used as usual.

## License

Copyright © 2016–present Mark Karpov

Distributed under GNU GPL, version 3.
