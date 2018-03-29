This document will be the skechpad for all things related to `Samantha`, now renamed to `Arxiu`.

[Got a better name?](https://github.com/arxiu/docs/issues)

## To do
    - Define project and its goals
    - Define IPLD Hitag specs

## Goals

It's quite hard to define everything that `Arxiu` is trying to do.
The fundamental idea is to create a personal archive. This means, a system that a user can store and organize any data/reference/file... in any way she wants. In the same fashion the user can publish and share this data.

The system should not "lock in" in the user in any way. And this inludes the structures used to oranize the information, the way to display the information, the algorithms to find it, the permissions of other users... 

The main feature of this file system is that it wants allow a lot of flexibility in how the user organizes the information. It has two main components, the storage in itself, which uses `IPFS`, and the data model that we call `Hitag`.

### Data
In this document I will use `data` to refer to an item of the file system. This could be a file (an mp3, a document...) or a reference (a url, a [Merkle Path](https://github.com/ipld/specs/tree/master/ipld#what-is-a-merkle-path))

### Hitag
`Hitag` stands for "hierachical tag". It means that to any `data`, the user can associate it multiple tags. The particularity is that this tag can have other tags inside, and so on. We call this tags `hitag`.
It is some sort of tree data structure with multiple trunks.

### Ideas
#### Rules
A hitag can set rules for its children.
Exemples:
    - Only few children hitags are available.
        An score system (1stars, 2stars, 3 stars)

    - Exclusive. Only one hitag can be set.
        In a book managing system. `Want to read` or `Currently reading` or  `Have read`



## Stack

## Definitions
## IPLD Hitag repository