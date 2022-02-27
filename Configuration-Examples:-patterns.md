# `patterns` Examples

```
# this is a comment

# marker to ignore all code on line
^.*/\* #no-spell-check-line \*/.*$
# marker for ignoring a comment to the end of the line
// #no-spell-check.*$

# patch hunk comments
^\@\@ -\d+(?:,\d+|) \+\d+(?:,\d+|) \@\@ .*
# git index header
index [0-9a-z]{7,40}\.\.[0-9a-z]{7,40}

# cid urls
(['"])cid:.*?\g{-1}

# data urls
\(data:.*?\)
(['"])data:.*?\g{-1}
data:[-a-zA-Z=;:/0-9+]*,\S*

# The `\b` here means a break, it's the fancy way to handle urls, but it makes things harder to read
# In this examples content, I'm using a number of different ways to match things to show various approaches
# asciinema
\basciinema\.org/a/[0-9a-zA-Z]+

# appveyor
\bci\.appveyor\.com/api/projects/status/[0-9a-z]+
\bci\.appveyor\.com/project/[^/]*/[^/]*/builds?/\d+/job/[0-9a-z]+

# Amazon
# AWS S3
\b\w*\.s3[^.]*\.amazonaws\.com/[-\w/&#%_?:=]*
# AWS execute-api
\b[0-9a-z]{10}\.execute-api\.[-0-9a-z]+\.amazonaws\.com\b
# AWS ELB
\b\w+\.[-0-9a-z]+\.elb\.amazonaws\.com\b
# AWS SNS
\bsns\.[-0-9a-z]+.amazonaws\.com/[-\w/&#%_?:=]*

# Here, we're matching `http://` and `https://` by using `s?`
# YouTube
https?://(?:(?:www\.|)youtube\.com|youtu.be)/(?:channel/|embed/|playlist\?list=|watch\?v=|v/|)[-a-zA-Z0-9?&=_]*
<\s*youtube\s+id=['"][-a-zA-Z0-9?_]*['"]
\bimg\.youtube\.com/vi/[-a-zA-Z0-9?&=_]*
# Google Accounts
\baccounts.google.com/[-_/?=.:;+%&0-9a-zA-Z]*
# Google Analytics
\bgoogle-analytics\.com/collect.[-0-9a-zA-Z?%=&_.~]*
# Google APIs
\bgoogleapis\.com/[a-z]+/v\d+/[a-z]+/[@./?=\w]+
\b[-a-zA-Z0-9.]*\bstorage\d*\.googleapis\.com(?:/\S*|)
# Google Calendar
\bcalendar\.google\.com/calendar(?:/u/\d+|)/embed\?src=[@./?=\w&%]+
\w+\@group\.calendar\.google\.com\b
# Google DataStudio
\bdatastudio\.google\.com/(?:(?:c/|)u/\d+/|)(?:embed/|)(?:open|reporting|datasources|s)/[-0-9a-zA-Z]+(?:/page/[-0-9a-zA-Z]+|)
# The leading `/` here is as opposed to the `\b` above
# ... a short way to match `https://` or `http://` since most urls have one of those prefixes
# Google Docs
/docs\.google\.com/[a-z]+/(?:u/\d+|d/(?:e/|)[0-9a-zA-Z_-]+/)?(?:edit\?[-\w=#.]*|/\?[\w=&]*|)
# Google Drive
\bdrive\.google\.com/(?:file/d/|open)[-0-9a-zA-Z_?=]*
# Google Groups
\bgroups\.google\.com/(?:(?:forum/#!|d/)(?:msg|topic)|a)/[^/]+/[a-zA-Z0-9]+(?:/[a-zA-Z0-9]+|)
# Google Maps
\bmaps\.google\.com/maps\?[\w&;=]*
# Google themes
themes\.googleusercontent\.com/static/fonts/[^/]+/v\d+/[^.]+.
# Google CDN
\bclients2\.google(?:usercontent|)\.com[-0-9a-zA-Z/.]*
# Goo.gl
/goo\.gl/[a-zA-Z0-9]+
# Google Chrome Store
\bchrome\.google\.com/webstore/detail/[-\w]*(?:/\w*|)
# Google Books
\bbooks\.google\.(?:\w{2,4})/books\?[-\w\d=&#.]*
# Google Fonts
\bfonts\.(?:googleapis|gstatic)\.com/[-/?=:;+&0-9a-zA-Z]*

# GitHub SHAs
\bapi.github\.com/repos/[^/]+/[^/]+/[^/]+/[0-9a-f]+\b
(?:\[[0-9a-f]+\]\(https:/|)/(?:www\.|)github\.com/[^/)]+/[^/)]+(?:/[^/)]+/[0-9a-f]+(?:[-0-9a-zA-Z/#.]*|)\b|)
\bgithub\.com/[^/]+/[^/]+[@#][0-9a-f]+\b
# githubusercontent
/[-a-z0-9]+\.githubusercontent\.com/[-a-zA-Z0-9?&=_\/.]*
# gist github
\bgist\.github\.com/[^/]+/[0-9a-f]+
# git.io
\bgit\.io/[0-9a-zA-Z]+
# GitHub JSON
"node_id": "[-a-zA-Z=;:/0-9+]*"
# Contributor
\[[^\]]+]\(https://github\.com/[^/]+\)
# GHSA
GHSA(?:-[0-9a-z]{4}){3}

# GitLab
\bgitlab\.[^/]*/\S+/\S+/commit/[0-9a-f]{7,16}#[0-9a-f]{40}\b
\bgitlab\.[^/]*/\S+/\S+/-/merge_requests/\d+/diffs#[0-9a-f]{40}\b
\bgitlab\.[^/]*/uploads/[-a-zA-Z=;:/0-9+]*
\bgitlab\.[^/]*/[^/]+/[^/]+/commits?/[0-9a-f]+\b

# binanace
accounts.binance.com/[a-z/]*oauth/authorize\?[-0-9a-zA-Z&%]*

# bitbucket
\bapi\.bitbucket\.org/\d+\.\d+/repositories/[^/]+/[^/]+/diff(?:stat|)/[^/]+/[^/]+:[0-9a-f]+
\bapi\.bitbucket\.org/\d+\.\d+/repositories/[^/]+/[^/]+/commits?/[0-9a-f]+
\bbitbucket\.org/[^/]+/[^/]+/commits?/[0-9a-f]+

# bit.ly
\bbit\.ly/\w+

# bitrise
\bapp\.bitrise\.io/app/[0-9a-f]*/[\w.?=&]*

# circleci
https://circleci.com/gh/[^/]+/[^/]+/[^/]+(?:/[^/]+|).[a-z]+\?[-0-9a-zA-Z=&]+

# gitter
\bgitter\.im/[^/]+/[^/]+\?at=[0-9a-f]+

# gravatar
\bgravatar\.com/avatar/[0-9a-f]+

# ibm
[a-z.]*ibm\.com/[-_#=:%!?~.\\/\d\w]*

# imgur
\bimgur\.com/[^.]+

# Internet Archive
\barchive\.org/web/\d+/(?:[-\w.?,'/\\+&%$#_:]*)

# discord
/discord(?:app\.com|\.gg)/(?:invite/)?[a-zA-Z0-9]{7,8}

# Disqus
\bdisqus\.com/[-\w/%.()!?&=_]*

# medium
link\.medium\.com/[a-zA-Z0-9]+
\bmedium\.com/\@[^/]+/[-\w]+

# microsoft
\b(?:https?://|)(?:(?:download\.visualstudio|docs|msdn2?)\.microsoft|blogs\.msdn)\.com/[-_a-zA-Z0-9()=./%]*
# powerbi
\bapp\.powerbi\.com/reportEmbed/[^"' ]*

# mvnrepository.com
\bmvnrepository\.com/[-0-9a-z./]+

# now.sh
/[0-9a-z-.]+\.now\.sh\b

# oracle
\bdocs\.oracle\.com/[-0-9a-zA-Z./_?#&=]*

# chromatic.com
/\S+.chromatic.com\S*[")]

# codacy
\bapi\.codacy\.com/project/badge/Grade/[0-9a-f]+

# compai
\bcompai\.pub/v1/png/[0-9a-f]+

# mailgun
\.api\.mailgun\.net/v3/domains/[0-9a-z]+\.mailgun.org/messages/[0-9a-zA-Z=@]*
\b[0-9a-z]+.mailgun.org

# Reddit
\breddit\.com/r/[/\w_]*

# requestb.in
\brequestb\.in/[0-9a-z]+

# sched
\b[a-z0-9]+\.sched\.com\b

# Slack
slack://[a-zA-Z0-9?&=]+
\bslack\.com/[-0-9a-zA-Z/_~]*
\bslack-edge\.com/[-a-zA-Z0-9?&=%./]+
\bslack-imgs\.com/[-a-zA-Z0-9?&=%.]+

# shields.io
\bshields\.io/[-\w/%?=&.]*

# stackexchange -- https://stackexchange.com/feeds/sites
\b(?:askubuntu|serverfault|stack(?:exchange|overflow)|superuser).com/questions/\d+/[a-z-]+

# Sentry
[0-9a-f]{32}\@o\d+\.ingest\.sentry\.io\b

# Twitter
\[\@[^[/\]:]*?]\(https://twitter.com/[^/]*(?:/status/\d+(?:\?[-_0-9a-zA-Z&=]*|)|)\)
\btwitter\.com/hashtag/[\w?_=&]*
\btwitter\.com/[^/]*(?:/status/\d+(?:\?[-_0-9a-zA-Z&=]*|)|)
\btwimg\.com/profile_images/[_\w./]*
\btwimg\.com/media/[-_\w./?=]*
\bt\.co/\w+

# facebook
\bfburl\.com/[0-9a-z_]+

# dropbox
\bdropbox\.com/s/[^/]+/[-0-9A-Za-z_.%]+

# ipfs
ipfs://[0-9a-z]*
/ipfs/[0-9a-z]*

# w3
\bw3\.org/[-0-9a-zA-Z/#.]+

# loom
\bloom\.com/embed/[0-9a-f]+

# regex101
\bregex101\.com/r/[^/]+/\d+

# figma
\bfigma\.com/file(?:/[0-9a-zA-Z]+/)+

# HyperKitty lists
/archives/list/[^@/]+\@[^/]*/message/[^/]*/

# list-management
\blist-manage\.com/subscribe(?:[?&](?:u|id)=[0-9a-f]+)+

# kubectl.kubernetes.io/last-applied-configuration
"kubectl.kubernetes.io/last-applied-configuration": ".*"

# pgp
\bgnupg\.net/pks/lookup[?&=0-9a-zA-Z]*

# ANSI color codes
\\u001b\[\d+(?:;\d+|)m

# URL escaped characters
\%[0-9A-F]{2}
# IPv6
\b(?:[0-9a-f]{0,4}:){5}[0-9a-f]{0,4}\b
# c99 hex digits (not the full format, just one I've seen)
0x[0-9a-fA-F](?:\.[0-9a-fA-F]*|)[pP]
# Punycode
\bxn--[-0-9a-z]+
# sha256
sha256:[0-9a-f]+
# sha-... -- uses a fancy capture
(['"]|&quot;)[0-9a-f]{40,}\g{-1}
# hex in url queries
=[0-9a-fA-F]+&
# ssh
(?:ssh-\S+|-nistp256) [-a-zA-Z=;:/0-9+]*
# PGP
\b(?:[0-9A-F]{4} ){9}[0-9A-F]{4}\b
# uuid:
[<({"'>][0-9a-fA-F]{8}-(?:[0-9a-fA-F]{4}-){3}[0-9a-fA-F]{12}[<'"})>]
# hex digits including css/html color classes:
(?:[\\0][xX]|\\u|[uU]\+|#x?|\%23)[0-9a-fA-FgGrR_]{2,}(?:[uUlL]{0,3}|u\d+)\b
# integrity
integrity="sha384-[-a-zA-Z=;:/0-9+]{64}"

# https://www.gnu.org/software/groff/manual/groff.html
# man troff content
\\f[BCIPR]

# .desktop mime types
^MimeTypes?=.*$
# .desktop localized entries
^[A-Z][a-z]+\[[a-z]+\]=.*$

# IServiceProvider
\bI(?=(?:[A-Z][a-z]{2,})+\b)

# crypt
"\$2[ayb]\$.{56}"

# Input to GitHub JSON
content: "[-a-zA-Z=;:/0-9+]*="

# Python stringprefix / binaryprefix
\b(?:B|BR|Br|F|FR|Fr|R|RB|RF|Rb|Rf|U|UR|Ur|b|bR|br|f|fR|fr|r|rB|rF|rb|rf|u|uR|ur)'

# Regular expressions for (P|p)assword
\([A-Z]\|[a-z]\)[a-z]+

# JavaScript regular expressions
/.*/[gim]*\.test\(
\.replace\(/[^/]*/[gim]*\s*,

# Go regular expressions
regexp\.MustCompile\(`[^`]*`\)

# kubernetes pod status lists
# https://kubernetes.io/docs/concepts/workloads/pods/pod-lifecycle/#pod-phase
\w+(?:-\w+)+\s+\d+/\d+\s+(?:Running|Pending|Succeeded|Failed|Unknown)\s+

# kubectl - pods in CrashLoopBackOff
\w+-[0-9a-f]+-\w+\s+\d+/\d+\s+CrashLoopBackOff\s+

# posthog secrets
posthog\.init\((['"])phc_[^"',]+\g{-1},

# Update Lorem based on your content (requires `ge` and `w` from https://github.com/jsoref/spelling; and `review` from https://github.com/check-spelling/check-spelling/wiki/Looking-for-items-locally )
# grep lorem .github/actions/spelling/patterns.txt|perl -pne 's/.*i..\?://;s/\).*//' |tr '|' "\n"|sort -f |xargs -n1 ge|perl -pne 's/^[^:]*://'|sort -u|w|sed -e 's/ .*//'|w|review -
# Warning, while `(?i)` is very neat and fancy, if you have some binary files that aren't proper unicode, you might run into:
## Operation "substitution (s///)" returns its argument for non-Unicode code point 0x1C19AE (the code point will vary).
## You could manually change `(?i)X...` to use `[Xx]...`
## or you could add the files to your `excludes` file (a version after 0.0.19 should identify the file path)
# Lorem
(?:\w|\s|[,.])*\b(?i)(?:amet|consectetur|cursus|dolor|eros|ipsum|lacus|libero|ligula|lorem|magna|neque|nulla|suscipit|tempus)\b(?:\w|\s|[,.])*

# the negative lookahead here is to allow catching 'templatesz' as a misspelling
# but to otherwise recognize a Windows path with \templates\foo.template or similar:
\\templates(?![a-z])
# ignore long runs of a single character:
\b([A-Za-z])\g{-1}{3,}\b
# Note that the next example is no longer necessary if you are using
# to match a string starting with a `#`, use a character-class:
[#]backwards
# version suffix <word>v#
[Vv]\d+(?:\b|(?=[a-zA-Z_]))
# Compiler flags
[\t >"'`=(](?:-J|)-[DPWXY]
[\t "'`=(]-[DPWXYLlf]
,-B
# curl arguments
\b(?:\\n|)curl(?:\s+-[a-zA-Z]+)+
# set arguments
\bset\s+-[abefiuox]+\b
# tar arguments
\b(?:\\n|)tar(?:\s+-[a-zA-Z]+|\s[a-z]+)+
# macOS temp folders
/var/folders/\w\w/[+\w]+/(?:T|-Caches-)/
```

## See also

* [[Forbidden patterns|Feature: Forbidden patterns]]

## Notes

* `patterns` operate on a per line basis
* the first match wins, and matches are replaced by a single space character -- roughly resulting in the matched content being treated as a word break (and not seen by the word checker)
  * the behavior may change such that the length of a replacement matches the length of the replaced content...
* there is no support for multiline patterns, see [[Feature: Block Ignore]] for my current thoughts
