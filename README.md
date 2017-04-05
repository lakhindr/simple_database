# Simple DB

This code is a replacment for a non-working code in Common-Lisp section of https://rosettacode.org/wiki/Simple_database

** To run it without any options will show help-menu 
```
$ clisp db.lisp
clisp db.lisp  delete <item-name> -------------------  delete an item
               delete-all ---------------------------  delete the database
               insert <item-name> <item-category> ---  insert an item with its category
               show ---------------------------------  shows the latest inserted item
               show-categories ----------------------  show all categories
               show-all -----------------------------  show all items
               show-per-category --------------------  show the latest item per category
```

** Here are a few steps to add a few titles, and their categories.
```
$ clisp db.lisp insert "title-vinyl-1" "vinyl"
$ clisp db.lisp insert "title-cd-1" "cd"
$ clisp db.lisp insert "title-dvd-1" "dvd"
$ clisp db.lisp insert "title-tape-1" "tape"
$ clisp db.lisp insert "title-tape-2" "tape"
```

** Here is the latest entry in the db
```
$ clisp db.lisp show
title-tape-2: (tape) (2017-04-04 20:19:06)
```

** Here is a (sorted time wise) list of all the entries
```
$ clisp db.lisp show-all
title-tape-2: (tape) (2017-04-04 20:19:06)
title-tape-1: (tape) (2017-04-04 20:19:00)
title-dvd-1: (dvd) (2017-04-04 20:18:55)
title-cd-1: (cd) (2017-04-04 20:18:48)
title-vinyl-1: (vinyl) (2017-04-04 20:18:41)
```

** Here is the latest entry for each category
```
$ clisp db.lisp show-per-category
title-vinyl-1: (vinyl) (2017-04-04 20:18:41)
title-cd-1: (cd) (2017-04-04 20:18:48)
title-dvd-1: (dvd) (2017-04-04 20:18:55)
title-tape-2: (tape) (2017-04-04 20:19:06)
```

** Here is the list of all categories
```
$ clisp db.lisp show-categories
(vinyl) (cd) (dvd) (tape) 
```

** To delete an entry
```
$ clisp db.lisp delete "title-tape-2"
```

** To delete all entries
```
$ clisp db.lisp delete-all
```
