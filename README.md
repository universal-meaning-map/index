This document will be the skechpad for all things related to `Samantha`, now renamed to `Arxiu`.
Everything is a work in progress, and improvements are very much appreciated. :)

[Got a better name?](https://github.com/arxiu/docs/issues)

## Goals

It's quite hard to define everything that `Arxiu` is trying to do.
The fundamental idea is to create a personal archive. This means, a system that a user can store and organize any data/reference/file... in any way she wants. In the same fashion the user can publish and share this data.

The system should not "lock in" in the user in any way. And this inludes the structures used to organize the information, the way to display the information, the algorithms to find it...

One main goal of this file system is to allow for the highest degree of flexibility in how the user organizes the information.

The storage in itself uses `IPFS`.

The data model that we call `Hitag`.

### Data
In this document I will use `data` to refer to an item of the file system. Wich is more like a reference. That could be:
    - A URL
    - An IPFS multi-hash
    - An [IPLD path](https://github.com/ipld/specs/tree/master/ipld#what-is-the-ipld-data-model))
    - A `hitag`

### Hitag
`Hitag` stands for "hierachical tag". It means that to any `data`, the user can associate it multiple tags. The particularity is that this tag can have other tags inside, and so on. We call this tags `hitag`.

#### Properties
Each hitag have a set of properties. This properties allow to define sofisticated behaviours.
These properties are defined in a JSON object. The hash of this object is a unique identifier of this hash (`UID`)

    - label : The display name of the `hitag`
    - maxChildren: Number of allowed children to have.
    - allowedChildren: An array of `hitag` `UIDs`. Only these hitag can be used.
    - excludedChildren:  An array of `hitag` `UIDs`. These hitags can't be used.
    - MandatoryChildren:  An array of `hitag` `UIDs`. These hitags have to be used.

An spec on how this properties are sorted needs to be set in order to ensure a deterministic `UID`
Probably there are more elegant way to define these properties.

#### Metadata
Each hitag may have metadata associated with it. These metadata is concidered non-critical, and is mostly to assist the UX
    - description
    - default color
    - any property defined by the user

#### Domains

The hash `UID` is contextual (is only unique on the domain of its siblings)
To reference an specific `hitag` `UID` in a global domain, it needs to be referenced through a `Hitag IPLD path`




## Stack

## Definitions
## IPLD Hitag repository