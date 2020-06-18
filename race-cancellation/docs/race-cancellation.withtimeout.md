<!-- Do not edit this file. It is automatically generated by API Documenter. -->

[Home](./index.md) &gt; [race-cancellation](./race-cancellation.md) &gt; [withTimeout](./race-cancellation.withtimeout.md)

## withTimeout() function

Wrap a cancellable async function with a timeout.

<b>Signature:</b>

```typescript
export default function withTimeout<TResult>(cancellableAsync: CancellableAsyncFn<TResult>, milliseconds: number, raceCancel?: RaceCancelFn): Promise<TResult>;
```

## Parameters

|  Parameter | Type | Description |
|  --- | --- | --- |
|  cancellableAsync | [CancellableAsyncFn](./race-cancellation.cancellableasyncfn.md)<!-- -->&lt;TResult&gt; | a [CancellableAsyncFn](./race-cancellation.cancellableasyncfn.md) function |
|  milliseconds | number | a timeout in miliseconds |
|  raceCancel | [RaceCancelFn](./race-cancellation.racecancelfn.md) | an optional outer scope [RaceCancelFn](./race-cancellation.racecancelfn.md) function that will be combined with the timeout race before being passed to the [CancellableAsyncFn](./race-cancellation.cancellableasyncfn.md) function |

<b>Returns:</b>

Promise&lt;TResult&gt;

## Remarks


## Example


```js
async function fetchWithTimeout(url, timeoutMs, raceCancel) {
  return await withTimeout((raceTimeout) => cancellableFetch(url, raceTimeout), timeoutMs, raceCancel);
}

```
