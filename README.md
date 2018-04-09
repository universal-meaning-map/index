This document will be the skechpad for all things related to [Samantha](https://github.com/xavivives/Samantha/tree/master/extension), now renamed to `Arxiu`.
Everything is a work in progress, and improvements are very much appreciated. :)

[Got a better name?](https://github.com/arxiu/docs/issues)

## Motivations

## Goals

The fundamental idea is to create a personal archive. This means, a system that a user can store and organize any data/reference/file... in any way she wants. In the same fashion the user can publish and share this data.

The system should not "lock in" in the user in any way. And this inludes the structures used to organize the information, the way to display the information, the algorithms to find it...

It should allow for the highest degree of flexibility regarding how the user organizes the information and the relations between each element. It should not be restricted by the interface, or the underling file-system.

### Data
In the system we're describing,`data` lives separated from the `information`. What that means is we only take care on how do the information is organized (the realtionships between data).
The storage and retrival of data is delegated to another system powered by [IPFS](https://ipfs.io). 

So what we will call `data` to refer to an item of the file system, even if in the background is just a reference pointing to some bytes.

This reference is an [IPLD path](https://github.com/ipld/specs/tree/master/ipld#what-is-the-ipld-data-model). It allows us to pretty much point to anything.

### Hitag
A `Hitag` is a subset of `IPLD`. It is the basic unit we use to organzie content. It stands for "hierachical tag".What this means is you organize data by tagging it with multiple tags. The particularity is that this tag can have other tags inside, and so on. We call these tags `hitag`.

#### IPLD
A `Hitag` is nothing but an IPLD object, with few properties of its own.
If you don't know what IPLD is, check out [this video](https://www.youtube.com/watch?v=Bqs_LzBjQyk) from Juan Benet. Also [IPLD specs](https://github.com/ipld/specs/tree/master/ipld)

#### Properties
Like any IPLD object a `hitag` can have any set of arbitrary properties.
Some of them are reserved for the system.

- canRead : Public keys that are allowed to read the object and its properties, including the children hitags
- canWrite : Public keys that are allowed to write the object and its properties
- history :  Hashes of the previous data associated with this hitag
- hitags : List of all the children hitag


#### Metadata
Each hitag may have metadata associated with it. These metadata is concidered non-critical, and is mostly to assist the UX. This metadata is also part of the IPLD object.

Exemples:
- description
- default color
- creation timestamp
- last modificatio timestamp
- last edition timestamp
- any property defined by the user
- ...
