
;; Added by Package.el.  This must come before configurations of
;; installed packages.  Don't delete this line.  If you don't want it,
;; just comment it out by adding a semicolon to the start of the line.
;; You may delete these explanatory comments.
(package-initialize)

(custom-set-variables
 ;; custom-set-variables was added by Custom.
 ;; If you edit it by hand, you could mess it up, so be careful.
 ;; Your init file should contain only one such instance.
 ;; If there is more than one, they won't work right.
 '(ansi-color-faces-vector
   [default default default italic underline success warning error])
 '(custom-enabled-themes (quote (tango-dark)))
 '(package-selected-packages (quote (auctex))))
(custom-set-faces
 ;; custom-set-faces was added by Custom.
 ;; If you edit it by hand, you could mess it up, so be careful.
 ;; Your init file should contain only one such instance.
 ;; If there is more than one, they won't work right.
 '(default ((t (:family "Inconsolata" :foundry "outline" :slant normal :weight normal :height 113 :width normal)))))

;(autoload 'flyspell-mode "flyspell" "On-the-fly spelling checker." t)

(add-hook 'LaTeX-mode-hook 'LaTeX-math-mode) ; Enable LaTeX Math mode by default
(add-hook 'LaTeX-mode-hook 'turn-on-reftex) ; Enable RefTeX by default
;(add-hook 'LaTeX-mode-hook 'flyspell-mode) ; Enable Flyspell by default
;(add-hook 'LaTeX-mode-hook (lambda ()
;			     (TeX-fold-mode 1))) ; Automatic code folding

(setq TeX-electric-sub-and-superscript 1) ; Automatically insert a pair of braces
;(setq TeX-parse-self t) ; Enable parse on load.
;(setq TeX-auto-save t) ; Enable parse on save.

(defun insert-frac ()
  "We insert  \\frac{}{} and position point before the first right brace."
  (interactive)
  (progn
    (insert "\\frac{}{}")
    (backward-char)
    (backward-char)
    (backward-char)))
(global-set-key "\C-cf"   'insert-frac)
 ; Define \frac{}{}
