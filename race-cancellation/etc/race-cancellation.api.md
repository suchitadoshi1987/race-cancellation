## API Report File for "race-cancellation"

> Do not edit this file. It is a report generated by [API Extractor](https://api-extractor.com/).

```ts

// @public
export type AsyncFn<TResult> = () => PromiseLike<TResult>;

// @public
export interface CancelError<TName extends string = "CancelError"> extends Error {
    // (undocumented)
    isCancelled: true;
    // (undocumented)
    name: TName;
}

// @public
export type CancelExecutorFn = (resolve: () => void) => void;

// @public
export type CancellableAsyncFn<TResult> = (raceCancel: RaceCancelFn) => Promise<TResult>;

// @public
export function cancellablePromise<TResult>(disposableExecutor: DisposableExecutorFn<TResult>, raceCancel?: RaceCancelFn): Promise<TResult>;

// @public
export type CancelReason = CancelError<string> | string;

// @public
export function composeRaceCancel(inner?: RaceCancelFn, outer?: RaceCancelFn): RaceCancelFn;

// @public
export function deferCancel(): [RaceCancelFn, ResolveCancelFn];

// @public
export type DisposableCancelExecutorFn = (resolve: ResolveCancelFn) => DisposeFn;

// @public
export type DisposableExecutorFn<TResult> = (resolve: (value?: TResult | PromiseLike<TResult>) => void, reject: (reason?: unknown) => void) => DisposeFn;

// @public
export type DisposeFn = () => void;

// @public
export type IsCancelledFn = () => boolean;

// @public
export function newRaceCancel(isCancelled: IsCancelledFn, executor: CancelExecutorFn, cancelReason?: (() => CancelReason | undefined) | CancelReason): RaceCancelFn;

// @public
export const noopRaceCancel: RaceCancelFn;

// @public
export type RaceCancelFn = <TResult>(asyncFnOrPromise: AsyncFn<TResult> | PromiseLike<TResult>) => Promise<TResult>;

// @public
export type ResolveCancelFn = (reason?: CancelReason) => void;

// @public
export interface TimeoutError<TName extends string = "TimeoutError"> extends CancelError<TName> {
    // (undocumented)
    isTimeout: true;
}

// @public
export function withCancel<TResult>(cancellableAsync: CancellableAsyncFn<TResult>, disposableCancelExecutor: DisposableCancelExecutorFn, outerRaceCancel?: RaceCancelFn): Promise<TResult>;

// @public
export function withCancelPending<TResult>(cancellableAsync: CancellableAsyncFn<TResult>, outerRaceCancel?: RaceCancelFn): Promise<TResult>;

// @public
export function withTimeout<TResult>(cancellableAsync: CancellableAsyncFn<TResult>, milliseconds: number, raceCancel?: RaceCancelFn): Promise<TResult>;


```
