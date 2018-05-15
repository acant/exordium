# Exordium
The goal of this project is to provide a static website generator published using [indieweb](http://indiewebcamp.com/) [microformats](http://microformats.org/), suitable for both a personal site or a [special interest group](https://en.wikipedia.org/wiki/Special_Interest_Group).

I will also make use of [convention over configuration](https://en.wikipedia.org/wiki/Convention_over_configuration) and the choice of reasonable defaults, which can be overridden when necessary.

I will start by extracting the common elements from [andrewsullivancant.ca](http://andrewsullivancant.ca/) and [kwruby.ca](http://kwruby.ca/).

Integrate with existing projects as much as possible:
* [Middleman](http://middlemanapp.com)
* [webmention.io](https://github.com/aaronpk/webmention.io)
* [webmention client](https://github.com/indieweb/mention-client-ruby)
* [pluto](https://github.com/feedreader/pluto)

# URL Design
This is a map of possible URLs for an exordium website, and so might change over time. URLs may or may not get implemented as time permits.
```
/
  # figure out a common structure for hompeage based upon
  # https://indieweb.org/homepage
  #   * include vcard with optional additional details
  #   * optional stream with configuration
  #   * think about what other stuff to include
/[yyyy]
  /[mm]
    /[dd]
      /article/[title]
      /notes/[count for day]
      /reply
      /photo
      /rsvp
      /event
      /commit
      /request
      /read
      /pull_request
      /request
        # entry in an issue tracker or ticketing system
        # No sure if issue and pull_request should be seperate.
        # https://indieweb.org/issue_tracker
/articles
/events
/request
/posts/
  # This could contain all posts
/wiki
  /[article name]
    /changes
/tag
  /[tag name]
/git
  /[repo_name]
    /log
    /tags
    /branches
      /[branch_name]
    /[file path]
      /[oid]
/posts
  # feed of all posts
/[each post type]
  # each is a collection for seeing just that post type
  # 
/photo
  # possible endpoints for providing things like galleries and collections of
  # photos
/about
  # Is there any value in putting the identity into is own resource?
  # Yes, because the homepage provides a summary and the this contains more
  # details.
  # I do n0t totally like 'about', but it is so commonly used that it makes
  # sense to continue using it. (alternative names: identity, me, id)
  /disambugation
    # Should this be a seperate page, or just in the about page.
  /avatar
    # display the list of available avatars
    /current
    /[image_hash]
      # default to 80x80
      /[size]
    /[email_hash]
      # provider either re-directs or copies to the images
      # default to 80x80 again
  /gpg
  /resume
    is cirriculum_vitae at better name for this?
      probably because it is not as common as usage
    allow various formats of resume (pdf, word, opendoc)
```

## Questions?
* where should subscrition links go?
  - RSS feed + indieweb idea of a link which is readable and subscribe-able
* www vs no-www for the conical URL
  - https://stackoverflow.com/questions/1109356/www-or-not-www-what-to-choose-as-primary-site-name
  - http://www.yes-www.org/why-use-www/

## Research
* https://indiewebcamp.com/URL_design
* http://indiewebcamp.com/permalinks
* http://manas.tungare.name/blog/url-design-sins-16-things-that-dont-belong-in-urls/
* https://github.com/Octo-Labs/middleman-alias
* http://tantek.com/w/Whistle
* https://github.com/homesteading
* http://www.yes-www.org/
* http://no-www.org/
* https://aaronparecki.com/2018/03/12/17/building-an-indieweb-reader

### Git repository displays
* [GitHub](http://github.com)
* [Gitlab](http://gitlab.com)
* [cgit](http://git.zx2c4.com/cgit/)
* [stagit](http://git.2f30.org/stagit/)
* [sourcegraph](https://src.sourcegraph.com/sourcegraph)
* indieweb has some note about this
  - http://indiewebcamp.com/issue_tracker
  - http://indiewebcamp.com/code
* microformats to create
  - hTicket
  - hRepository
  - http://indieweb.org/git
  - http://indieweb.org/code
  - http://indieweb.org/issues
  - http://indieweb.org/issue
* [patch work](https://github.com/getpatchwork/patchwork)
  - a git tool for managing mailing list patches on the web as well
  - http://jk.ozlabs.org/projects/patchwork/


# Ideas
* every feed to posts should include 
  - HTML5 indieweb microformat feed
  - RSS
  - iCal
* https://github.com/statonjr/middleman-sitemap
* gpg publishing
  - looks like it can work with [indieauth](https://indieauth.com/gpg)
  - http://indiewebcamp.com/pgp
  - [hawkpost.co](https://hawkpost.co/), a system for sending GPG encrypted
    messages from people who do not have GPG setup, uses [OpenPGP.js](http://openpgpjs.org/)
* static file encryption with GPG
  - http://git-annex.branchable.com/encryption/
  - http://git-annex.branchable.com/design/encryption/
  - http://obnam.org/encryption/
  - https://github.com/ahoward/middleman-gibberish
  - can the webauthn API help with using GPG de-cryption in the browser?
* separate command/control services from static publishing service
  - authenticate publicly accessible command services with client certificates
    * http://blog.nategood.com/client-side-certificate-authentication-in-ngi
  - consider including a micropub interface
  - consider too to help with content creation
    * automated spelling, grammar, proofreading, reading quality
    * meta data suggestions (e.g.,
      [HashRobot](https://blog.monkeylearn.com/hashrobot-a-social-media-assistant-built-with-monkeylearn/)
  - https://github.com/yabwe/medium-editor
* create helpers for setting site license (CC, PD, all reserved)
* create a consistent identity structure
  - integrate with namecoin
  - handle multiple and deprecated email addresses
  - disambugation pages
  - xfn related things
  - webfinger
  - indieauth
  - openid
* avatar support and POSSE
  - save all avatars which have been used, and provide a browsing page
  - specify the current avatar for the site
  - POSSE, default or an overridden, avatar to
    * gravatar
    * twitter
    * linkedin
  - provide libravatar support
* add public GPG key publishing
  - keep all keys including revoked onces with their revokation certificates
  - associate with appropriate email address
  - point to the appropriate default key for communication
* implement [POSSE](https://indiewebcamp.com/POSSE) to various other services
  - [Twitter](http://twiter.com)
  - [Meetup](http://meetup.com)
  - [LinkedIn](http://linkedin.com)
  - [medium](http://medium.com)
    * http://www.elezea.com/2016/02/medium-as-rss-reader/
  - [image sizes on various services](http://www.entrepreneur.com/article/225761)
  - initially implement to be executed from a workstation/laptop
    * this will avoid having to worry about how to store credentials on the
      network
    * investigate a secure way to do this in the future
  - [SNAP wordpress extensions](https://www.nextscripts.com/social-networks-auto-poster-for-wordpress/)
* investigate storing POSSE and webmention information in data-branches
* get push notifications working
  - [PubSubHubbub](http://indiewebcamp.com/PubSubHubbub)
  - http://christopheducamp.com/w/PubSubHubbub?christopljw_session=mke14ssbovehvdo6tq94bpff44
  - other formats to use?
* easy SSL with [lets encrypted](https://helloworld.letsencrypt.org/)
* adding an easy option for deploying to various sites:
  - [internet archive](https://archive.org/) Wayback Machine
  - P2P networks (e.g., [IPFS](http://ipfs.io/))
  - S3
  - github pages
  - CloudFlare
  - rsync
  - ftp
  - [google amp](https://www.ampproject.org/)
    * [Amplify for Jekyll](https://github.com/ageitgey/amplify)
  - [facebook instance articles](https://developers.facebook.com/docs/instant-articles)
  - [google shield](https://jigsaw.google.com/products/project-shield/)
  - [Scuttlebut social network]
* make it easy to add a [.onion](https://en.wikipedia.org/wiki/.onion) address
* write a plugin for doing draft blog management in branches
* add link checking and wayback machine support for content and links
  - check links regularly
  - link to the wayback machine in content if the original page disappears
  - can I send pages I link to to the wayback machine?
    * yes http://lifehacker.com/manually-archive-web-pages-by-submitting-them-to-the-wa-1580713309
* add support for auto filling different kinds of links
  - investigate if this would work in Markdown or now
  - easy links to things like
    * internal pages
    * wikipedia
    * github
    * public contact/person information
* publish contacts and membership with XFN and rel tags
  - http://microformats.org/wiki/rel-group
  - think about what level of privacy would be appropriate?
    * who should be able to access what
    * how to authenticate (indieauth with the related page, GPG encryption)
* search
  - use a client side javascript search
  - http://manas.com.ar/blog/2015/10/22/middleman-search-client-side-search-in-your-middleman-site.html
* allow code examples to be stored in separate files and inlined into articles
  - this should make it easier to check and execute the code
  - would this then need to include a gist like system?
* look into integrating the mermaid diagraming tool
* add support for including code snippets as separate files which are include
  into articles
* make it easy to do mentions in articles/wiki/etc
  - https://seblog.nl/2017/06/14/6/at-mentioning-people
* things to [PESOS](https://indieweb.org/PESOS)
  - [OpenStreetMap](https://www.openstreetmap.org/)
  - [MusicBrainz](https://musicbrainz.org/)
  - [Wikipedia](https://www.wikipedia.org/)
* figure out how to publish events and session
  - both allow events to be created, this could be [PESOS](https://indieweb.org/PESOS) from other places
  - example https://aaronparecki.com/presentations
  - and POSSE to other sites
    * https://www.slideshare.net/
    * https://slidr.io/aspleenic/rails-still
* include vcard list with exordium, for linking to others
  - https://indieweb.org/nicknames-cache
  - use ppl to manage it
* support posting and subscription over email
  - how to make it easy
    * have a paid which is the default
    * and easy support for something self-hosted
  - consider using gitlab CI
  - allow posting by email, maybe something like matrix as well
* pick a method for doing slides with works well with this
  - https://github.com/geraldb/talks/blob/master/slideshow-s9.md
* describe at least one method for CI/CD/automatic deploying
  - GitlabCI
  - https://github.com/alestic/aws-git-backed-static-website

## HTML5/Microformats

* for git repository
  - consider flag to indicate intended usage (e.g., for use, clone only, deprecated)
  - want to integrate web comments on all parts of the repo
    * e.g., commits, lines, PRs
  - would like to integrate display of related wiki and issues
  - also include an intent flag
    * prototype
    * clone
    * deprecated
    * for_use
    * what else?
  - generate arbitrary diffs in the browser using web worker + [git.js](https://github.com/creationix/js-git)
* for projects
  - want to be able to go all the way from idea to full running project
  - embed list of links and tickets
  - and then allow links out to the same later on
  - this will be useful for 
  - http://microformats.org/wiki/h-product
  - http://microformats.org/wiki/project
  - https://github.com/ewilderj/doap/wiki
  - http://microformats.org/wiki/project-formats
* use a HTML5 structure with main and related structure tags
  - https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Using_HTML_sections_and_outlines

## Wiki
* add category support, like wikipedia

#Inspiration
This to review for ideas:
* https://github.com/crtvhd/middleboy
* https://github.com/gregory/middleman-settings
* [Locking the Web Open: A Call for a Distributed Web](http://brewster.kahle.org/2015/08/11/locking-the-web-open-a-call-for-a-distributed-web-2/)
  - javascript (e.g., [client side search engine](https://github.com/cebe/js-search))
  - bitcoin
  - IPFS/bittorrent
  - Namecoin
  - public/private keys
* investigate pushing git repos or projects to aggregators
  - openhub
  - github
  - gitlab
  - bitbucket
  - rubytoolbox
  - article on this topic by [flameeyes](https://flameeyes.eu), [Project Memory](https://blog.flameeyes.eu/2017/04/project-memory/)
* [Autotune](http://product.voxmedia.com/2015/7/8/8907841/introducing-autotune) Vox Media's middleman based CMS
* [Ain't CMS](http://aint.io/)

# License
Copyright 2015 [Andrew Sullivan Cant](http://andrewsullivancant.ca/). Licensed [GPLv3](https://www.gnu.org/licenses/gpl.html), see [LICENSE](LICENSE) for details.
