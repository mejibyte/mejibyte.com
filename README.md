# mejibyte.com

This is the source code of my personal website: https://www.mejibyte.com.

It is written in Jekyll and hosted on GitHub Pages.

## Notes to self

### Testing locally before committing

```
$ ./server.sh
```

### Customizing theme

```
$ open $(bundle info --path minima)
```

Then copy any file from that directory to local repo. For example:

```
$ cp $(bundle info --path minima)/_includes/header.html ./_includes/header.html
```

More details: https://jekyllrb.com/docs/themes/#overriding-theme-defaults