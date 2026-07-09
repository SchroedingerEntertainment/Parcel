Modern game development doesn't happen inside a single ecosystem.

A typical project combines C++, C#, Rust, scripting languages, asset pipelines, build tools, editors and platform-specific tooling. Every language brings its own package manager. Every ecosystem introduces its own dependency model, metadata format and registry.

Parcel was built around a different idea:
> Instead of replacing existing package managers, Parcel connects them.

It provides a unified package model, a federated registry catalog and a consistent interface between Hamper and the package ecosystems your project already depends on. While packages stay where they belong, Parcel makes them work together

---

## Not Another Package Manager

Parcel intentionally avoids becoming another language-specific package manager. Traditional package managers solve problem within their own language. Parcel solves it across languages.

Whether a package originates from Cargo, npm, NuGet, PyPI or another supported source, Parcel presents it as part of one coherent package graph that Hamper can understand.

The goal is not to replace existing ecosystems, but to unify them.


Rather than compiling code, its responsibility is to discover packages, normalize metadata, resolve dependencies and provide Hamper with a consistent view of the software ecosystem.

Cargo builds Rust.
Parcel builds package graphs

---

## Federated Package Catalog

Parcel does not replace package registries. Instead, it maintains a federated catalog of every registry available to the project. Each registry remains the authoritative source for its own packages.

Parcel stores and manages:

- registry definitions
- registry adapters
- authentication information
- available packages
- version metadata
- dependency metadata
- local package cache
- normalized package descriptors

Whenever a package is requested, Parcel communicates with the appropriate registry through its adapter, retrieves the required metadata and translates it into Hamper's universal package model. To Hamper, every package looks the same, regardless of where it originated