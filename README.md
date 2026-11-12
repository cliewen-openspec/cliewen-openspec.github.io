# Cliewen for OpenSpec website

The organization introduction is at https://cliewen-openspec.github.io/ and the guide at https://cliewen-openspec.github.io/guide/.

Documentation, the introduction, and the reusable deployment workflow live in [the product repository](https://github.com/cliewen-openspec/cliewen-openspec). Edit those sources there. This repository contains only the deployment caller; it does not duplicate the guide.

The workflow checks public source every 15 minutes and skips an unchanged revision. GitHub may delay scheduled runs. Pushes here and manual workflow dispatch deploy immediately. The site exposes `source-revision.json` to identify its source commit. No cross-repository write secret is needed.

For an immediate refresh:

```sh
gh workflow run pages.yml --repo cliewen-openspec/cliewen-openspec.github.io
```

The workflow runs the source guide build, browser checks, and legacy redirect checks before deploying with this repository's Pages permissions. Keep Actions enabled. Report product bugs and ideas in the product repository.
