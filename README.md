# docker-action

https://docs.github.com/en/actions/creating-actions/creating-a-composite-action

.github/workflows/main.yml

```yaml
on: [push]

jobs:
  hello_world_job:
    runs-on: ubuntu-latest
    name: A job to say hello
    steps:
      - uses: actions/checkout@v3
      - id: foo
        uses: 030/docker-action@v0.1.0
        with:
          who-to-greet: "Mona the Octocat"
      - run: echo random-number ${{ steps.foo.outputs.random-number }}
        shell: bash
```
