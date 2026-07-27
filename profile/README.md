# UNS DataHub

Open-source building blocks for industrial Unified Namespace systems.

**Website:** [www.uns-datahub.com](https://www.uns-datahub.com)

UNS DataHub turns fragmented industrial signals into a governed, queryable
data layer. Python, TypeScript and Node-RED applications publish, process,
archive, and query operational data through a consistent MQTT-based namespace,
preserving the same context for live and historical values.

The public repositories in this organization are designed to cover distinct
roles in a complete flow. Visit the website for the project map, architecture,
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

### Private preview: UNS DataHub Runtime

UNS DataHub Runtime is the easiest way to run the complete integrated stack
locally. It brings together the controller, local infrastructure, setup,
configuration, and lifecycle tooling in one deployable environment. Typed secret
references can resolve from environment variables or optionally from Infisical,
including Machine Identity-backed bootstrap. The add-on catalog can combine
compatible public GitHub add-ons with approved services from configured GitHub
or Azure DevOps sources. Runtime also validates service configuration against
packaged schemas, retains per-instance snapshots, and preflights matching
versions and configuration before starting workloads on another controller.

The SDKs, supporting services, reference application, and bootstrap are public
and available independently. The integrated Runtime is currently distributed
through a private preview.

Users with preview access can install the public, version-matched bootstrap on
macOS or Linux:

```sh
curl -fsSL \
  https://github.com/uns-datahub/uns-datahub-bootstrap/releases/latest/download/install.sh |
  sh

"$HOME/.local/bin/uns-bootstrap" install
```

The bootstrap verifies the matching download and starts the setup wizard.
Docker or Podman with Compose is required. Complete installation and operating
instructions are in the Runtime `README.md` included with the downloaded
bundle.

[Open Runtime documentation](https://www.uns-datahub.com/docs/).
[Review the public bootstrap repository](https://github.com/uns-datahub/uns-datahub-bootstrap).
Need preview access?
[Join the email-only access list](https://www.uns-datahub.com/#early-access).

The controller remains a component of the Runtime architecture; the planned
public-facing distribution is `uns-datahub-runtime`, rather than a standalone
`uns-datahub-controller` release.

| Repository | Purpose |
| --- | --- |
| [`uns-kit`](https://github.com/uns-datahub/uns-kit) | TypeScript and Python toolkits, runtime libraries, and project scaffolding for UNS applications |
| [`rtt-demo-app`](https://github.com/uns-datahub/rtt-demo-app) | Hot rolling mill simulator and end-to-end example built with `@uns-kit` |
| [`uns-archiver`](https://github.com/uns-datahub/uns-archiver) | QuestDB archiver for UNS data and table packets |
| [`uns-api-global`](https://github.com/uns-datahub/uns-api-global) | Authenticated REST API for current and historical UNS data |
| [`node-red-contrib-uns`](https://github.com/uns-datahub/node-red-contrib-uns) | Node-RED nodes for subscribing to and publishing UNS messages |
| [`uns-datahub-bootstrap`](https://github.com/uns-datahub/uns-datahub-bootstrap) | Minimal verified installer for version-matched Runtime releases |

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

Each public component repository documents its own prerequisites,
configuration, and verification commands. For a first look at the open
components, use `rtt-demo-app` as the example application and `uns-kit` as the
TypeScript and Python library reference.

## Roadmap

The open stack is planned to expand with:

- `uns-datahub-runtime` — currently a private preview and planned as the deployable public entry point that connects the controller, local infrastructure, configuration, and lifecycle tooling.
- `uns-bridge-mqtt` — an external MQTT mapping bridge for bringing existing third-party topic structures and payloads into a governed UNS.
- `uns-bridge-opcua` — mapping OPC UA nodes and values into the same model.

Assistant capabilities are planned for a later phase. Current private
implementation work explores cited operational guidance over live and
historical signals, operator-reviewed schema proposals, validated TypeScript
and Python service-bundle generation, and disabled-by-default local
MCP-compatible tool access with scoped tokens and auditing. Public scope and
delivery are still under review.

Follow the latest overview at [www.uns-datahub.com](https://www.uns-datahub.com/#roadmap).

## Participate

- Read the shared [contribution guide](https://github.com/uns-datahub/.github/blob/main/CONTRIBUTING.md).
- Report security issues privately as described in the
  [security policy](https://github.com/uns-datahub/.github/blob/main/SECURITY.md).
- Use the issue tracker of the affected repository for bugs and focused feature
  requests.

Unless a repository says otherwise, public source is licensed under the MIT
License.