# Tomodo GitHub Action

You can use tomodo in your GitHub actions to run MongoDB instances for your workflows and pipelines. One popular
usage of containerized databases is running unit tests in GitHub Actions.

Here is an example of how you can run an Atlas container in your GitHub Actions with tomodo; it uses a simplified
Node.js example to illustrate how the Atlas container's connection string is injected into an environment variable:

```yaml
name: Run unit test
on: [ push ]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Git checkout
        uses: actions/checkout@v4

      - name: Set up Node.js
        uses: actions/setup-node@v4
        with:
          node-version: 20

      - name: Start a MongoDB Atlas container
        id: tomodo
        uses: yuvalherziger/tomodo-github-action@v1
        with:
          type: "atlas"
          username: "unittest"
          password: "supersecret"

      - run: npm install

      # Use the tomodo step's output to grab the connection string - and you're done!
      - name: Run tests
        run: npm test
        env:
          MONGODB_URI: ${{ steps.tomodo.outputs.connection-string }}
```

You can check out the example in [this repository](https://github.com/yuvalherziger/tomodo-action-example) to see
how your unit tests can run against a local MongoDB Atlas instance.

## Action Input

The action accepts the following parameters:

| Name             | Description                                                      | Type                                                    | Default         |
|------------------|------------------------------------------------------------------|---------------------------------------------------------|-----------------|
| `name`           | The deployment's name                                            | String                                                  | auto-generated  |
| `instance-type`  | The MongoDB instance type                                        | One of: `atlas`, `standalone`, `replica-set`, `sharded` | `atlas`         |
| `username`       | Optional authentication username                                 | String                                                  | -               |
| `password`       | Optional authentication password                                 | String                                                  | -               |
| `port`           | MongoDB port (in a cluster, this is the first incrementing port) | Integer; Min: `0`, Max: `65535`                         | `27017`         |
| `image-tag`      | The MongoDB image tag (determines the MongoDB version)           | String                                                  | `latest`        |
| `replicas`       | The number of replica set nodes to provision                     | One of: `1`, `3`, `5` ,`7`                              | `3`             |
| `shards`         | The number of shards to provision (sharded cluster)              | Integer (positive)                                      | `2`             |
| `config-servers` | The number of config server replica set nodes (sharded cluster)  | One of: `1`, `3`, `5` ,`7`                              | `1`             |
| `mongos`         | The number of mongos routers (sharded cluster)                   | Integer (positive)                                      | `1`             |
| `network-name`   | The Docker network to provision the deployment in                | string                                                  | `mongo-network` |
