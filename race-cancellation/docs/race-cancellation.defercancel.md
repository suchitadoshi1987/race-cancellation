<!-- Do not edit this file. It is automatically generated by API Documenter. -->

[Home](./index.md) &gt; [race-cancellation](./race-cancellation.md) &gt; [deferCancel](./race-cancellation.defercancel.md)

## deferCancel() function

Create a tuple of [RaceCancelFn](./race-cancellation.racecancelfn.md) and [ResolveCancelFn](./race-cancellation.resolvecancelfn.md) functions.

<b>Signature:</b>

```typescript
export default function deferCancel(): [RaceCancelFn, ResolveCancelFn];
```
<b>Returns:</b>

\[[RaceCancelFn](./race-cancellation.racecancelfn.md)<!-- -->, [ResolveCancelFn](./race-cancellation.resolvecancelfn.md)<!-- -->\]

## Remarks

In general, it is better to use [withCancel()](./race-cancellation.withcancel.md) to scope cancellation to an async task so that the cancellation concern is cleaned up.

If the cancellation concern will be GC'ed with the cancel already and no cleanup needed like removing an event listener than this method can be simpler.
