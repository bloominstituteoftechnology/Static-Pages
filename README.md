# Static-Pages
Guide/comparison of ways to create and host static pages

## What is a static webpage?
Any webpage where all the content (HTML, JavaScript, CSS, images) is loaded in
and rendered by the user's browser ("front-end"). There are some important
benefits and limitations of this:

- *Can* host freely/cheaply at a bunch of places, deploy and switch hosts easily
- *Can* 
- *Can't* persist user data across sessions/devices (or need to rely on external service to do so)
- *Can't*

Static just means "unchanging", and overall that's what static webpages are good
for - content that doesn't change. However, front-end frameworks like
[React](https://github.com/facebook/react) have blurred the lines a bit, and you
can have a front-end application that is static from a code/infrastructure
perspective but is still dynamic and engaging to the user. So get creative! Take
advantage of the many tools and services available, and you can build an awesome
webpage that maximizes the advantages and minimizes the disadvantages of being
static.

## How can I build a static webpage?
The simplest thing to do is just build it "by hand" - that is, use a text editor
and write .html, .css, and .js files to your hearts content. This "back to
basics" approach can be appropriate for things that are really simple, really
won't need lots of updates, and also if you're just feeling nostalgic or want to
reinforce your knowledge on the basics (which helps with everything else).

For more substantial and/or frequently updated pages, it's a good idea to use a
static site generator - a tool that renders all the actual HTML/JS/CSS based on
templates, parameters, and usually
[Markdown](https://daringfireball.net/projects/markdown) files for the actual
content. There is an absurd number of these generators, you can
[check out popular ones here](https://www.staticgen.com).

With many options come many opinions, but in general you can't go wrong with
anything that is well-maintained and has a good community around it. It's also a
good idea to pick something that is either in a language/framework that you know
about or are interested in learning more - as you start to try to customize your
page you'll find yourself digging in to how the generator actually works, so
it's good to choose accordingly.

Some top highlights:

- [Jekyll](https://jekyllrb.com) - Ruby, it's been around (mature/stable), and
is what actually powers GitHub pages if you just push Markdown files (see also:
[Octopress](http://octopress.org)).
- [Hexo](https://hexo.io) - Node.js, essentially a JavaScript take on Jekyll
(compatible with the same Markdown and similar plugin ecosystem).
- [Hugo](http://gohugo.io) - Go, *extremely fast*, great for generating *big*
sites. Also just a single binary, so no need to mess with package management or
dependencies for installation.
- [Pelican](https://blog.getpelican.com) - Python, supports a variety of content
formats and integrates/imports from WordPress and others.
- [Gatsby](https://github.com/gatsbyjs/gatsby) - React, creates a "dynamic"
static site (a Single Page Application where everything is loaded on the initial
request and further clicking/browsing doesn't refresh the page).
- [Brunch](http://brunch.io) - JavaScript, not really a blog generator like the
above but rather a build tool/pipeline to simplify making a modern static site.

## How/where can I deploy a static webpage?
One of the big advantages of static webpages is the ease and flexibility of
deployment. To deploy all you do is copy the files to the server that serves
them - that's it! The only dependency is a basic webserver that listens to and
returns basic HTTP requests. You can of course build/deploy your own server (and
that is an excellent exercise), but for our purposes here we'll consider some of
the many excellent free/cheap services that do this for you.

### GitHub Pages
[GitHub Pages](https://pages.github.com) are a great way to get started, and
actually still a strong choice as you scale up. It's a free service, but can
handle substantial traffic, supports custom URLs/domains, and gives SSL. The
deploy process is simple - just enable GitHub Pages in the settings page for
your repository. You have a few options:

- Use the `master` branch - this means any content in the master branch of
`github.com/user/repo/` will be served from `user.github.io/repo/`. Good for
repos that are entirely meant to be webpages.
- Use the `gh-pages` branch - content in `gh-pages` will be served per the same
URLs as above. Good for repos that use a tool/template to generate the page (you
save that to your `master` branch and save the built output to `gh-pages`).
- Use the `/docs` folder on the master branch - good for non-webapp projects
(e.g. tools, games, etc.) where you want to serve the documentation as a page.

This particular repository is using the first approach, so you can read this
very file from [https://lambdaschool.github.io/Static-Pages/](https://lambdaschool.github.io/Static-Pages/)
(if you're not already).
