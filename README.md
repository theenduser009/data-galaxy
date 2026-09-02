# Data Galaxy

DataGalaxy processing and column-lineage assets for the SourceAmerica Microsoft Fabric ETL flow.

## Column-lineage pilot

The importable pilot package is in `data-processing/column-lineage-pilot/`:

1. `DataProcessing-1-General.csv` defines the flow and processing hierarchy.
2. `DataProcessing-4-DataProcessingItems.csv` maps three validated `account` columns across Landing, Bronze, Silver, Gold CDC, and final `dbo`.
3. `DataProcessing-5-Linked-Objects.csv` connects the EPL orchestrator to the four stage pipelines.

Import the files in that order for a new setup. The Dictionary databases, models, tables, and columns must already exist. The Data Processing Items file is intentionally a pilot: it maps only `accountid`, `accountnumber`, and `address1_city`, and assumes direct pass-through transformations.

Separate table-level In and Out files are omitted to avoid parallel links that make column lineage harder to read.
