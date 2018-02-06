# The ForSyDe public page

This repository generates the public face of ForSyDe, using the [Jekyll](https://jekyllrb.com/) static site generator. Read these instructions carefully before proceeding to modify things.

## Installation

The site at https://forsyde.github.io/ is re-generated every time someone pushes to the `master` branch. This means that it would be wise to render it locally and verify it on `localhost:4000` before any changes are commited publicly.

First you need to install [Jekyll](https://jekyllrb.com/docs/installation/) and other dependencies. On Ubuntu, you would do

    # install make and gcc
    sudo apt install build-essential
	
	# install Ruby
	sudo apt install ruby-all-dev
	
	# build Jekyll
	sudo gem install jekyll bundler
	
	# set up this site
	cd path/to/this/repo
    bundle install

In order to start the preview server, run

    bundle exec jekyll serve
	
Visit [`localhost:4000`](http://localhost:4000) in your browser to preview the theme.

## Usage

There are several ways to tweak the contents of the web site without getting your hands dirty in the source code. For more elaborate changes in the behavior, style or layout of the site, please contact the repository maintainer.

### Configuration

The `_config.yml` file contains the main configuration parameters available throughout the site, following the [YAML](https://en.wikipedia.org/wiki/YAML) syntax, roughly: 

    name: value

The variable names should be documented or self-explanatory. 

### Adding a new page

The main content of the web site can be found under the `pages` folder. The pages can be written in Markdown, Texile or plain HTML. Check the [Markdown cheatsheet](cheatsheet.md) for syntax tips, and the [Jekyll help page](https://jekyllrb.com/docs/posts/) for more tricks. Regardless of the format, each page file *needs to have a preamble*, aliong the lines of:

    ---
	variable: value
	---
	
	{ main content }

The page variables are:

 * `title`: the page title, shown as the window title. 
 * `layout`: the page layout and style. The currently available layouts are `default` and `empty`.
 * `permalink`: the permanent relative link of the generated HTML within the site, regardless of the original file name or path. If left empty, the page will need to be referenced with its full path within the repository directories, e.g. for `<repo_root>/pages/news/news.md` the link would be `<domain>/pages/news/news.html`.
 * `top-navbar`: Adds a link to this page on the top navigation bar. Default is `false`.
 * `toc`: Creates a page navigation bar in the right side of the web page. Default is `true`.
 * `folder`: The relative path under the `docs` directory, for easy navigation. Default is `./`.

### Site resources

The current site resources are images which are found under the `assets` and `images` folders.

### Writing news / blogging

A news article is just a normal source page (usually Markdown), that:

 * needs to be placed under the `_posts` directory;
 * needs to follow the naming convention `YEAR-MONTH-DAY-title.MARKUP`, e.g. `2012-09-12-how-to-write-a-blog.md`. 
 * needs to have a document preamble like any other page. Apart from the usual variables, the following also apply:
   - `date`: for a more fine-grained manipulation of the date, e.g. `2015-11-17 16:16:01 -0600`
   - `categories`: the category of the news article. The recommended categories are `news, updates, release notes, announcements`. Before making a new category make sure you *really need it*! Also, check the spellig.
   
In case you added categories, to generate the new page structure, run the script
   
    ./script/tagbuild

### Writing drafts

Similar to posts, there exists a `_drafts` folder where you can write test or work-in-progress pages without actually publishing them. To check how the site looks you need to run the preview server with the `--drafts` switch:

    bundle exec jekyll serve --drafts

### Adding BIB references

To add bibliographic references to the [Publications](https://forsyde.github.io/publications.html) page, you need to update the `.bib` file found at `assets/bib/references.bib`. Again, pay close attention to the spelling, especially when it comes to the `categories` field. The recommended categories are: `analysis and dse, modeling, simulation, adaptivity, design flow, synthesis, refinement, verification`. After this, you need to generate the appropriate pages with:

    ./script/make-publication-list

### Running CI tests

The theme contains a minimal test suite, to ensure a site with the theme would build successfully. To run the tests, simply run 

    ./script/cibuild
