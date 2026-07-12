# SPASM: Stable Persona-driven Agent Simulation for Multi-turn Dialogue Generation

This repository contains the dialogue datasets for the paper
[SPASM: Stable Persona-driven Agent Simulation for Multi-turn Dialogue Generation](https://aclanthology.org/2026.findings-acl.412/)
(Findings of ACL 2026).

## Available datasets

| Version | Model pairing | Personas | Conversations per persona | Conversations | Status |
|---|---|---:|---:|---:|---|
| v1.0.0 | DeepSeek-V4-Flash / DeepSeek-V4-Flash | 500 | 10 | 5,000 | Available |

## Dataset statistics

| Property | Value |
|---|---:|
| Total conversations | 5,000 |
| Total utterances | 44,950 |
| Mean utterances per conversation | 8.99 |
| Maximum observed utterances | 36 |
| Natural terminations | 5,000 (100%) |
| Exact duplicate conversations | 0 |
| Language | Primarily English; multilingual generations may occur |

## Data format

The dataset is distributed as JSON Lines. Each record contains:

```json
{
  "persona_id": 0,
  "conversation_id": 0,
  "persona_fields": {},
  "persona_description": "...",
  "turns": [
    {"speaker": "client", "turn_index": 0, "text": "..."},
    {"speaker": "tested", "turn_index": 1, "text": "..."}
  ],
  "termination_reason": "natural_termination"
}
```

See [DATASET_CARD.md](DATASET_CARD.md) for generation configuration,
validation, intended uses, and limitations.

## Repository contents

- `data/spasm_deepseek_v4_flash_500x10.jsonl` - dialogue records
- `DATASET_CARD.md` - dataset documentation
- `metadata/run_stats.json` - generation statistics and distributions
- `metadata/role_audit_summary.json` - role-consistency audit summary
- `SHA256SUMS.txt` - data integrity checksum
- `CITATION.cff` - citation metadata
- `LICENSE` - CC BY 4.0 dataset license

## To do

Future coverage is subject to API access, compute budget, and validation. Model
names below indicate planned families rather than a release commitment.

- [x] DeepSeek-V4-Flash
- [ ] OpenAI GPT-5 family: GPT-5.6, GPT-5.5, GPT-5.4, GPT-5.4 mini, GPT-5.4 nano, GPT-5 pro
- [ ] OpenAI GPT-4.1 family: GPT-4.1, GPT-4.1 mini, GPT-4.1 nano
- [ ] OpenAI reasoning/open-weight families: o3, o4-mini, gpt-oss-120b, gpt-oss-20b
- [ ] Anthropic Claude family: Claude Opus, Claude Sonnet, Claude Haiku
- [ ] Alibaba Qwen family: Qwen3.5, Qwen3-Max, Qwen3-Plus, Qwen3-Coder, Qwen3-VL, Qwen3-235B-A22B, Qwen3-30B-A3B
- [ ] Google Gemini family: Gemini Pro, Gemini Flash, Gemini Flash-Lite
- [ ] xAI Grok family
- [ ] Meta Llama family
- [ ] Mistral AI family: Mistral Large, Mistral Small, Magistral, Codestral, Mixtral
- [ ] Cohere Command family
- [ ] DeepSeek reasoning and general families: DeepSeek-R1, DeepSeek-V4-Pro
- [ ] Moonshot AI Kimi family
- [ ] Zhipu AI GLM family
- [ ] MiniMax family
- [ ] Baidu ERNIE family
- [ ] Tencent Hunyuan family
- [ ] ByteDance Doubao family
- [ ] Amazon Nova family
- [ ] Microsoft Phi family
- [ ] NVIDIA Nemotron family
- [ ] AI21 Jamba family
- [ ] 01.AI Yi family
- [ ] InternLM family

## Quality controls

- Structural validation of all 5,000 records
- Complete `500 x 10` coverage with no missing persona/conversation pairs
- Full-coverage automated role-consistency screening
- Targeted human review and regeneration of flagged records
- Deterministic scans for AI-identity leakage, prompt leakage, credentials,
  email addresses, URLs, empty messages, and exact duplicates
- Redaction of generated contact-, account-, and reference-like strings

The automated role-consistency screen is not a substitute for full human
annotation.

## Citation

If you use this dataset, please cite:

```bibtex
@inproceedings{luo2026spasm,
  title={SPASM: Stable Persona-driven Agent Simulation for Multi-turn Dialogue Generation},
  author={Luo, Han and Laban, Guy},
  booktitle={Findings of the Association for Computational Linguistics: ACL 2026},
  pages={8455--8475},
  year={2026}
}
```

When reporting results, please also identify the dataset version and model
pairing used.

## License

The dataset and accompanying dataset documentation are released under the
[Creative Commons Attribution 4.0 International License](LICENSE).
