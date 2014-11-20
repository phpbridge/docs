# The PHPBridge Documentation Project

[![Build Status](https://travis-ci.org/phpbridge/docs.png)](https://travis-ci.org/phpbridge/docs)

## Lovingly Based on RailsBridge

Thanks to the amazing work of the volunteers behind [RailsBridge](http://railsbridge.org) and their
decision to release all of their content under a Creative Common (CC-BY) license, we are able to create
PHPBridge by standing on their shoulders and building up.

## Overview

This is a Sinatra app, deployed at <http://docs.railsbridge.org>. The PHPBridge documentation project is home to a few subprojects, including the PHPBridge installfest instructions, which leads students through the various complicated setup instructions for getting PHP, MySQL, Git, etc. installed on their computer (whatever combination of computer, OS, and version they happened to bring to the workshop!), as well as the PHPBridge workshop "Suggestotron" curriculum.

Each subproject (a "site") comprises files stored under the "sites" directory; for instance, the installfest instructions are located at ROOT/sites/en/installfest, while the intro PHP curriculum can be found under ROOT/sites/en/intro-to-php.

These files can be in any of these formats:

* `.step` for [StepFile](step_file_reference.md)
* `.md` for [Markdown](http://daringfireball.net/projects/markdown/syntax)
* `.mw` for MediaWiki (temporary)
* `.deck.md` for [deck.rb](https://github.com/alexch/deck.rb)

(If multiple files exist with the same base name, `.step` is preferred over `.md`, and `.md` over `.mw`.)

## Usage

    bundle install
    rake run

If the above fails (say, because `rerun` doesn't work on your system), try

    rackup

Then open <http://localhost:9292> in a web browser, and verify that you can navigate the installfest slides.

## Locales

To serve sites from "sites/en", use `rake run` or a vanilla deploy.

To server sites from another locale (say, "es" or Spanish)...
  * Locally, use the SITE_LOCALE environment variable: `SITE_LOCALE=es rake run`
  * On a server, make the server respond to a locale subdomain: `http://es.railsbridge.org`
  * Or to temporarily test, use a `locale` or `l` parameter: `http://docs.railsbridge.org/?l=es` (note that in this mode, links are not rewritten, so if they fail you will have to manually add the parameter again)

## Contributing

Check out [CONTRIBUTING.md](CONTRIBUTING.md) to see how to join our [list of contributors](https://github.com/phpbridge/docs/graphs/contributors)!

## Resources

- Workship Organizers see [WORKSHOP.md](WORKSHOP.md)
- [StepFile Reference](step_file_reference.md)
