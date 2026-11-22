# Speculative Decoding for Inference Optimization

Empirical research into whether draft-model speculative decoding improves local large language model inference speed without changing the target model's output quality.

## Research question

Under what target-draft model pairings and decoding configurations does speculative decoding reduce inference latency and increase generation throughput while preserving target-model output quality in local LLM deployment?

## Background

Autoregressive generation normally uses the target model once for every newly generated token. Speculative decoding adds a smaller draft model that proposes several tokens, after which the target model verifies those proposals in a single step. Accepted tokens can increase throughput; rejected proposals can add overhead.

## Planned comparison

- Standard target-model decoding
- Draft-model speculative decoding
- Multiple target-draft model pairings
- Multiple draft lengths
- Relevant model precision and quantization settings

## Metrics

- Time to first token
- Total generation latency
- Generation throughput in tokens per second
- Draft-token acceptance rate
- Target-model verification rate
- Peak RAM usage
- Stored model size
- Output consistency and task accuracy

## Experimental principles

- Use identical prompts and sampling settings for all comparisons.
- Keep the target model fixed when comparing draft configurations.
- Report both absolute measurements and speedup relative to standard decoding.
- Separate speed improvements from output-quality changes.
- Repeat measurements and report variability where practical.

## Planned research contributions

This project aims to provide a reproducible systems-level evaluation of when speculative decoding is useful for locally deployed language models, including cases where draft-model overhead may eliminate the expected speedup.

## Status

Project initialized. Experimental design, model selection, and baseline implementation are pending.
