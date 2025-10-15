---
slug: 2025-10-14-labs-update
title: Labs project update
authors: [dylan]
tags: [engineering]
---

_As the saying goes, time flies when you are having fun!_

Here over at Labs, we have been hard at work since the last blog post, cutting up bits and pieces of our internal repos and moving them over to Labs repos.
There are now a total of 7 OSS repos that contain an increasingly large amount of code that was previously considered proprietary and strictly internal.

## Some of the new repos:

### Micro
https://github.com/journeyapps-labs/micro

While currently a WIP, this repo now contains (at the time of writing) 4 of our internal JourneyMicro framework packages that (complete with the internal version) provides all the tools required to
build cutting-edge modern micro-services with enormous development velocity. These packages were moved over to enable moving over `common-sdk`.

### Common > SDK
https://github.com/journeyapps-labs/common/tree/main/packages/sdk

A new package in the `common` project that enables high-quality SDK clients that run in both Node.js & web environments, are fully typed and support pagination via async-generators.
This project was moved over to enable us to OSS and make available the `V4BackendClient`.

### Clients
https://github.com/journeyapps-labs/clients

This project contains only a single client at the moment (`V4BackendClient`) but will soon contain more of our SDKs that speak to the shared infrastructure
at JourneyApps. This will eventually also include the `AccountsClient` which provides nice typed, paginated access to `organizations`, `projects` and `developers`!

When coupled with the `DeployService` APIs, creating cloud integrations with JourneyApps becomes much, much simpler.

## Why are we doing this?

In the last post, we announced an early version of Sector which we decided we wanted to build in the open, and since then Sector has evolved dramatically.
As part of that evolution, the OSS version of Sector now shows indexes and (very shortly) will also integrate the OpLog. We figured that now is a good time
to move over a bit more of the technology so we can make use of our typed SDK clients to enable this.

## What's next for labs?

Right now we are working on getting the cloud version of Sector up and running, but we are working on improving all the current Labs projects as we go.
While shipping all versions of Sector, if we have an opportunity to improve a feature / add a missing feature in a way where we can move more code over to Labs, 
then we almost always now take that route.

Some examples of this:
* Big improvements to Reactor around themes, tables, and large data sets.
* Moving over Micro
* Moving over SDK Core (`common-sdk`)
* Moving over clients (`V4BackendClient`)
* Bumping package dependencies across all the Labs repos to stay in sync with active development happening over at Sector.

You can also expect to see more SDKs moved over to the `clients` repo since the core SDK tech is now available in `common`.

Micro is going to be fleshed out with more packages such as our `router` and `mongo` packages. When we do so, we will also provide example projects
that showcase how Micro can be used to set up and deploy micro-services.

We also have some CLI tools that will be heading over soon, and will probably land over at a `journeyapps-labs/dev` project in the near future. Keep an eye out for those!

That's all for now, but make sure to keep an eye out on the various Labs repos as we push updates there almost every day. 
