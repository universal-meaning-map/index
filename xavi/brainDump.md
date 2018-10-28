_This is Xavi's sketch file for ideas, issues, readmes... anything that is not fully developed yet_

# Atomic data structure

## Semantic triple
In the original specs of the mindmap, we mentioned that our priority was to figure out the best data structure.

Without knowing about them we end up with , we end up the very similar constructions of the [semantic triple](https://www.w3.org/TR/2014/REC-rdf11-concepts-20140225/#dfn-rdf-triple) where:
`origin` = `subject`
`type` = `verb`
`target` = `object`

At this point it seems clear that those three elements are escential in order to represent meaningful connections between content in a distributed system.

What is not clear, and this issue is what this is about, is how to structure this data.

## Original approach

The original structure (`O`) was designed as such:

```json
{
    "origin":"Mars",
    "relations": [
        {
            "target": "red",
            "type": "is"
        }
    ]
}
```

And we have extensively discussed this alternative (`A`):

```json
{
    "origin":"Mars",
    "target": "red",
    "type": "is"
}
```

The difference is that `C` allows to attach multiple `relations` around an `origin`.

These two constructions can represent the same stuff, but is likely that they will incentivise different usages.

If you want to represent a more complex idea around "Mars"
`O`:

 ```json
 {
    "origin":"Mars",
    "relations": [
        {
            "target": "red",
            "type": "is"
        },
        {
            "target": "planet",
            "type": "is"
        },
        
    ]
}
```
`A`
```json
{
    "origin":"Mars",
    "target": "red",
    "type": "is"
},
{
    "origin":"Mars",
    "target": "planet",
    "type": "is"
}
```

In `A` we now need multiple `triples`. 


# Do we need `origin`?
- We use it as ankor point

# RDF and semantic triplets

# No concensus
- We want to enhance the mind. And its subjective view.
- Our tools don't serve a platform but a mind.
- Concensus is a layer on top of the mind subjective view.

# Bi-directional links

# Documentation praxis manifesto
- Documentation should be implicit when possible (ex: function with a good descriptive name), otherwise
    - Documention should be derived from the implementation automatically
- Documentation needs to be acessible. Is not ok for a documentation to exists if is hard to reach
- Avoid links that can be broken easly.
- No broken documentation. No todos, no WIP. A documentation entry should be be cohesive with itself. While a section with WIP may be necessary
- Documention should be developed in paralel of an implementation. (Ex: Do not accept a PR without its corresponding documentation)

# Other projects
- [Project Xanadu](https://en.wikipedia.org/wiki/Project_Xanadu)

# Encapsulation
- The smaller the encapsulation, the more reasuable
- Context

# How to create links