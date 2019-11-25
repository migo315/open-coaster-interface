# Open Coaster Interface (OCI)
**Open Coaster Interface** is an GraphQL API for themeparks provided by [coaster.cloud](https://coaster.cloud). This repository
introduce to the API and show some examples. In addition, we handle all issues, suggestions and provide a change log.

GraphQL Endpoint: `https://oci.coaster.cloud/graphql/v1`

GraphQL IDE (Playground): [https://oci.coaster.cloud](https://oci.coaster.cloud)

**WARNING:** OCI is currently in the "Release Candidate" phase and will be versioned on November 25th 2019. Before OCI is
versioned, there may still be Breaking Changes.

## Version (from 25th of November)
**OCI** follows the [Semantic Versioning](https://semver.org/): MAJOR.MINOR.PATCH
- MAJOR version changed when we made incompatible changes (Breaking Change).
- MINOR version changed when we add new fields which don't affect current functionality.
- PATCH version changed when we fix a bug which don't affect current functionality.

Therefor, all changes in MINOR or PATCH don't have breaking changes.

## Examples
You will find here some example request for fetching data.

* [Get single park (e.g. "Phantasialand")](./examples/single_park.md)
* [Get single attraction (e.g. "Taron")](./examples/single_attraction.md)
* [Get list of parks](./examples/list_park.md)
* [Get waiting times (e.g. "Efteling")](./examples/waiting_times.md)
* [Get facet search (e.g. of parks)](./examples/facet_park.md)
* [Get parks by geo location](./examples/location_filter.md)

Please keep in mind that these are very simple examples with only a fraction of the fields.
The complete documentation can be found in our [Playground](https://oci.coaster.cloud).

## Localization
You can help to improve the english translations at [crowdin](https://crowdin.com/project/coastercloud). We are grateful for any help.
