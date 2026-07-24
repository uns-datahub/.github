# UNS DataHub

Open-source building blocks for industrial Unified Namespace systems.

**Website:** [www.uns-datahub.com](https://www.uns-datahub.com)

UNS DataHub projects help Python, TypeScript and Node-RED applications publish, process,
archive, and query operational data through a consistent MQTT-based namespace.
The public repositories in this organization are designed to be useful
independently. Visit the website for the complete project map, architecture,
and current roadmap.

## Choose your SDK

| Language | Package | Use it for |
| --- | --- | --- |
| TypeScript | [`@uns-kit/*`](https://www.npmjs.com/org/uns-kit) | Typed UNS applications, runtime services, metadata, and project scaffolding |
| Python | [`uns-kit`](https://pypi.org/project/uns-kit/) | Python UNS MQTT clients, runtime services, DataHub access, and project scaffolding |

Both SDKs are developed in the public [`uns-kit`](https://github.com/uns-datahub/uns-kit)
repository. The Python source and documentation live in
[`packages/uns-py`](https://github.com/uns-datahub/uns-kit/tree/master/packages/uns-py).

## Start here

### Coming next: UNS DataHub Runtime

`uns-datahub-runtime` will be the key public entry point that brings the complete
stack together: the controller, local infrastructure, configuration, and
lifecycle tooling in one deployable runtime. We are preparing it for public
release.

The controller remains a component of the runtime architecture; the planned
public-facing distribution is `uns-datahub-runtime`, rather than a standalone
`uns-datahub-controller` release.

Interested in early access? [Join the email-only notification list](https://www.uns-datahub.com/#early-access).

| Repository | Purpose |
| --- | --- |
| [`uns-kit`](https://github.com/uns-datahub/uns-kit) | TypeScript and Python toolkits, runtime libraries, and project scaffolding for UNS applications |
| [`rtt-demo-app`](https://github.com/uns-datahub/rtt-demo-app) | Hot rolling mill simulator and end-to-end example built with `@uns-kit` |
| [`uns-archiver`](https://github.com/uns-datahub/uns-archiver) | QuestDB archiver for UNS data and table packets |
| [`uns-api-global`](https://github.com/uns-datahub/uns-api-global) | Authenticated REST API for current and historical UNS data |
| [`node-red-contrib-uns`](https://github.com/uns-datahub/node-red-contrib-uns) | Node-RED nodes for subscribing to and publishing UNS messages |

## How the pieces fit

```text
TypeScript, Python and Node-RED producers
                  |
                  v
             MQTT / UNS
               |     |
               |     +----> UNS applications built with @uns-kit or uns-kit
               |
               +----------> UNS Archiver ----> QuestDB ----> UNS API Global
```

Each repository documents its own prerequisites, configuration, and verification
commands. For a first look, use `rtt-demo-app` as the example application and
`uns-kit` as the TypeScript and Python library reference.

## Roadmap

The open stack is planned to expand with:

- `uns-datahub-runtime` — the deployable public entry point that connects the controller, local infrastructure, configuration, and lifecycle tooling.
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
