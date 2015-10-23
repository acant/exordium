# Exordium
Static website generator using [indieweb](http://indiewebcamp.com/) [microformats](http://microformats.org/).

I will start by extracting the common elements from [andrewsullivancant.ca](http://andrewsullivancant.ca/) and [kwruby.ca](http://kwruby.ca/).

Integrate with existing projects as much as possible:
* [Middleman](http://middlemanapp.com)
* [webmention.io](https://github.com/aaronpk/webmention.io)
* [webmention client](https://github.com/indieweb/mention-client-ruby)
* [pluto](https://github.com/feedreader/pluto)

# Ideas
* create a URL design
  - need to come up with a good design that can get the various indieweb types
  - https://indiewebcamp.com/URL_design
  - http://manas.tungare.name/blog/url-design-sins-16-things-that-dont-belong-in-urls/
  - https://github.com/Octo-Labs/middleman-alias
  - http://tantek.com/w/Whistle
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
* easy SSL with [lets encrypted](https://helloworld.letsencrypt.org/)
* adding an easy option for deploying to multiple sites:
  - internet archive
  - P2P networks (e.g., [IPFS](http://ipfs.io/))

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

# License
Copyright 2015 Andrew Sullivan Cant. Licensed GPLv3, see [LICENSE] for details.

