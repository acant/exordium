# Exordium
Static website generator using indieweb microformats.

I will start by extracting the common elements from [andrewsullivancant.ca](http://andrewsullivancant.ca/) and [kwruby.ca](http://kwruby.ca/).

Integreate with existing projects as much as possible:
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

# License
Copyright 2015 Andrew Sullivan Cant. Licensed GPLv3, see [LICENSE] for details.

