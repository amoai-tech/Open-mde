# MDE tenant (SAN-1717)

This package adapts the official Fintech example for one default customer-facing Ask MDE Bot and ten shared skills. The original Fintech package remains unchanged.

Build from the repository root:

```sh
docker build -f examples/mde/Dockerfile -t mde-openbot:dev .
```

The base image is pinned to the official v1.2.0 release manifest. The model reference is inherited from the Fintech example; real provider access still needs a streamed chat test. No secrets are included. Supply the existing deployment's environment securely; never point operational database migrations at the MDE business Supabase database.

No package channels are seeded: use supported per-user conversation creation and membership. No unconnected knowledge sources are declared. Skill tool declarations do not grant apps. Exa and Firecrawl are supplementary; MDE business tools and Mastra router integration remain SAN-1720. The built-in Bot is a development baseline until the supported remote adapter and actor context are proven.

Do not apply this package blindly to the existing Fintech volume: the current manually created MDE Bot and private /rentals skill could collide or survive package seeding. Verify supported migration/retirement and preserve existing records. Shared browser/computer is not a tenant boundary. Keep the current reference deployment unchanged until boot, reseed, two-user isolation, grants and actual MDE journeys pass. See SAN-1719 for identity integration.

References: https://github.com/CopilotKit/OpenBot/blob/v1.2.0/docs/configuration.md#tenant-package and https://github.com/CopilotKit/OpenBot/releases/tag/v1.2.0.
