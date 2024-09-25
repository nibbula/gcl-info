# Moved to https://codeberg.org/nibbula/gcl-info

### Info files for Common Lisp

w/minor fixes, split out from GCL for your (or mostly my) convenience.

Q. How to use?

A. 1. Dump into `~/info` or something.

   2. Optionally, compress them. Perhaps something like:
   ```
    $ gzip *.info-[0-9]*
```
   3. Maybe let emacs in on it:
```emacs-lisp
;; If wherever you put it isn't already in your info list:
(setq Info-directory-list (append Info-directory-list '("~/info")))

;; Something like this was suggested on Lemonodor?
(defvar lisp-hyperspec-lookup-history nil
  "Prompt history for lisp-hyperspec-lookup")
(defun lisp-hyperspec-lookup (arg)
  (interactive "P")
  (let ((what (if arg
		  (read-string "Lookup in Hyperspec: " nil
			       lisp-hyperspec-lookup-history)
		  (thing-at-point 'symbol))))
    (Info-goto-node (concat "(gcl) " what))))

;; This is, of course, just a suggestion.
(define-key ctl-x-map "h" 'lisp-hyperspec-lookup)
```
   4. Don't touch the mouse.
   5. ...??
   6. Profit??

♥ to [William F. Schelter](https://www.gnu.org/software/gcl/) and everyone who made this.

🖕 to specification hoarders.
