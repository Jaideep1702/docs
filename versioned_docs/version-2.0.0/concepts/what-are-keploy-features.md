---
id: what-are-keploy-features
title: Keploy Features
sidebar_label: Keploy Features
description: Keploy platform automatically mocks application dependencies and safely replay writes. It does accurate noise detection and statistical de-duplication.
tags:
  - explanation
  - keploy features
  - features
  - record replay test
  - mock mutations
keywords:
  - test cases
  - data dumps
  - keploy features
  - features
  - record replay test
  - mock mutations
---

To kick things off, let's dive into the fundamentals:

## 📽️ Record-Replay Complex API Flows

#### Turn API Calls into Test-Cases and Mocks

With Keploy, you can effortlessly record and replay intricate, distributed API flows as mocks and stubs. It's like having a time machine for your tests! ⏳

Keploy will record all API calls and their subsequent network traffic served by the application. You can utilize your favorite API management tools like [Postman](https://www.postman.com/), [Hoppscotch](https://hoppscotch.io/), or even [Curl](https://curl.se/) to generate test cases.

Keploy automatically [mocks](/concepts/general-glossary.md#1-api-data-mocking) network/external dependencies for **all CRUD operations** with correct responses.

<img src="/gif/record-replay.gif?raw=true" width="80%" alt="API Tools"/>

Once recorded, you have the flexibility to replay and simulate the same flow with mutations/write calls locally or within your CI environment without needing to connect to external services/dependencies.

No more data dumps, stubs, or mocks for dependencies like DBs, internal services, or third-party services like twilio, shopify, or stripe are required anymore. 💡

<img src="/img/mock-dependencies.png?raw=true" width="50%" alt="Mock Application Dependencies"/>

[Idempotency](/concepts/general-glossary.md#2-idempotency) guarantees are also **not required** in the application. Multiple Reads after write operations can be replicated automatically too. 🔄

<img src="/img/record-api.gif?raw=true" width="80%" alt="API Tools"/>

## 🧩 Combined Test Coverage:

#### Run Tests with Mocks Anywhere You Like

Keploy has [native integrations](/concepts/general-glossary.md#4-interoperability) with your unit-testing libraries like `go-test`, `jUnit`, `jest`, `pyTest`.
Keploy gives combined test-coverage and can also be integrated in
existing CI pipelines easily within `go-test`, `jUnit`, `jest`, `pyTest` workflows.

<img src="/gif/replay-tc.gif?raw=true" alt="Keploy Integration with Testing Libraries"  width="80%"/>

Run tests with mocks anywhere you like—**locally on the CLI**, in your **CI pipeline**, or even across a **Kubernetes cluster**. It's testing wherever you want it! 🌍

## ♻️ Multi-Purpose Mocks

#### Re-Use Mocks for Testing Servers

Keploy generated dependency mocks can also be used as test case for the server. These tests can be used for use-cases like chaos testing, e2e testing, integration testing, api and regression testing. 🌟

## 🌐 Code-less EBPF Instrumentation

#### Network Layer Integration makes it Light-Weight

Keploy uses EBPF like a secret sauce to make integration code-less, language agnostic, and oh-so-lightweight. 🍲

## 🔍 Accurate Noise Detection

#### Eliminates random fields for Assertion

Keploy identifies [noisy fields](/concepts/general-glossary.md#3-noisy-field) in the responses accurately like (timestamps, random values) to ensure high quality tests.

As the application serves the API, Keploy re-run that API request with the captured dependency mocks.

[//]: # '<img src="/img/noise-filtration.png?raw=true" alt="Keploy noise filtration"/>'

Keploy identifies differences in API responses, marking them as random/noisy fields. 🧐✅
