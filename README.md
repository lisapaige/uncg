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

Run a crawl — the commands resolve only inside a km-pipeline checkout
(this repo does not install km-pipeline):

```bash
cd ~/code/km-pipeline
uv run km-crawl ~/code/uncg/data/crawl/config/general_tracer/tree.yaml --out-dir ~/code/uncg/data/crawl
uv run km-crawl ~/code/uncg/data/crawl/config/general/tree.yaml --out-dir ~/code/uncg/data/crawl
```
