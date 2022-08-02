# company-spell

![A dropdown selection in Emacs with word suggestions](doc/example.gif)

An Emacs `company-mode` backend for any terminal spellchecker. Unlike `company-ispell` which requires a plaintext dictionary, this just pipes results from a spellchecking command on your computer into `company-mode`. I have not run into any notable performance issues with this approach.

## Instructions

1. Ensure a terminal spellchecker is installed (`aspell`, `hunspell`, `ispell`, etc)
2. Clone this repo and load it like this:
```
(add-to-list 'load-path "~/.emacs.d/local/company-spell")
(require 'company-spell)
```
3. Once loaded:
```
(add-to-list 'company-backends  'company-spell t)
```
4. Optionally, set a spellchecker that isn't the default value of `aspell`:
```
(setf company-aspell-command "hunspell")
;; or
(setf company-aspell-command "ispell")
```
5. You can further customize your results by setting custom args (only `-a` is enabled by default). For instance, search via "soundslike":
```
(setf company-spell-args "-a soundslike")
```
