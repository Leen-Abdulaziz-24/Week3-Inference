# Capacity note (team, one page)

Fill every field from your bench_report.json. The green check reads this file and 
refuses template placeholders

## The numbers

- Locked model: Qwen/Qwen2.5-1.5B-Instruct
- Target p95 end-to-end latency (your SLO today): `3.0` seconds
- Knee concurrency (highest concurrency whose p95 is still under target):
  `16`
- Tokens per second at the knee: `574.45`
- Max sustainable request rate at the target p95: `5.31 req/s`
  can serve at the knee before p95 crosses target.

## The limiting family

One sentence, using this morning's triage lens (compute vs memory vs overhead):
which family limits this stack at the knee, and the tell that points to it.

- "No clear limiting family was reached: throughput was still rising at
  concurrency 16 while p95 remained under the 3.0 s SLO."

## Why the knee, not the peak

One sentence in your own words on why you report the knee at the SLO rather than
the peak throughput.

- The knee represents the highest concurrency that still meets the latency SLO,
  while peak throughput may come at the cost of unacceptable latency.