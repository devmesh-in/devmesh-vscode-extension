# DevMesh

**Coding challenges for the AI-agentic era.**

DevMesh is an editor extension for working through coding challenges with AI assistance. Open the DevMesh panel from the activity bar, paste an invite token or pick a challenge from the public feed, and the workspace loads with a brief, a starter repo, and a sandboxed test runner.

Build the solution using AI as much or as little as you want — chat, file edits, terminal, and a runner all live inside the editor. Submit when ready. DevMesh executes the solution in an isolated sandbox and produces a report at [devmesh.live](https://www.devmesh.live).

## What it does

- Loads a coding challenge brief and starter workspace from an invite link or the public feed.
- Routes model calls through DevMesh's relay so no API keys, provider accounts, or billing are needed.
- Records session activity inside the challenge workspace to generate the evaluation report.
- Submits the solution to a sandboxed test runner and produces an evidence-backed report.

## How models are handled

Model calls in DevMesh go through the DevMesh backend relay. No third-party provider SDKs are bundled and no API keys are read from the local machine. Token usage is shown live in the sidebar.

## Privacy

DevMesh records your session activity inside the active challenge workspace as part of the evaluation. Activity in other editor windows, personal repositories, or files outside the challenge workspace is not recorded. Consent is acknowledged at invite acceptance.

Full policy: [devmesh.live/privacy](https://www.devmesh.live/privacy). For data deletion or access requests, contact [team@devmesh.live](mailto:team@devmesh.live).

## Links

- Product: [devmesh.live](https://www.devmesh.live)
- Documentation: [devmesh.live/docs](https://www.devmesh.live/docs)
- Contact: [team@devmesh.live](mailto:team@devmesh.live)

## License

Apache License 2.0. The full license text ships in the extension package.
