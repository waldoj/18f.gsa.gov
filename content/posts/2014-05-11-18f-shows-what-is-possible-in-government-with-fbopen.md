---
layout: post
date: '2014-05-11T13:02:00-04:00'
tumblr_url: http://18fblog.tumblr.com/post/85434416767/18f-shows-what-is-possible-in-government-with-fbopen

title: "With FBOpen API, 18F shows what's possible in government"
description: There has been some <a href="http://e-pluribusunum.com/2014/03/12/at-18f-in-gsa-u-s-seeks-to-tap-the-success-of-the-u-k-s-government-digital-services/">great coverage of the new group of tech specialists out of the GSA</a>, dubbed <a href="https://18f.gsa.gov/">18F</a>.
excerpt: There has been some <a href="http://e-pluribusunum.com/2014/03/12/at-18f-in-gsa-u-s-seeks-to-tap-the-success-of-the-u-k-s-government-digital-services/">great coverage of the new group of tech specialists out of the GSA</a>, dubbed <a href="https://18f.gsa.gov/">18F</a>.
image: /assets/blog/fbopen/fbopen-pilot-logo.png

authors:
- kinlane

tags:
- fbopen
- procurement
- acquisition services
- api
- best practices
hero: false
---

There has been some [great coverage of the new group of tech specialists
out of the
GSA](http://e-pluribusunum.com/2014/03/12/at-18f-in-gsa-u-s-seeks-to-tap-the-success-of-the-u-k-s-government-digital-services/),
dubbed [18F]({{ "/" | url }}). According to their own home page,
18F:

> *...builds effective, user-centric digital services focused on the
> interaction between government and the people and businesses it
> serves. We help agencies deliver on their mission through the
> development of digital and web services.*

[![FBOpen
Logo]({{ "/assets/blog/fbopen/fbopen-pilot-logo.png" | url }})](https://fbopen.gsa.gov)

I know most of the team members from my work with the GSA, and my own
time (albeit short) as a Presidential Innovation Fellow, and I am
extremely optimistic about the potential of the team. This optimism is
being seriously validated after looking through the group's recent
release of the [FBOpen API](http://docs.fbopen.apiary.io), which is a
simple API resource to get access to opportunities to do business with
the U.S. federal government.

**Use existing tools**

18F demonstrates their tech chops by not re-inventing the wheel when it
comes to designing and developing the FBOpen API. After they downloaded
the existing business opportunity XML dumps from
[FBO.gov](https://www.fbo.gov), they employed [Apache
Solr](https://lucene.apache.org/solr/) to develop a thin API layer on
top of the files. Solr does two things well, it provides a REST
interface on top of document stores, and supports the Lucene query
syntax, which provides a powerful query interface on top of the simple
API. Beyond Solr, 18F also used [Apiary](https://apiary.io) and
[Github](https://github.com), to cobble together a platform for API
operations, demonstrating their dedication to agility and speed.

**Simplicity rules**

The FBOpen API interface adheres to API simplicity by providing
logical, versioned URI for accessing the government business
opportunities, with a query and data source parameter allowing you to
tailor the source of your query. Then you can filter by noncompetes or
closed opportunities, as well as controlling the number of results
returned, including common pagination controls developers are used to
when working with APIs. FBOpen API does one thing, and does it well –
the calling card of successful APIs.

**Modern design lifecycle**

Again, demonstrating their grasp of modern technology, 18F employs
Apiary to model and design the FBOpen API interface – using [API
Blueprint](https://apiblueprint.org) allowed them to define the API
interface in markdown, then deploy a mock interface, interactive API
documentation and code samples in a variety of languages. This approach
to designing APIs in government is the future for not just providing a
machine readable definition of the API, but delivers the documentation
and code necessary to onboard any developer in minutes—increasing the
chances the API will be integrated with.

**Open By Default**

The FBOpen API sets the bar for all government APIs, by making sure not
just the API is public and accessible, but so is the API design, source
code and underlying tooling—allowing anyone to deploy an instance of the
FBOpen API. Since FBOpen is built on Solr, publicly available XML data
source, and published on GitHub, anyone can download or fork, and deploy
their own instance of the FBOpen API. This is the definition of an open
API.

**Central key management with api.data.gov**

Before you can make calls on the central FBOpen API instance, you must
obtain an API key from [api.data.gov](https://api.data.gov). This should
be standard business operations for ALL federal government APIs.
Developers shouldn't have to manage separate accounts with each agency,
they should be able to request credentials in a single location, and use
across all APIs they consume within in the federal government.
api.data.gov uses [API Umbrella](https://github.com/NREL/api-umbrella),
an open source API management solution developed by National Renewable
Energy Laboratory (NREL), and is employed by the GSA in the common API
infrastructure available to all agencies.

**Read / write APIs in government (kindasorta)**

I started to cry when I saw that there was not just a GET method for
FBOpen, but here was a POST method, allowing for users to add or update
opportunities via the API—then I saw it was disabled, and the tears
dried up. The option is only available if you deploy your own instance
of the API, which in my opinion actually represents the future of read /
write APIs in government. I just don't think government can move fast
enough, and manage the responsibility of write APIs in all scenarios,
and providing open source APIs like FBOpen, that anyone can download,
install and allow for adding and updating data can bridge this canyon.
If enough trusted instances of the FBOpen can be established outside the
federal government firewall, agencies can make their own decision around
which sources they want to trust and pull opportunities back into
internal systems. With proper certification of API deployments by our
government, APIs lie FBOpen can share the load of managing data with
private sector, without the risk that comes with doing it all
internally.

*Cross-posted from [API Evangelist](https://apievangelist.com/2014/04/08/18f-shows-what-is-possible-in-government-with-fbopen-api/) by former Presidential Innovation Fellow Kin Lane.*
