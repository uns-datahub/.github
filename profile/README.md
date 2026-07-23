# UNS DataHub

Open-source building blocks for industrial Unified Namespace systems.

**Website:** [www.uns-datahub.com](https://www.uns-datahub.com)

UNS DataHub projects help Python, TypeScript and Node-RED applications publish, process,
archive, and query operational data through a consistent MQTT-based namespace.
The public repositories in this organization are designed to be useful
independently. Visit the website for the complete project map, architecture,
and current roadmap.

## Start here

| Repository | Purpose |
| --- | --- |
| [`uns-kit`](https://github.com/uns-datahub/uns-kit) | TypeScript toolkit, runtime libraries, and project scaffolding for UNS applications |
| [`rtt-demo-app`](https://github.com/uns-datahub/rtt-demo-app) | Hot rolling mill simulator and end-to-end example built with `@uns-kit` |
| [`uns-archiver`](https://github.com/uns-datahub/uns-archiver) | QuestDB archiver for UNS data and table packets |
| [`uns-api-global`](https://github.com/uns-datahub/uns-api-global) | Authenticated REST API for current and historical UNS data |
| [`node-red-contrib-uns`](https://github.com/uns-datahub/node-red-contrib-uns) | Node-RED nodes for subscribing to and publishing UNS messages |

Published JavaScript packages are available from the
[`@uns-kit` organization on npm](https://www.npmjs.com/org/uns-kit).

## How the pieces fit

```text
Producers and Node-RED
          |
          v
     MQTT / UNS
       |     |
       |     +----> UNS applications built with @uns-kit
       |
       +----------> UNS Archiver ----> QuestDB ----> UNS API Global
```

Each repository documents its own prerequisites, configuration, and verification
commands. For a first look, use `rtt-demo-app` as the example application and
`uns-kit` as the library reference.

## Roadmap

The open stack is planned to expand with:

- `uns-datahub-controller` — the central controller and embedded UI.
- `uns-bridge-mqtt` — mapping external MQTT payloads into a governed UNS.
- `uns-bridge-opcua` — mapping OPC UA nodes and values into the same model.

`uns-assistant-runtime`, including the `uns-rag` retrieval capability, is planned
as a subscription offering around the open stack. These repositories remain
private while the release and subscription model are being prepared.

Follow the latest overview at [www.uns-datahub.com](https://www.uns-datahub.com/#roadmap).

## Participate

- Read the shared [contribution guide](https://github.com/uns-datahub/.github/blob/main/CONTRIBUTING.md).
- Report security issues privately as described in the
  [security policy](https://github.com/uns-datahub/.github/blob/main/SECURITY.md).
- Use the issue tracker of the affected repository for bugs and focused feature
  requests.

Unless a repository says otherwise, public source is licensed under the MIT
License.
