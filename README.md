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
      /pull_request
      /read
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
/photo
  # possible endpoints for providing things like galleries and collectios of
  # photos
/about
  # Is there any value in putting the identity into is own resource?
  # Yes, because the homepage provides a summary and the this contains more
  # details.
  # I do n0t totally like 'about', but it is so commonly used that it makes
  # sense to continue using it. (alternative names: identity, me, id)
  /disambugation
  /avatar
    # display the list of available avatars
    /current
    /[image_hash]
      # default to 80x80
      /[size]
    /[email_hash]
      # providier either re-directs or copies to the images
      # default to 80x80 again
  /gpg
  /resume
    is cirriculum_vitae at better name for this?
      probably because it is not as common as usage
    allow various formats of resume (pdf, word, opendoc)
```

## Research
* https://indiewebcamp.com/URL_design
* http://indiewebcamp.com/permalinks
* http://manas.tungare.name/blog/url-design-sins-16-things-that-dont-belong-in-urls/
* https://github.com/Octo-Labs/middleman-alias
* http://tantek.com/w/Whistle
* https://github.com/homesteading
* http://www.yes-www.org/
* http://no-www.org/

### Git repository displays
* [GitHub](http://github.com)
* [Gitlab](http://gitlab.com)
* [cgit](http://git.zx2c4.com/cgit/)
* [sourcegraph](https://src.sourcegraph.com/sourcegraph)
* indieweb has some note about this
  - http://indiewebcamp.com/issue_tracker
  - http://indiewebcamp.com/code

# Ideas
* https://github.com/statonjr/middleman-sitemap
* gpg publishing
  - looks like it can work with [indieauth](https://indieauth.com/gpg)
  - http://indiewebcamp.com/pgp
* static file encryption with GPG
  - http://git-annex.branchable.com/encryption/
  - http://git-annex.branchable.com/design/encryption/
  - http://obnam.org/encryption/
  - https://github.com/ahoward/middleman-gibberish
* separate command/control services from static publishing service
  - authenticate publicly accessible command services with client certificates
    * http://blog.nategood.com/client-side-certificate-authentication-in-ngi
  - consider including a micropub interface
  - consider too to help with content creation
    * automated spelling, grammar, proofreading, reading quality
    * meta data suggestions (e.g.,
      [HashRobot](https://blog.monkeylearn.com/hashrobot-a-social-media-assistant-built-with-monkeylearn/)
  - https://github.com/yabwe/medium-editor
* microformat standard for git repository
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
  - [facebook instance articles](https://developers.facebook.com/docs/instant-articles)
  - [google shield](https://jigsaw.google.com/products/project-shield/)
* write a plugin for doing draft blog management in branches
* add link checking and wayback machine support for content and links
  - check links regularly
  - link to the wayback machine in content if the original page disappears
  - can I send pages I link to to the wayback machine?
    * yes http://lifehacker.com/manually-archive-web-pages-by-submitting-them-to-the-wa-1580713309

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

# License
Copyright 2015 [Andrew Sullivan Cant](http://andrewsullivancant.ca/). Licensed [GPLv3](https://www.gnu.org/licenses/gpl.html), see [LICENSE](LICENSE) for details.
