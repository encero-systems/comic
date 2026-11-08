# COMIC and Crumb

COMIC (Canonical Object Markup for Interoperable Crumbs) and Crumb are two forms of one typed value model, specified by Encero.

- **Crumb** is the binary form: a typed value encoded the way it sits in memory, so a reader can reach one field without decoding the rest.
- **COMIC** is the text form of the same value. It is canonical, so one value has exactly one spelling, and people and tools can read it.

A value written by one implementation reads back as the same typed value in any other, and converting between Crumb and COMIC loses nothing.

## Status

Draft. Nothing here is stable yet: a document or crumb written against one draft may not read under the next.

## What the specification covers

- the value model both forms share: records, variants, sequences, maps, exact scalars, text, bytes and references
- what counts as the same value, and the hashes computed over it
- field identity, and how a field keeps its identity when it is renamed
- schema identity and schema evolution
- the COMIC grammar and its canonical form
- the Crumb binary layout
- what a reader must refuse

The core names no programming language. Kinds that belong to one language live in a profile on top of the core, and a reader that doesn't know a profile still reads its values as ordinary tagged values.

## Conformance corpus

The corpus is plain files that any implementation can run: valid documents with the values they hold, documents a reader must refuse, and matching sets of Crumb bytes, COMIC text and hashes.

## Implementations

- **Incan**, in `std.primitives.crumb` (in progress). Incan is the first implementation and implements the format natively: its models, enums and newtypes crumble and print as COMIC without code written for them.

Where an implementation and this specification disagree, the specification decides.

## License

Apache License 2.0. See [LICENSE](LICENSE).
