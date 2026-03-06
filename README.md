tree-sitter for [lf filemanager](https://github.com/gokcehan/lf) configed with [lumesh](https://github.com/superiums/lumesh)


start with the following cmd to write lf config with lume:

```bash
#! lumelf
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

## for Helix Editor

```toml
[[language]]
name = "lumelf"
scope = "source.lumelf"
injection-regex = "lumelf"
shebangs = ["lumelf"]

file-types = ["lmf"]
roots = []
comment-token = "#"
indent = { tab-width = 2, unit = "  " }

[[grammar]]  
name = "lumelf"  
source = { git = "https://github.com/superiums/tree-sitter-lumelf", rev = "v0.13.1" }
```

add shebang or rename `lfrc` to `lfrc.lmf` to get highlight
