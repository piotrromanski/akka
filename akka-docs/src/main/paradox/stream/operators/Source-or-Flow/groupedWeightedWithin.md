# groupedWeightedWithin

Chunk up this stream into groups of elements received within a time window, or limited by the weight of the elements, whatever happens first.

@ref[Timer driven stages](../index.md#timer-driven-stages)

@@@div { .group-scala }

## Signature

@@signature [Flow.scala]($akka$/akka-stream/src/main/scala/akka/stream/scaladsl/Flow.scala) { #groupedWeightedWithin }

@@@

## Description

Chunk up this stream into groups of elements received within a time window, or limited by the weight of the elements,
whatever happens first. Empty groups will not be emitted if no elements are received from upstream.
The last group before end-of-stream will contain the buffered elements since the previously emitted group.


@@@div { .callout }

**emits** when the configured time elapses since the last group has been emitted,
but not if no elements has been grouped (i.e: no empty groups), or when weight limit has been reached.

**backpressures** downstream backpressures, and buffered group (+ pending element) weighs more than *maxWeight*

**completes** when upstream completes

@@@

