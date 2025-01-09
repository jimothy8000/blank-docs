---
title: Classify
excerpt: >-
  This endpoint makes a prediction about which label fits the specified text
  inputs best. To make a prediction, Classify uses the provided `examples` of
  text + label pairs as a reference.

  Note: [Fine-tuned models](https://docs.cohere.com/docs/classify-fine-tuning)
  trained on classification examples don't require the `examples` parameter to
  be passed in explicitly.
api:
  file: cohere-processed.json
  operationId: classify
hidden: false
---