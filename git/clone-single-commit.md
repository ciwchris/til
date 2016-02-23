Clone single commit
===================

Many times when cloning a repo the entire repo is not needed. In this case the number of commits to
clone can be specified using the `depth` flag.

```
git clone --depth 1 https://github.com/some-user/some-project
```

I've heard this mentioned previously but saw it used in an ideal scenario in the [angular2-webpack-starter repo README](https://github.com/AngularClass/angular2-webpack-starter).
