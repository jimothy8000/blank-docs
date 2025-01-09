---
title: Ingest Vehicle Acceleration
excerpt: >-
  Post vehicle telemetry including acceleration & speed to Tirematics


  Tirematics supports 2 identification methods to map telemetries to a specific
  vehicle. Option 1: dId + dt Option 2: vId + rs.

  If the both are provided in the telemetry, then Tirematics will use the option
  1.
api:
  file: bridgestone.json
  operationId: createVehicleTelemetry
hidden: false
---