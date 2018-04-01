This document will be the skechpad for all things related to `Samantha`, now renamed to `Arxiu`.
Everything is a work in progress, and improvements are very much appreciated. :)

[Got a better name?](https://github.com/arxiu/docs/issues)

## Motivations

## Goals

It's quite hard to define everything that `Arxiu` is trying to do.
The fundamental idea is to create a personal archive. This means, a system that a user can store and organize any data/reference/file... in any way she wants. In the same fashion the user can publish and share this data.

The system should not "lock in" in the user in any way. And this inludes the structures used to organize the information, the way to display the information, the algorithms to find it...

One main goal of this file system is to allow for the highest degree of flexibility in how the user organizes the information. A user should be able to organize it the way its mind works, and not be restricted by the interface, or the underlin file-system.

The storage in itself uses `IPFS`.

The data model that we call `Hitag`.

### Data
In the system we're describing,`data` lives separated from the `information`. What that means is we only take care on how do the information is organized (the realtionships between data).
The storage and retrival of data is delegated to another system powered by [IPFS](https://ipfs.io). 

So what we will call `data` to refer to an item of the file system, even if in the background is just a reference pointing to some bytes.

This reference is an [IPLD path](https://github.com/ipld/specs/tree/master/ipld#what-is-the-ipld-data-model). It allows us to pretty much point to anything.

### Hitag
`Hitag` stands for "hierachical tag". It means that any `data` we can associate multiple tags. The particularity is that this tag can have other tags inside, and so on. We call these tags `hitag`.

#### IPLD
A `Hitag` is nothing but an IPLD object, with few properties of its own.
If you don't know what IPLD is, check out [this video](https://www.youtube.com/watch?v=Bqs_LzBjQyk) from Juan Benet. Also [IPLD.io](http://IPLD.io)

#### Properties
Each hitag have a set of properties. This properties allow to define sofisticated behaviours.
The hash of this object is a unique identifier of this hash (`UID`)

    - label : The display name of the `hitag`
    - maxChildren: Number of allowed children to have.
    - allowedChildren: An array of `hitag` `UIDs`. Only these hitag can be used.
    - excludedChildren:  An array of `hitag` `UIDs`. These hitags can't be used.
    - MandatoryChildren:  An array of `hitag` `UIDs`. These hitags have to be used.

This requires some [canonical](https://en.wikipedia.org/wiki/Canonical_form) format to ensure deterministic `UID`
Probably there are more elegant ways to define these properties. Ideas?

#### Metadata
Each hitag may have metadata associated with it. These metadata is concidered non-critical, and is mostly to assist the UX
    - description
    - default color
    - creation timestamp
    - last modificatio timestamp
    - last edition timestamp
    - any property defined by the user
    ...

#### Domains

The hash `UID` is contextual (is only unique within the domain of its siblings), so two children can't have the same ID. But to `hitags` in different trees/branches could.
To reference an specific `hitag` `UID` in a global domain, it needs to be referenced through a `Hitag IPLD path`

CONTENT RELATIONS?


## Stack

## Definitions
## IPLD Hitag repository
 
## History


name layer,\
hitags are merkle trees, 
used for subscripton changes ,
hash nodes,
canonical path,
selctors(define a subtree)
access of content is only having th hash
