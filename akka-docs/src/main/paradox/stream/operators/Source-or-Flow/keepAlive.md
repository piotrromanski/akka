# keepAlive

Injects additional (configured) elements if upstream does not emit for a configured amount of time.

@ref[Time aware stages](../index.md#time-aware-stages)

@@@div { .group-scala }

## Signature

@@signature [Flow.scala]($akka$/akka-stream/src/main/scala/akka/stream/scaladsl/Flow.scala) { #keepAlive }

@@@

## Description

Injects additional (configured) elements if upstream does not emit for a configured amount of time.


@@@div { .callout }

**emits** when upstream emits an element or if the upstream was idle for the configured period

**backpressures** when downstream backpressures

**completes** when upstream completes

**cancels** when downstream cancels

@@@

