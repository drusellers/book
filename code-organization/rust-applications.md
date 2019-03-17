# Rust Applications

```text
src/
  apps/
    mod.rs
    cli/
      mod.rs
    http/
      mod.rs
  features/ -- bad name conflicts with #[feature(_)]
    mod.rs
    feature-a/
      mod.rs
  infrastructure/
    mod.rs
    fs/
      mod.rs
  lib.rs
  main.rs
migrations/
doc/
Cargo.toml
Cargo.lock
```

## How to construct a feature in rust

Rust's packaging system allows for a more tailored module layout. C\# is folders and namespaces, but inside of an assembly its harder to construct a clean module. Node/JavaScript with their reexport capabilities allow for a more crafted experience.

```text
~/
  <the feature>/
    http.rs
      implement iron handlers here
    cli.rs
      implement cli commands here
    mod.rs
      rexport model here?
    model.rs
      the entity struct
      the implementation of display
    repository.rs
      implement repository access here
```

## Style Notes

Return a `Box<Error>` when returning a variety of errors. This will let you pass the real error type.

Also, use - [https://github.com/brson/error-chain](https://github.com/brson/error-chain)

Use `try!()` or the new `?` operator to reduce "pattern matching noise".

If working with the database directly look at the `From` trait.

