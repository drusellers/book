# Rust Applications

```
src/
  apps/
    mod.rs
    http/
      mod.rs
  features/
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

## Style Notes

Return a `Box<Error>` when returning a variety of errors. This will let you pass the real error type.

Use `try!()` or the new `?` operator to reduce "pattern matching noise".

If working with the database directly look at the `From` trait.