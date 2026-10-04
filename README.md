# AI Data Engineer Capstone Project

This directory contains the implementation for the North York Housing Intelligence Agent capstone.

## Purpose

The implementation is organized to satisfy the rubric in `requirements/capstone-project-submission.md` with a scope that is ambitious enough to score well and narrow enough to finish reliably.

## MVP Summary

The project delivers:

- a Spark Bronze/Silver/Gold pipeline over North York housing context data
- a real third-party API integration using TTC GTFS-Realtime
- a Lakebase operational schema for user actions
- a RAG layer over curated housing and planning documents
- an action-taking AI agent with real write tools
- an analytics pipeline tied to operational and agent activity
- a Databricks App backend MVP deployed from `project/src/app`

## Current Data Status

The current Silver implementation uses a Delta lookup table for neighborhood key standardization and a matched-subset neighborhood model for integrated outputs.

Latest observed coverage:

- `142` matched neighborhood rows in `silver_neighborhood_features`
- `141` rows with boundary matches
- `142` rows with crime matches
- `125` rows currently eligible for Gold outputs

The remaining excluded rows are tracked explicitly through lookup-table logic and deferred as future expansion work.

## Current Status

All MVP implementation phases through Phase 8 are now complete at the backend validation level.

Confirmed implementation status:

- TTC GTFS-Realtime Bronze, Silver, and Gold transit context are implemented
- curated housing/planning RAG ingestion, chunking, vector indexing, and retrieval validation are implemented
- Lakebase operational schema, seed data, analytics ingestion, and aggregate metrics are implemented
- the Databricks App backend is deployed successfully from `project/src/app`
- the deployed app now serves all planned MVP backend endpoints:
  - `/health`
  - `/api/neighborhoods`
  - `/api/neighborhoods/{canonical_key}`
  - `/api/rankings/{metric}`
  - `/api/transit/{canonical_key}`
  - `/api/watchlists/{user_id}`

Phase 8 follow-up work is now limited to richer frontend flows, evidence capture, and final rubric packaging.

## Documentation Map

- `docs/01-mvp-scope.md`
- `docs/02-rubric-checklist.md`
- `docs/03-implementation-phases.md`
- `docs/04-project-structure.md`
- `docs/05-requirement-verification.md`
- `docs/06-demo-checklist.md`
- `docs/08-phase8-run-order.md`

## Build Approach

We will implement and test phase by phase:

1. Lock scope and scaffold the project.
2. Build structured data pipelines.
3. Add API ingestion.
4. Add Lakebase operational storage.
5. Add unstructured retrieval and RAG.
6. Add the action-taking agent.
7. Add analytics.
8. Build, deploy, and validate the application.
