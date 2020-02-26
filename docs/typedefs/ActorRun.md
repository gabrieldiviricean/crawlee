---
id: actor-run
title: ActorRun
---

<a name="actorrun"></a>

Represents information about an actor run, as returned by the [`Apify.call()`](/docs/api/apify#call) or [`Apify.callTask()`](/docs/api/apify#calltask)
function. The object is almost equivalent to the JSON response of the
[Actor run](https://apify.com/docs/api/v2#/reference/actors/run-collection/run-actor) Apify API endpoint and extended with certain fields. For more
details, see [Runs.](https://docs.apify.com/actor/run)

## Properties

### `id`

**Type**: `String`

Actor run ID

---

### `actId`

**Type**: `String`

Actor ID

---

### `startedAt`

**Type**: `Date`

Time when the actor run started

---

### `finishedAt`

**Type**: `Date`

Time when the actor run finished. Contains `null` for running actors.

---

### `status`

**Type**: `String`

Status of the run. For possible values, see [Run lifecycle](https://docs.apify.com/actor/run#lifecycle) in Apify actor documentation.

---

### `meta`

**Type**: `Object`

Actor run meta-data. For example:

```
{
  "origin": "API",
  "clientIp": "1.2.3.4",
  "userAgent": "ApifyClient/0.2.13 (Linux; Node/v8.11.3)"
}
```

---

### `stats`

**Type**: `Object`

An object containing various actor run statistics. For example:

```
{
  "inputBodyLen": 22,
  "restartCount": 0,
  "workersUsed": 1,
}
```

Beware that object fields might change in future releases.

---

### `options`

**Type**: `Object`

Actor run options. For example:

```
{
  "build": "latest",
  "waitSecs": 0,
  "memoryMbytes": 256,
  "diskMbytes": 512
}
```

---

### `buildId`

**Type**: `String`

ID of the actor build used for the run. For details, see [Builds](https://docs.apify.com/actor/build) in Apify actor documentation.

---

### `buildNumber`

**Type**: `String`

Number of the actor build used for the run. For example, `0.0.10`.

---

### `exitCode`

**Type**: `Number`

Exit code of the actor run process. It's `null` if actor is still running.

---

### `defaultKeyValueStoreId`

**Type**: `String`

ID of the default key-value store associated with the actor run. See [`KeyValueStore`](/docs/api/key-value-store) for details.

---

### `defaultDatasetId`

**Type**: `String`

ID of the default dataset associated with the actor run. See [`Dataset`](/docs/api/dataset) for details.

---

### `defaultRequestQueueId`

**Type**: `String`

ID of the default request queue associated with the actor run. See [`RequestQueue`](/docs/api/request-queue) for details.

---

### `containerUrl`

**Type**: `String`

URL on which the web server running inside actor run's Docker container can be accessed. For more details, see
[Container web server](https://docs.apify.com/actor/run#container-web-server) in Apify actor documentation.

---

### `output`

**Type**: `Object`

Contains output of the actor run. The value is `null` or `undefined` in case the actor is still running, or if you pass `false` to the `fetchOutput`
option of [`Apify.call()`](/docs/api/apify#call).

For example:

```
{
  "contentType": "application/json; charset=utf-8",
  "body": {
    "message": "Hello world!"
  }
}
```

---