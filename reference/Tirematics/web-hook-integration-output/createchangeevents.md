---
title: Change Events (Deprecated)
excerpt: |-
  Events contain only changes detected for mounitng positions and sensors.

  For example for following list of events: |

  1. Sensor 1 SPLOW (WARNING) DETECTED
  2. Sensor 1 SBLOW (WARNING) DETECTED, Sensor 2: SPLOW (WARNING) DETECTED
  3. Sensor 1 SPLOW SEVERITY_CHANGED (CRITICAL)
  4. Sensor 2 SPHGH (WARNING)
  5. Sensor 2 SPHGH SEVERITY_CHANGED (CRITICAL)
  6. Sensor 2 SPHGH RESOLVED

  When consumed the final result are: |

  - Sensor 1: SPLOW (CRITICAL), SBLOW (WARNING)
  - Sensor 2: SPLOW (WARNING)


  Restrictions:

  - The events can be buffered and sent in chronological order.
  - The chronological order of events are sent in the context of device.
  - Outdated events and events with future time are ignored.

   #### *NOTE*: *Please replace PATH with your webhook path and communicate that with Tirematics Team.*
api:
  file: bridgestone.json
  operationId: createChangeEvents
deprecated: true
hidden: false
---