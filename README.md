# Personal homepage site builder

## To update information

1. Update the `config.toml`
2. Check updates in local environment via `hugo server`
3. Generate site with `hugo` command
4. Manually copy site to hosting

# To write new post by template

`hugo new --kind post <name>`


# Maintenance notes

## Theme update

On first clonning I need:

```
git submodule update --init --recursive
```

To update theme files:

 ```
 git submodule update --remote --merge
 ```
