---
title: Ingest Compressed (Gzip) Vehicle Telemetries
excerpt: >+
  Post compressed (Gzip) vehicle telemetry including acceleration & speed to
  Tirematics.


  Tirematics supports 2 identification methods to map telemetries to a specific
  vehicle. Option 1: tId + dt Option 2: vId + rs. If the both are provided in
  the telemetry, then Tirematics will use the option 1.

api:
  file: bridgestone.json
  operationId: createCompressedVehicleTelemetry
hidden: false
---