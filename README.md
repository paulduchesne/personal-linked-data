# Personal Linked Open Data

Semantic experiments with personal data. Inspired by Karl Ove Knausgård, Adelheid Heftberger, Shoshana Zuboff and my former housemates who were performing statistical analysis on their bowel movements. Note that there is substantial overlap with the [Solid](https://solidproject.org/) project and this may be abandoned in the future, in lieu of working with that protocol.

### Summary

We have become so accustomed to our personal data being harvested and filtered back to us, that it feels almost transgressive to self-host it. There is however an extraordinary feeling of liberation to be able to choose *what is shared* and *how it is shared*. It also occurs to me that at a granular enough level, this could also represent a "data diary" or even a "data autobiography".  

### Architecture

These systems are being developed using the well established W3C structures for Linked Open Data. The `example` directory provides an initial example of the data processing pipeline. The source is a [JSON-LD file](example/data.json) derived from details surrounding my birth. To enable the ability to encrypt individual statements, there is a meta layer of RDF which renders all the declared statements as Literals. Ideally this source file would stay with the originator, or not at all, given that all statements can be subsequently decrypted. 

The [example notebook](example/example.ipynb) walks through the subsequent processing of this data. The statements which have been designated as "closed statements" are encrypted (currently using Ansible Vault for reasons of convenience), and produce two results: the partially encrypted [JSON-LD file](example/example.json) which can be freely shared, and an [index of keys](example/keys.json). Encryption management, and how portions of data can be deemed appropriate to share, will likely be one of the biggest challenges of this project. Also storing single keys is not ideal, better would be some form of mutual authentication. 

### Storage

At present the plan is that the result data will be hosted under a self-owned domain, in line with the intention of maintaining digital sovereignty. Another model to explore would be peer-to-peer decentralisation of the dataset, although thought would have to be given to retaning provenance. Also worth exploring, is the ability to begin embedding documents and media files into the graph (likely via base64 encoding), which moves the project away from simply declaring data into something closer to a decentralised file system.