# Frequenz Microgrid Component Graph Library Release Notes

## Summary

This release updates the [`frequenz-microgrid-component-graph`](https://github.com/frequenz-floss/frequenz-microgrid-component-graph-rs) Rust crate to [v0.6.4](https://github.com/frequenz-floss/frequenz-microgrid-component-graph-rs/releases/tag/v0.6.4). `ComponentGraph` now accepts components of unspecified or unrecognized category that have no connections.

## Bug Fixes

- `ComponentGraph` no longer fails to build when an `UnspecifiedComponent` or `UnrecognizedComponent` has no connections. `components()` and `component()` can return such a component, but no formula includes it, even if it is a real device. To find these components, use `components(matching_types=UnspecifiedComponent)`. `ComponentGraph` still raises `InvalidGraphError` if one of these components has a connection.
