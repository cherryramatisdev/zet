# how to replace a string on whole git project

Disclaimer: If you're not using git for your project, bro wtf?????


On Linux:
```sh
git grep -l 'original_text' | xargs sed -i 's/original_text/new_text/g'
```

On Mac:
```sh
git grep -l 'original_text' | xargs sed -i '' -e 's/original_text/new_text/g'
```

On Windows:
Bro wtf????

**Another disclaimer: using sed on here is the best way to do it ?**
