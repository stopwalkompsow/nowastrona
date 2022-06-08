---
layout: post
title: "Announcing Wildland Client v0.1"
excerpt: "First release of the Wildland client reference implemention!"
thumbnail: "/img/blog/4.jpg"
---

On behalf of the whole [team][team], I'm proud to announce the first public release of Wildland client! This is a reference implementation of the Wildland protocol, which we have described in our ["Why, What and How" (aka W2H) paper][w2h].

Leaving aside all the usual disclaimers about how early-beta and for-power-users-only this version really is, I'd like to focus on what's already working and possible :)

## What's here

Firstly, you can connect multiple storage backends (S3 buckets, WebDAV servers, Dropbox accounts, etc) and expose them all as _one unified file system_. We believe that this is how data management should really be done: users should not be concerned with which service provider their data is currently being held, but instead should be able to address their data using infrastructure-agnostic addressing, such as e.g.: `/projects/Wildland/blog/Announcing Wildland v0.1`. Whether this file lives in my Dropbox, local NAS, some p2p-synced storage, or on my local disk, should be of secondary importance, and not serve as a justification for including the infrastructure address in the main address of this piece of data.

Secondly, Wildland natively implements what we call _multi-categorization_. This means that every data container (the smallest unit of information on Wildland) can be assigned more than one address and can be accessed using any of these alternative addresses. Functionality-wise this is similar to having a directory on a traditional filesystem with multiple hard-links, except that with Wildland every path is equal.We believe that this feature is vital in making the filesystems powerful enough to allow for for them to be used as a primary tool for information and knowledge management. This is a broad and exciting topic and we will be talking more about it in future posts.

Finally, the third highlight of this release is support for what we call _cascading addressing_. Described in more detail in the paper [w2h], it can be thought of as an "upside-down DNS", or a bottom-up scalable addressing scheme which does not require any centralized authority, like pre-defined DNS root servers. It's important to note that this addressing scheme does not require any blockchain either.

Aside from today's release of the client, we're also opening up for public read-only access two Wildland _forests_ (a forest is a namespace built around one user identity):

1. The _Pandora_ forest (a reference to the Avatar movie), which is a repository of memos, reports, documents, etc, which we've been using internally to help us with Wildland's development. It's a bit like a shared Dropbox folder, except that it uses abstracted storage and heavily utilizes multi-categorization.

2. The _Ariadne_ forest, which is a very small forest containing bridges to other forests, specifically to the Pandora forest, and some other, internal forests, which are encrypted and not exposed for public use.

## What lies ahead

There are more exciting things ahead of us which we plan to bring to you in the upcoming releases. These can be generally grouped into three areas:

1. Making Wildland _easier to use_ and set up. This means: better integration on various platforms, easy-to-use GUI, and -- last but not least -- an Ethereum-based marketplace for storage, followed by user-centered governance and GLM integration, as described in the [W2H paper][w2h].

2. Making Wildland _faster_.

3. Making Wildland _more universal_, which includes better integration with more data storage backends, integration with various data sources, as well as adding support for compute backends attached to containers, allowing them to actively process the data.

And all this with the ultimate goal of providing a set of tools for users to be able to better manage their digital universe of information and do so on their own terms, rather than remaining dependent on large service providers.

If you would like to try Wildland today, we suggest you read [this introduction][intro] first. This [HOWTO][demo-forests] contains instructions on how to mount and explore the above-mentioned demo forests.

[team]: https://wildland.io/team
[w2h]: https://wildland.io/2020/04/09/wildland.html
[intro]: https://TODO/Wildland_Introduction.md
[demo-forests]: https://TODO
