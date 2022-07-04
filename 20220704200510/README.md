# how to show diff commit without context

The flag `-U0` is absolutely incredible

It disables the context from the diff command

## Examples

### Without the flag

The normal `git show <hash-commit>` would show something like this:
```diff
diff --git a/20220405220326/README.md b/20220405220326/README.md
index 9075080..378006a 100644
--- a/20220405220326/README.md
+++ b/20220405220326/README.md
@@ -1,20 +1,20 @@
 # searching unordered words on a phrase with amazon open search

 -I'm having a lot of problems to achieve this goal, I basically ran into
 -a "stable" release for the phrase searches with unordered words But the results
 +I'm having a lot of problems to achieve this goal, I basically ran into a
 +"stable" release for the phrase searches with unordered words. But the results
  tend to be a lot specially with Italian articles like `nel`

   For example If I input `vomito nel sangue` the results will be:
```

### With the flag

You see that lines that are not prefixed by - or +? git provide this to give us some context on where this change was made

But you can use the command `git show <hash-commit> -U0` and get this:

```diff
diff --git a/20220405220326/README.md b/20220405220326/README.md
index 9075080..378006a 100644
--- a/20220405220326/README.md
+++ b/20220405220326/README.md
@@ -3,2 +3,2 @@
-I'm having a lot of problems to achieve this goal, I basically ran into
-a "stable" release for the phrase searches with unordered words But the results
+I'm having a lot of problems to achieve this goal, I basically ran into a
+"stable" release for the phrase searches with unordered words. But the results
@@ -9,9 +9,9 @@ For example If I input `vomito nel sangue` the results will be:
-
```

That way is much more easy to copy and modify like when I'm updating dependencies.


  #git #programming #diff #log #show

