<template>
  <section>
    <h1>{{interval$}}</h1>
    <h1>{{timesTwo$}}</h1>
    <h1>{{timesThree$}}</h1>
  </section>
</template>

<script>
import { Observable } from "rxjs"

export default {
  subscriptions() {
    const interval$ = Observable.interval(1000);
    const timesTwo$ = interval$.map(i => i * 2);
    const timesThree$ = interval$.map(i => i * 3);
    return {
      interval$,
      timesTwo$,
      timesThree$
    }
  }
}
</script>

