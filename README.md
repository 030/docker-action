# docker-action

A composite action has been created based on
[this](https://docs.github.com/en/actions/creating-actions/creating-a-composite-action) documentation.

Create a `.github/workflows/docker.yml` file:

```yaml
---
name: Docker
"on": push
jobs:
  docker:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: 030/docker-action@v0.2.0
        with:
          image: utrecht/dive:${{ github.sha }}
```
