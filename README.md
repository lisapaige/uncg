# uncg

UNC Greensboro instance data: crawl configs (the whitelist SSOT), crawl and
chunk snapshots, and eval data as it grows. The crawl/chunk how-to lives in
[km-pipeline](https://github.com/lisapaige/km-pipeline)'s stage READMEs.

```
data/crawl/config/<subject>/        # tree.yaml — tracked, the scope decisions
data/crawl/<subject>/<run_id>/      # crawl outputs (untracked)
data/chunks/<subject>/<run_id>/     # chunk outputs + entities artifact (untracked)
prompts/                            # chunker failcase ledger, prompt vars
```

Local only: `.env` (workspace API keys, mint-URL comments inline).

```bash
uv sync
pre-commit install
```
