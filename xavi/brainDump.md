_This is Xavi's sketch file for ideas, issues, readmes... anything that is not fully developed yet_\

# Research

# Mappers and packers
Once I realized that we could treat each mind-map node as a [literal definition](https://github.com/interplanetarymindmap/mind-map/issues/2), it was pretty much impossible to me to concieve an alternative usage.

From a user perspective all I do is to keep adding `relations` to concept, and little by little I will end up with a model of my subjective view of the world.

With this in mind the data structure evolved trying to protect this construction.

Dani rapidly raised his hand and argued that if we benefit the mentioned construction, we may be biasing the design towards people that think in a very specific way, therefore going against [our main goal](https://github.com/interplanetarymindmap/mind-map#mind-map-1)
>
The idea of a mind-map, a tool that allows organizing information in the way that your brain works and not in a simplified way restricted by a user interface or a data structure.



# No concensus
- We want to enhance the mind. And its subjective view.
- Our tools don't serve a platform but a mind.
- Concensus is a layer on top of the mind subjective view.

# Bi-directional links

# Relationship dimensions

# Documentation praxis manifesto
- Documentation should be implicit when possible (ex: function with a good descriptive name), otherwise
    - Documention should be derived from the implementation automatically
- Documentation needs to be acessible. Is not ok for a documentation to exists if is hard to reach
- Avoid links that can be broken easly.
- No broken documentation. No todos, no WIP. A documentation entry should be be cohesive with itself. While a section with WIP may be necessary
- Documention should be developed in paralel of an implementation. (Ex: Do not accept a PR without its corresponding documentation)
- KISS: Can you say the same with less words. Can you use easier words?
- https://github.com/RichardLitt/standard-readme


# Encapsulation
- The smaller the encapsulation, the more reasuable
- Context

# How to create links


### Node
We are working towards eliminating this word from our dictionary because it keeps generating confusion. There are a lot of types of nodes, they almost represent the same thing, but they don't.

### Node cluster [OUTDATED]
One of the [original specs](##-original-specs) was:
> It needs to work on a global domain. This means that two different mindmaps pointing to the same concept should converge if put together

We call this convergence a `node cluster`. In other words is the set of nodes that are pointing to the same `CID`.

### Others
https://en.wikipedia.org/wiki/Ontology_(information_science)