# verb [![NPM version](https://badge.fury.io/js/verb.png)](http://badge.fury.io/js/verb)

> A project without documentation is like a project that doesn't exist. Verb solves this by making it dead simple to generate docs, using simple markdown templates, with zero configuration required.

Verb is a new project, please give feedback on your experience so we can improve it! See [what's planned for v0.3.0](https://github.com/assemble/verb/issues/12), feel free to add your thoughts or ask questions there as well.

## Runners
**Verb itself is just an API**, so it requires a "runner" to run.
Currently, there are three Verb runners to choose from:

* [verb-cli](https://github.com/assemble/verb-cli) runs Verb globally from the command line
* [grunt-verb](https://github.com/assemble/grunt-verb) for your favorite JavaScript task runner.
* [gulp-verb](https://github.com/assemble/gulp-verb) for your streaming build systems.

Those tools are great for building docs once they already exist, but you can also use [generator-verb](https://github.com/assemble/generator-verb) to:

* Initialize new Node.js projects _with documentation read-to-go_. This is a great generator for Node.js projects in general, even if you don't want to use Verb!
* Add docs templates to new or existing projects

Read [the documentation](./DOCS.md) to learn more about Verb!


## Install
Install with [npm](npmjs.org):

```bash
npm i verb --save
```


## Meet Verb
> Verb's CLI makes kickstarting new markdown documentation a breeze.

For example, to [generate a readme](https://github.com/assemble/generator-verb) for your project just add `docs/README.tmpl.md` with the following:

```markdown
# {%= name %}

> {%= description %}

Sed ut perspiciatis unde omnis iste natus error sit voluptatem
accusantium doloremque laudantium, totam rem aperiam.
```

Then run `verb` in the command line and it will generate `README.md`, _automatically using data from your project's package.json to process templates_.

**[Built-in tags](./DOCS.md#tags)**

Need more than simple variables, like `date()`? Use one of Verb's [built-in tags](./DOCS.md#date):

```markdown
## License
Copyright (c) {%= date('YYYY') %} {%= author.name %}, contributors.
Released under the {%= license.type %} license
```

**[Includes](./DOCS.md#include)**

Easily include other documents. To use any markdown file in the `docs/` directory just use [`{%= docs() %}`](./DOCS.md#docs):

```markdown
## Contribute
{%= docs("contributing") %}
```

That's it! [See this gist](https://gist.github.com/jonschlinkert/9712957) for a more detailed example.

This is just a simple example though, Verb can easily build multi-page markdown documentation, with a fully-linked [multi-page TOC](./DOCS.md#toc), or even build a book!

_(Verb builds its own docs (WIP) too, check progress in the [docs directory](./docs)!)_.



## Customize
Verb is easy to extend, here are some examples ([verb-cli](https://github.com/assemble/verb-cli) will automatically use these):

* [example verbfile](https://gist.github.com/jonschlinkert/9685280), with custom `src`, `dest` and metadata.
* [example verbfile with logging](https://gist.github.com/jonschlinkert/9685144)
* [example .verbrc.yml](https://gist.github.com/jonschlinkert/9686195)

You can also use Verb as a basis for creating your own documentation generator!

## Test
Run Verb's 75+ unit tests:

```bash
mocha -R spec
```

## Release history
**DATE**       **VERSION**   **CHANGES**                                                        
* 2014-03-29   v0.2.0        Changes the delimiter escaping format to be similar to Yeoman.,Adds
                             documentation. Fixes and adds tests for front matter.              
* 2014-03-10   v0.1.0        First commmit.                                                     

## Contribute
All contributions are welcome! _Stars and tweets_ are always a great way to show your support! But we can definitely use some help with:

* [documentation](./docs)
* [writing unit tests](./test)
* [addressing issues](https://github.com/assemble/verb/issues)

Please read [contributing guide](CONTRIBUTING.md) for more info!

## Author

**Jon Schlinkert**

+ [github/jonschlinkert](https://github.com/jonschlinkert)
+ [twitter/jonschlinkert](http://twitter.com/jonschlinkert)

## License
Copyright (c) 2014 Jon Schlinkert, contributors.  
Released under the MIT license

***

_This file was generated by [verb-cli](https://github.com/assemble/verb-cli) on May 22, 2014._