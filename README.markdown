Puppet Docs
===========

Curated documentation for Puppet, and tools for generating a deployable copy
of the docs site.

Installation
------------

The tools and rake tasks for generating the puppet-docs site require Ruby 1.8.7.

To install the documentation-generating code:

1.  Clone the repository:

        $ git clone git://github.com/puppetlabs/puppet-docs.git

2.  Add the mcollective documentation:

        $ git submodule update --init

2.  Use your package manager to install rake, libxml2-dev,
    libxslt-dev, and pygments.  Package names may vary by platform; for example,
    using Macports, these packages could be installed with:

        $ sudo port -d install rb-rake libxml2 libxslt py-pygments

3.  Install the ruby dependencies:

        $ sudo rake install

Building and Viewing
--------------------

1.  Generate the documentation:

        $ rake generate

2.  Start a little server to view it at http://localhost:9292:

        $ rake serve

    (You can use `rake run` to combine these steps.)

Build Generated Docs For A Given Puppet Version
-----------------------------------------------

    $ VERSION=0.25.0 rake references:puppetdoc

Build Updated HTML Manpages
---------------------------

    $ PUPPETDIR=~/Documents/puppet rake update_manpages

You will need to point the PUPPETDIR environment variable at a git checkout of
the Puppet code. Currently, we only maintain a single version of the manpages,
and this task will only work cleanly with Puppet 2.7 or higher. Unlike
generating references, this task is not currently run on a set schedule.

Generate a PDF or Other Single-File Documentation
-------------------------------------------------

    (update page order)
    $ rake generate_pdf
    $ rake serve_pdf
    (replace '-latest-' in index.html with literal
        latest version, e.g. '-2-6-7-')
    (point PDF-generating tool at localhost:9292)

See pdf_mask/README.txt for more details.

Errors and Omissions
--------------------

If something in the documentation doesn't seem right -- or if you
think something important is missing, please [submit a ticket][1] to
[the "puppet-docs" project][1] (not to Puppet itself).  The best way
to get your change in is to contribute it; see the next section for
details.

NOTE: If you're talking about additional content, keep in mind that it might
make more sense to be on the [Wiki][2].  You might want to start by
adding it there.

Contributing Changes
--------------------

* Fork the project (we recommend [GitHub][3])
* Make sure you read the writing guide (README_WRITING.markdown) and the 
style and usage guide, which are both in the root of this project.
* Make your documentation addition/fix -- preferably in a branch.
* If you're fixing or adding features to the generation
  infrastructure, add some passing specs.
* Commit, do not mess with the README, LICENSE, etc.
* [Submit a ticket][1] requesting your contribution be added, and make
  sure you note the location of the repository and branch.

[1]: http://projects.puppetlabs.com/projects/puppet-docs
[2]: http://projects.puppetlabs.com/projects/puppet/wiki/
[3]: http://github.com
[4]: http://docs.puppetlabs.com/guides/style_and_usage.html

Copyright
---------

Copyright (c) 2009-2011 Puppet Labs. See LICENSE for details.


