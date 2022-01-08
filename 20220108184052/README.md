# vim function to manage scratch buffers

The idea for this is to press a binding and create a scratch buffer with vim file type by default on that scratch buffer I can press one binding to just close it and keeping the content alive, or another binding to erase the buffer and delete it permanently

This is a great opportunity to learn the buffer creation API for vimscript and manage bindings inside those scratch buffers.

**Reference:** <https://github.com/vim-scripts/scratch.vim/tree/master/plugin>

The base is to check if buffer already exists on the first place so we
can create a new one or just open the created one.

```vim
let l:buffer_name = '[Scratch]'
let l:buffer_number = bufnr(l:buffer_name)

if l:buffer_number == -1
	echo "buffer nao existe"
else
	echo "buffer existe"

	exe "split +buffer" . l:buffer_number
endif
```
