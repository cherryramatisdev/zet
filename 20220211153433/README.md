# How to install stumpwm

1. First install `sbcl`
   Download x64 from sourceforge on website :: http://sbcl.org/
   Just extract it and run `sudo sh install.sh`
2. Install quicklisp from `sbcl`
   Download quicklisp and run with sbcl

   ```sh
       $ curl -O https://beta.quicklisp.org/quicklisp.lisp
       $ sbcl --load quicklisp.lisp
   ```

   Then at the REPL:

   ```lisp
   (quicklisp-quickstart:install)
   ```

   Make sure you have added it to your lisp init file using

   ```lisp
   (ql:add-to-init-file)
   ```

3. Install clx cl-ppre alexandria from quicklisp

   Then, in a fresh `sbcl` repl install the dependencies:

   ```lisp
   (ql:quickload "clx")
   (ql:quickload "cl-ppcre")
   (ql:quickload "alexandria")
   ```

4. Build stumpWM

   1. First clone the repo

   ```sh
       $ git clone https://github.com/stumpwm/stumpwm.git
   ```

   2. Then instsall dependencies

   ```sh
   sudo apt install autoconf
   ```

   3. Run scripts

   ```sh
   ./autogen.sh
   ./configure
   ```

   4. install it

   ```sh
   make
   sudo make install
   ```
