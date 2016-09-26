# Introduction

This repository contains some example code for Urbit. There are
generators (short `:dojo` commands) in `dojo/`, web pages generated by
`%ford` in `web/`, `%gall` applications in `gall/` and libraries (to be
loaded into `:dojo`) in `libs/`.

# Installation

Clone this repo somewhere. Let's call it `/examples/path`.

On a running urbit `~your-urbit` create a separate desk (branch) to run
the examples:

    ~your-urbit:dojo> |merge %sandbox ~your-urbit %home

Then mount your `%sandbox` desk to Unix:

    ~your-urbit:dojo> |mount /=sandbox=

If your Urbit was installed at `/urbit/path` now you can find your
`%examples` desk at `/urbit/path/your-urbit/sandbox`.

To copy in all the generators:

    cp -r /examples/path/dojo/*/* /urbit/path/your-urbit/sandbox/

To run your first generator:

    ~your-urbit:dojo> :: switch to your %sandbox desk
    ~your-urbit:dojo> =dir /=sandbox=
    ~your-urbit:dojo/sandbox> +examples/euler1 2

To copy in all the web pages:

    cp -r /examples/path/web/*/* /urbit/path/your-urbit/sandbox/

You should be able to find them at
`http://localhost:8080/pages/examples/1` or similar.

Have your Urbit serve from the `%examples` desk:

    ~your-urbit:dojo/sandbox> |serve %examples

To copy in all the apps:

    cp -r /examples/path/gall/*/* /urbit/path/your-urbit/sandbox/

Apps are also inside `examples/` directories, but we use `-`.

Start the `%click` app:

    ~your-urbit:dojo> |start %examples %examples-click

`%click` also has a frontend at
`http://localhost:8080/pages/examples/click`.

To copy in all the libraries:

    cp -r /examples/path/libs/*/* /urbit/path/your-urbit/sandbox/

Load the [99 Lisp
Problems](http://www.ic.unicamp.br/~meidanis/courses/mc336/2006s2/funcional/L-99_Ninety-Nine_Lisp_Problems.html):

    ~your-urbit:dojo> :: switch to your %sandbox desk
    ~your-urbit:dojo> =dir /=sandbox=
    ~your-urbit:dojo/sandbox> /+  lisp99

Run the test:

    ~your-urbit:dojo/sandbox> test:lisp99

# Contributing / Feedback

PRs, comments and issues are more than welcome. If you need help the
best channel is to `:join ~dozbud/urbit-meta` on Urbit, but you can also
email `urbit@urbit.org` or tweet at `@urbit_`.
