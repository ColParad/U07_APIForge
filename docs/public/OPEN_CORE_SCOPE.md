# APIForge Core — Public Publication Boundary

**Status:** Public policy  
**Applies to:** `ColParad/U07_APIForge`  
**Purpose:** Define what may be published in the clean public APIForge Core repository.

## 1. Public repository purpose

This repository is the public open-source distribution surface for APIForge Core. Public materials must be independently suitable for open-source publication and must not expose internal PolyCode platform operations or unreleased commercial implementation details.

## 2. Allowlisted public material

Material may be published only after review and only when it belongs to one of the following categories:

- public project overview and user-facing documentation;
- independently buildable Core application sources;
- Core request-processing and local-data functionality intended for MIT distribution;
- public UI assets or components intended for the Core distribution;
- public tests for published Core functionality;
- public contribution, security-reporting, release, and changelog information;
- build configuration required solely for the published Core distribution.

Publication requires confirmation that the material does not import, reveal, or require non-public packages or services.

## 3. Material prohibited from public export

The following material must remain in the private canonical development repository unless a separate, explicit publication review approves a sanitized public equivalent:

- internal product handoff, roadmaps, execution plans, and project-control records;
- internal audits, readiness reports, penetration/security findings, and unresolved defect inventories;
- private prompt contracts, agent instructions, and development-control materials;
- authentication, licensing, entitlement, billing, subscription, webhook, or gateway implementation architecture;
- private API contracts, infrastructure topology, deployment configuration, environment-variable inventories, storage-key inventories, and operational runbooks;
- commercial packages or source paths implementing AI, team, cloud-sync, licensing, billing, or other separately distributed capabilities;
- private CI/CD, signing, distribution, release-gate, and commercial packaging configuration;
- secrets, credentials, API keys, tokens, test credentials, private endpoints, or material that facilitates misuse of internal services.

## 4. Code publication gate

No runtime source directory is published from the private repository until all of the following are true:

1. The selected public Core subset builds and tests independently without private packages.
2. Its dependency graph contains no imports of non-public commercial or platform-internal packages.
3. The licensing boundary has been reviewed: every published source file is intended for MIT distribution.
4. A secrets and internal-information scan has passed for both the exported tree and the new public commit history.
5. User-facing claims in the public README are supported by the exported Core implementation.

## 5. Export model

The private repository is the canonical development source. Public publication must use a curated export of approved files into this repository. Never mirror, fork, or copy the private repository history into the public repository.

## 6. Review checklist for each public change

Before merging or committing public material, verify:

- the file is on the public allowlist;
- the file contains no internal documentation, private service contract, operational detail, or credential;
- code imports only public dependencies;
- public product claims match delivered functionality;
- the material is intentionally released under the public repository licence.

A rejected or uncertain file remains private until reviewed.