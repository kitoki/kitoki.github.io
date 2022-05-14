---
layout: post
title: Architect and Maintain large-scale CSS codebases
date: 2022-04-14 08:49 +0700
categories: [large_scale, maintain, codebase]
tags: [CSS]
---

- it might be CSS that simply has a large file size. there's a lot of CSS output and so making changes to that codebase can be difficult, as there is so much of the code to consider.
- the CSS could be said to be 'large' due to the complexity of the user interface that is being built with it. the overall file size may be smaller than the first situation but there may be a great many pieces of user interface that's codified in those styles. considering how to effect changes across all those visuals may be problematic.
- it might be 'large CSS' simply due to the number of developers that have, are and will be likely to touch and change the CSS code base.
- or it  can be all the above.

> some basic need :
- to allow the easy maintenance of a large CSS codebase over time
- to allow portions of CSS code to be removed from the codebase without effecting the remaining styles
- it sould be possible to rapidly iterate on any new designs
- changing the properties and vales that apllied to one visual element should not unintentionally effect others
- any solution should require minimal tooling and workflow changes to implement
- where possible, W3C standards such as ARIA should be used to communicate state changewithin the user interface

