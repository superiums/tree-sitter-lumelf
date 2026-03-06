tree-sitter for [lf filemanager](https://github.com/gokcehan/lf) configed with [lumesh](https://github.com/superiums/lumesh)


start with the following cmd to write lf config with lume:

```bash
set ifs '\n'
set shellopts '-sM'
set shell /usr/bin/lume
set filesep "\n"

```

example config:
```bash
cmd toggle-preview %{{
    match $lf_preview {
        'true' => lf -remote `send $id :set nopreview; set ratios 1:5`
        _ => lf -remote `send $id :set preview; set ratios 1:2:3`
    }
}}
map zp toggle-preview
```
