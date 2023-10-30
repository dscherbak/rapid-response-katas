# Export observations into the camptrap DB exchange format

## Context:

The requirements dictate to have the possibility to publish the species occurrences to GBIF the Camtrap DP data exchange format.

## Decision:

Based on our research, we've decided that all the required data for generating the files for Camtrap DB format is present in the Observations Service.
On the export request, the Observation service will gather all the required data and process it, creating an archive file with Camtrap DB files.
Users can download the archive for further distribution using the app or host it in a shared storage.

## Consequences:

This export functionality enables researchers and conservationists to find value in the data collected through user observations. 

## Status:

Approved
