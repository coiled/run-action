# Coiled Run GitHub Action

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

## Examples

### Run a command on a Coiled cluster

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

### Use a GPU VM to train a model with Python using [package sync](https://docs.coiled.io/user_guide/software/sync.html)

```yaml
  - name: Coiled Login
    uses: coiled/login-action@v1
    with:
      token: ${{ secrets.COILED_API_TOKEN }}
  - name: Coiled Run
    uses: coiled/run-action@v1
    with:
      command: "python train.py"
      vm-type: "g4dn.xlarge"
```

### Run a Python script that uses a [manual software environment](https://docs.coiled.io/user_guide/software/manual.html)

```yaml
  - name: Coiled Login
    uses: coiled/login-action@v1
    with:
      token: ${{ secrets.COILED_API_TOKEN }}
  - name: Coiled Run
    uses: coiled/run-action@v1
    with:
      command: "python my_script.py"
      software: "my-env"
```

### Run a command in a [Docker container](https://docs.coiled.io/user_guide/software/docker.html)

```yaml
  - name: Coiled Login
    uses: coiled/login-action@v1
    with:
      token: ${{ secrets.COILED_API_TOKEN }}
  - name: Coiled Run
    uses: coiled/run-action@v1
    with:
      command: "python rapids_script.py"
      container: "nvcr.io/nvidia/rapidsai/base:23.08-cuda11.8-py3.10"
```
