# RO-Crate MASP examples

Example profiles and schemas written in [RO-Crate MASP](https://github.com/Language-Research-Technology/ro-crate-masp) (Machine Actionable Schemas and Profiles). Each one is an RO-Crate whose rules are contextual entities, with generated documentation, a spreadsheet copy of the rules, and in some cases a [Crate-O](https://github.com/crate-works/crate-o) mode file.

> **Examples only.** These are working examples for developing and testing MASP. Some will move on to their own permanent homes, so don't rely on these copies or their URLs staying put.

Browse and filter them on the **[landing page](https://language-research-technology.github.io/ro-crate-masp-examples/)**, or use the table below. Each name links to its published documentation; "Build" is the command that regenerates it.

These examples were moved here from [ro-crate-masp](https://github.com/Language-Research-Technology/ro-crate-masp), where their earlier git history remains. The MASP profile itself (the spec) stays there.

## Example profiles and schemas

<!-- catalogue:start -->
<!-- catalogue:end -->

## Related repositories

- [ro-crate-masp](https://github.com/Language-Research-Technology/ro-crate-masp): the MASP spec, written as a MASP profile.
- [crate-works/ro-crate-masp-tools](https://github.com/crate-works/ro-crate-masp-tools): documentation generation, Crate-O mode files, and converters from OWL and schema.org. The build scripts here use it.
- [crate-works/ro-crate-masp-validator](https://github.com/crate-works/ro-crate-masp-validator): validates an RO-Crate against a MASP profile or schema.
- [masp-templates](https://github.com/Language-Research-Technology/masp-templates): a starting point for writing your own profile or schema.

## Building the documentation

```bash
npm install
npm run build              # every profile and schema, then the catalogue
npm run build:ldac-profile # just one (see the table above for each command)
npm run build:catalogue    # the table above and catalogue.json for the landing page
```

The builds run `generate-masp-docs -x`, which first syncs `ro-crate-metadata.json` and `ro-crate-metadata.xlsx`: the newer of the two wins and the other is regenerated. Edit either one, then build.

`npm run generate:modes` regenerates the Crate-O mode files.

## Validating a crate against an example

```bash
npx masp-validate [--json] <target-crate.json> <profile-crate.json>
```

For example, the minimal workflow crate against the workflow profile (also `npm run validate:workflow`):

```bash
npx masp-validate profiles/workflow/examples/minimal-example/ro-crate-metadata.json profiles/workflow/profile-crate/ro-crate-metadata.json
```

## Tests

`npm test` checks the examples themselves: that each profile's Crate-O mode file is present and linked, and that the LDAC-DMLex and schema.org crates validate as expected.

## Licence

Apache-2.0
