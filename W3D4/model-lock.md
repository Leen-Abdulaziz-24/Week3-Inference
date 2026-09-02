# Model lock (team record)

Fill every field. This is your team's record of the model you serve for the rest
of the course. The green check reads this file and refuses template placeholders,
so replace every placeholder line with your real value.

## The locked model

- Model id: `Qwen/Qwen2.5-1.5B-Instruct-AWQ`
  `Qwen/Qwen2.5-1.5B-Instruct-AWQ` or the pocket known-good
  `Qwen/Qwen2.5-1.5B-Instruct`
- Quantisation: `awq`
- Why this one: Passed the smoke test 10/10, provides AWQ memory benefits, and maintained acceptable quality compared with fp16.

## The launch flags

The exact vLLM flags your team runs. Copy them from the SERVER_ARGS you launched
with.


```
--model Qwen/Qwen2.5-1.5B-Instruct-AWQ --dtype half --max-model-len 4096 
--gpu-memory-utilization 0.85 --port 8000 --quantization awq 
--enable-auto-tool-choice --tool-call-parser hermes
```


- Tool-call parser: `hermes` (Qwen2.5, Hermes-3) or `llama3_json`
  (Llama-3.1)

## The smoke score

- Score (valid behaviours out of 10): `10`
- Distractor stayed call-free in the majority: `yes`
- Passed the gate (>= 8/10 and distractor majority clean): `yes`
- Measured against: both, AWQ `10/10` and fp16 `10/10`

## Quality spot check note

- AWQ mostly held up compared with fp16, with no major degradation, although fp16 was slightly clearer on some prompts.
