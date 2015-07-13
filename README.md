# Exordium
The goal of this project is to provide a static website generator published using [indieweb](http://indiewebcamp.com/) [microformats](http://microformats.org/), suitable for both a personal site or a [special interest group](https://en.wikipedia.org/wiki/Special_Interest_Group). 

I will start by extracting the common elements from [andrewsullivancant.ca](http://andrewsullivancant.ca/) and [kwruby.ca](http://kwruby.ca/).

Integrate with existing projects as much as possible:
* [Middleman](http://middlemanapp.com)
* [webmention.io](https://github.com/aaronpk/webmention.io)
* [webmention client](https://github.com/indieweb/mention-client-ruby)
* [pluto](https://github.com/feedreader/pluto)

# Ideas
* static file encryption with GPG
  - http://git-annex.branchable.com/encryption/
  - http://git-annex.branchable.com/design/encryption/
  - http://obnam.org/encryption/
  - https://github.com/ahoward/middleman-gibberish
* authenticate publicly accessible command services with client certificates
  - http://blog.nategood.com/client-side-certificate-authentication-in-ngi
* microformat standard for git repository
  - consider flag to indicate intended usage (e.g., for use, clone only, deprecated)
* create helpers for setting site license (CC, PD, all reserved)
* create a consistent identity structure
  - integrate with namecoin
  - handle multiple and deprecated email addresses
  - libavatar/gravatar integrations
  - gpg key publishing
  - disambugation pages
  - xfn related things
* implement [POSSE](https://indiewebcamp.com/POSSE) to various other services
  - twitter, meetup, linkedin
  - [image sizes on various services](http://www.entrepreneur.com/article/225761)
* get push notifications working
  - [PubSubHubbub](http://indiewebcamp.com/PubSubHubbub)
  - other formats to use?

# License
Copyright 2015 Andrew Sullivan Cant. Licensed GPLv3, see [LICENSE] for details.

