# kurowebgadge
## About scouting policy

```scala
val (t, f) = scoutsStream().partition(s => {
  s.source.registeredBy(this) || (s.from[Email] && s.recipient == "kisaragi.effective+jobs.handler@gmail.com")
})

t.foreach(accept)
f.foreach { s =>
  requestPayment(s, jpy(100_000 + 105.86 * s.body.codePoints.count))
  discard(s)
}
```
