# Exordium
The goal of this project is to provide a static website generator published using [indieweb](http://indiewebcamp.com/) [microformats](http://microformats.org/), suitable for both a personal site or a [special interest group](https://en.wikipedia.org/wiki/Special_Interest_Group). 

I will start by extracting the common elements from [andrewsullivancant.ca](http://andrewsullivancant.ca/) and [kwruby.ca](http://kwruby.ca/).

Integrate with existing projects as much as possible:
* [Middleman](http://middlemanapp.com)
* [webmention.io](https://github.com/aaronpk/webmention.io)
* [webmention client](https://github.com/indieweb/mention-client-ruby)
* [pluto](https://github.com/feedreader/pluto)

# URL Design
This is a map of possible URLs for an exordium website, and so might change over time. URLs may or may not get implemented as time permits.
```
/posts/
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
/identity
  /disambugation
  /avatar
  /gpg
  /resume
    is cirriculum_vitae at better name for this?
      probably because it is not as common as usage
    allow various formats of resume (pdf, word, opendoc)
```

## Research
* https://indiewebcamp.com/URL_design
* http://manas.tungare.name/log/url-design-sins-16-things-that-dont-belong-in-urls/
* https://github.com/Octo-Labs/middleman-alias
* http://tantek.com/w/Whistle

# Ideas
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
* write a plugin for doing draft blog management in branches

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
Copyright 2015 [Andrew Sullivan Cant](http://andrewsullivancant.ca/). Licensed [GPLv3](https://www.gnu.org/licenses/gpl.html), see [LICENSE](LICENSE) for details.

