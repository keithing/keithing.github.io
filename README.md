## Deployment

This blog is hosted on Github Pages and served from the repository
`keithing.github.io`. This repository contains the necessary elements
to create the blog, but does not have the compiled html. The easiest
way to publish is to clone this respostiory and then clone the blog
into the `public` folder (`public` is added to `.gitignore`).


```bash
git clone git@github.com:keithing/blog.git
cd blog
git clone git@github.com:keithing/keithing.github.io.git public
```

The `public` folder is the default location where the html is compiled.
Essentially `public` is the static web site and everything in this
respository is just used to create the website. To make an update,
make the necessary changes to the elements in the repo and then compile
to `public`.


```bash
# first push changes to /blog
git add --all
git commit -m "Awesome New Post"
git push origin master

# compile site
Rscript -e "blogdown::build_site"

# push compiled changed to /keithing.github.io
cd public
git add --all
git commit -m "Awesome New Post"
git push origin master
```
