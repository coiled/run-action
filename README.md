cod# Coiled Run GitHub Action

This GitHub Action runs a command on a [Coiled](https://coiled.io) cluster by adding the following steps to your workflow. For more details see our [CLI job docs](https://docs.coiled.io/user_guide/cli-jobs.html).

```yaml
  - name: Coiled Login
    uses: coiled/login-action@v1
    with:
      token: ${{ secrets.COILED_API_TOKEN }}
  - name: Coiled Run
    uses: coiled/run-action@v1
    with:
      command: "echo 'Hello, Coiled!'"
```
