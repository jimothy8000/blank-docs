---
title: Create Update Associated Vehicles
excerpt: >-
  This API allows you to specify what other vehicles physically connected to the
  vehicle are.(e.g. tractor and trailer)

  We refer to such connected vehicles as “Associated Vehicles.” 


  Within this API, you can specify multiple Associated Vehicles for a single
  vehicle.

  Currently, Associated Vehicle(s) are used in the following ways

  - Display the vehicle and associated vehicle(s) together on Open Issue Report
  (refer to ReadMe article,
  https://dash.readme.com/project/tirematics/v4.0/docs/built-in-alert-channels) 

  - Calculation of the “LOAD_COMPOSITE” of PredictionCode (refer to ReadMe
  article, https://docs.bridgestonedigital.com/tirematics/docs/prediction-codes)
api:
  file: bridgestone.json
  operationId: createAssociatedVehicles
hidden: false
---