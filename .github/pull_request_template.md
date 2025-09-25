## Summary

- Added NFT plugin core (schemas, registry) and OpenSea plugin (reads + non-custodial write preps).
- Refactored OpenSea MCP to use the plugin; added new `nft` skill in Quickstart Agent.
- Added Magic Eden plugin skeleton aligned to the same interface (awaiting base URL/API key).
- Non-custodial by default; `ENABLE_OPENSEA_WRITE=false`. No personal creds used.
- CORS + SSE/STDIO transports verified in Inspector.

## Action Needed from Vibekit Team

- Provide `MAGICEDEN_BASE_URL` and `MAGICEDEN_API_KEY` to finalize Magic Eden plugin.
- Provide `OPENSEA_API_KEY` and `ARBITRUM_RPC_URL` (team-provided) for local end-to-end runs.

## Details

- Introduces `@vibekit/onchain-actions-nft` (plugin interface + zod schemas + registry)
- Implements `@vibekit/onchain-actions-opensea` (read ops + non-custodial write preparation)
- Adds `@vibekit/onchain-actions-magiceden` skeleton matching the same interface
- Refactors OpenSea MCP to use the plugin system
- Wires new `nft` skill into Quickstart Agent

## Notes

- All write actions are non-custodial (prepare-only). No private keys handled.
- Inspector connectivity verified over HTTP/SSE with permissive CORS.

## Testing

- `pnpm install && pnpm build` at `typescript/` passes.
- Read tools return data via OpenSea API v2; write tools return prepared tx payloads.

## Links

- Fork/Branch: https://github.com/oxdev6/EmberAGI-arbitrum-vibekit/tree/feat/nft-plugin-integration
- Compare (open PR): https://github.com/EmberAGI/arbitrum-vibekit/compare/main...oxdev6:feat/nft-plugin-integration?expand=1
