# A Fuel Indexer Project

## Use Cases

The Fuel indexer project can currently be used in a number of different ways:

- as tooling to compile arbitrary indicies
- as a standalone service
- as a part of a Fuel project, alongside other components of the Fuel ecosystem (e.g. [Sway](https://fuellabs.github.io/sway))

We'll describe these three different implementations below.

### As tooling for compiling indices

The Fuel indexer provides functionality to make it easy to build and compile abitrary indices by using [`forc index`](../plugins/forc-index/index.md). For info on how to use indexer tooling to compile arbitrary indices, check out our [Quickstart](./../quickstart/index.md); additionally, you can read through our [examples](../examples/index.md) for a more in-depth exploration of how to compile indices.

### As a standalone service

You can also start the Fuel indexer as a standalone binary that connects to a Fuel node to monitor the Fuel blockchain for new blocks and transactions. To do so, run the requisite database migrations, adjust the configuration to connect to a Fuel node, and start the service.

### As part of a Fuel project

Finally, you can run the Fuel indexer as part of a project that uses other components of the Fuel ecosystem, such as Sway. The convention for a Fuel project layout including an indexer is as follows:

```text
.
├── contracts
│   └── hello-contract
│       ├── Forc.toml
│       └── src
│           └── main.sw
├── frontend
│   └── index.html
└── indexer
    └── hello-index
        ├── Cargo.toml
        ├── hello_index.manifest.yaml
        ├── schema
        │   └── hello_index.schema.graphql
        └── src
            └── lib.rs
```

## An Indexer Project at a Glance

Every Fuel indexer project requires three components:

- a [Manifest](../components/assets/manifest.md) describing index metadata
- a [Schema](../components/assets/schema.md) containing models for the data you want to index
- an [Execution Module](../components/assets/module.md) which houses the logic for creating the aforementioned data models