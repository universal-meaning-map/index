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

# Beyond semantics. Definition trees.

We started by just conceiving semantics. And we end up with the triplet construction described in the [RDF documenation](https://www.w3.org/TR/2014/REC-rdf11-concepts-20140225/#dfn-rdf-triple):
`Subject` → `Predicate` → `Object`

[Quoting wikipledia](https://en.wikipedia.org/wiki/Semantic_triple):

>The components of a triple, such as the statement "The sky has the color blue", consist of a [`subject`](https://en.wikipedia.org/wiki/Subject_(grammar)) ("the sky"), a [`predicate`](https://en.wikipedia.org/wiki/Predicate_(grammar)) ("has the color"), and an [`object`](https://en.wikipedia.org/wiki/Object_(grammar)) ("blue"). This is similar to the classical notation of an [entity–attribute–value model](https://en.wikipedia.org/wiki/Entity%E2%80%93attribute%E2%80%93value_model) within [object-oriented design](https://en.wikipedia.org/wiki/Object-oriented_design), where this example would be expressed as an entity (sky), an attribute (colour) and a value (blue). From this basic structure, triples can be composed into [more complex models](https://en.wikipedia.org/wiki/Semantic_network), by using triples as objects or subjects of other triples — for example, Mike → said → (triples → can be → objects).

Shortly we realized that a pointer to a subjective set of `semantic triples` around a**instance** of a `subject` can be used as its literal `definition`

This is the definition (`MikeDefinition`) of a specific instance of "Mike".
For "specific instance" I'm referring for example to  my particular view of "Mike"
```
Mike = [
    (Mike → said → the sky is blue),
    (Mike → likes → apples),
    (Mike → is → my dog),
    ...
]
```
Which is very different from

`Mike → is → my dad`

A pointer to Mike's array of triplets (its hash), is no semantics anymore.

I don't know how this construction should be called. I will call it `definition` for now.

The cool thing is that we can use `MikeDefinition` as an element of a `semantic triplet` as well.

`MikeDefinition → is → Xavi's understanding of Mike`
`MikeDefinition → is used as →  the example`

Which is similar to the Wikipedia's more complex example above where it replaces an object with a triplet.
`Mike → said → (triples → can be → objects)`

This nesting allows us to create incredibly complex and accurate explanations/definitions since we can embed the exact definition of an element.


# How to create links