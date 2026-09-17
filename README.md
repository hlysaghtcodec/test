# test

Scratch repository for validating the Azure Boards <-> GitHub integration.

## Purpose

Proves that commits pushed to a GitHub-hosted repository can link to work items in the
Azure DevOps project `codecdss/Azure.AI.Workbase`, without that repository living in
Azure Repos.

This repo holds no product code and is not referenced by any build or deployment.

## How the link works

The Azure Boards GitHub App is installed on the `hlysaghtcodec` GitHub account and granted
access to this repository. A commit message, PR title, or PR description containing `AB#<id>`
creates a link to work item `<id>` in `Azure.AI.Workbase`.

    git commit -m "Some change. AB#123"

State transitions (`Fixes AB#123`) only apply to commits reaching the default branch.

## Configuration

| Setting | Value |
|---|---|
| Azure DevOps organization | https://dev.azure.com/codecdss |
| Azure DevOps project | Azure.AI.Workbase |
| GitHub account | hlysaghtcodec |
| Default branch | main |

No Azure Pipelines connection is configured for this repository.
