# Google Ads Reporting Tool

Private, single-operator integration with the Google Ads API, operated by
César Carro — an independent paid media specialist — to read and analyze
Google Ads performance data for the accounts under his manager account
(MCC 295-651-2723), including his own and those of a small number of direct
clients he manages.

- [Home](https://ccarro-d.github.io/google-ads-integration/)
- [Privacy Policy](https://ccarro-d.github.io/google-ads-integration/privacy.html)
- [Terms of Service](https://ccarro-d.github.io/google-ads-integration/terms.html)

## What it does

Read-only reporting and analysis over the Google Ads API. It does **not**
create, edit, or delete any advertising entity. There is no public interface
and no external users: only the operator runs it, locally.

## How it is built

Built on Google's official Google Ads MCP server
([`googleads/google-ads-mcp`](https://github.com/googleads/google-ads-mcp)),
run locally as a command-line process:

```bash
pipx run --spec git+https://github.com/googleads/google-ads-mcp.git google-ads-mcp
```

It exposes three read-only operations: GAQL `search`, listing accessible
customers, and reading resource metadata. It is associated with Google Cloud
project number `531937630254` and operates under manager account
`295-651-2723`.

## Scope

The integration requests a single OAuth scope,
`https://www.googleapis.com/auth/adwords`, and no other.

## Authentication and credentials

Authentication uses Google OAuth 2.0 (Application Default Credentials).
Credentials are stored in a local file with restricted permissions, are never
committed to version control, and are never sent to any intermediary or
third-party server.

## Status

Implemented and functional: the MCP server is registered and connected in the
operator's local environment, and used for read-only reporting on the accounts
under management.
