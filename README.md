# Standard
Standardized project structure and build tools for use by serverless JavaScript
applications.

## Project layout
- Project related files in root:
    - README
    - Gitignore
    - Build related files
- Assets in `src/`
- Entire project builds into `dist/`
- Static content copied into `dist/` (and optionally optimized along the way)
- Spritemap generated and copied to `dist/img/sprite.png`
- Shared CSS bundled into `dist/css/shared.css`
- Page CSS bundled as necessary into `dist/css/page.css`
- Vendor + shared JS bundled into `dist/js/shared.js`
- Page JS pages bundled as necessary into `dist/js/page.js`

### Fonts, Images copied
```
src/font/*                     ---> dist/font/*
src/img/*                      ---> dist/img/*
```

### Spritemap generated
```
src/img/sprite/1.png           ---> dist/img/sprite.png
src/img/sprite/2.png          /---> .tmp/sprite.css
src/img/sprite/3.png         /
```

### Shared CSS bundled
```
src/css/index.styl             ---> dist/css/shared.css
src/css/a.styl                /
src/css/b.styl               /
node_modules/dep/dep.styl   /
.tmp/sprite.css            /
```

### Page-specific CSS bundled
```
src/css/page/index.styl        ---> dist/css/page.css
src/css/page/a.styl           /
src/css/page/b.styl          /
```

### Vendor concatenated
```
src/js/vendor/jquery.js        ---> .tmp/vendor.js
src/js/vendor/a.js            /
src/js/vendor/b.js           /
src/js/vendor/c.js          /
src/js/vendor/d.js         /
```

### Shared JS bundled
```
src/js/index.coffee            ---> .tmp/shared.js
src/js/a.coffee               /
src/js/b.coffee              /
src/js/c.coffee             /
node_modules/dep/dep.js    /
```

### Concat vendor + shared bundle
```
.tmp/vendor.js                 ---> dist/js/shared.js
.tmp/shared.js                /
```

### Page-specific JS bundled
```
src/js/page/index.coffee       ---> dist/js/page.js
src/js/page/a.coffee          /
src/js/page/b.coffee         /
src/js/page/c.coffee        /
node_modules/dep2/dep2.js  /
```
