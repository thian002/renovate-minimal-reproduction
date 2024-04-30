# renovate-minimal-reproduction
This repo was created to demonstrate that cargo source replacement doesn't work correctly for Renovate. The goal is to make source replacement work as documented in [The Cargo Book](https://doc.rust-lang.org/cargo/reference/source-replacement.html).

For example, this cargo config should work:
```toml
[source.my-vendor-source]
registry = "https://example.com/path/to/index"

[source.crates-io]
replace-with = "my-vendor-source"
```

The logs currently show
```
DEBUG: Replacing index of cargo registry crates-io with cargo-source-replacement
DEBUG: cargo-source-replacement cargo registry is missing index
DEBUG: cargo-source-replacement cargo registry is missing index
DEBUG: Replacing index of cargo registry crates-io with cargo-source-replacement
DEBUG: cargo-source-replacement cargo registry is missing index
```

Discussion can be found [here](https://github.com/renovatebot/renovate/discussions/28752) 
