# tomodo provision

Provision a MongoDB deployment.

```shell
tomodo provision --help
```

## Subcommands

***

### tomodo provision standalone

Provision a standalone MongoDB deployment

#### Usage

```shell
tomodo provision standalone
```

#### Options and Flags

**`--port`**

- **Description:** The deployment's start port
- **Type:** Integer, between 0 and 65535
- **Required:** No (default: `27017`)
- **Example:**

    ```shell
    tomodo provision standalone --port 27111
    ```

**`--image-repo`**

- **Description:** The MongoDB image name/repo (NOTE: you probably don't want to change it)
- **Type:** String
- **Required:** No (default: `mongo`)
- **Example:**

    ```shell
    tomodo provision standalone --image-repo "mongo"
    ```

**`--image-tag`**

- **Description:** The MongoDB image tag, which determines the MongoDB version to install
- **Type:** String
- **Required:** No (default: `latest`)
- **Example:**

    ```shell
    tomodo provision standalone --image-tag "7.0.7"
    ```

**`--name`**

- **Description:** The deployment's name; auto-generated if not provided
- **Type:** String
- **Required:** No (default: generated randomly)
- **Example:**

    ```shell
    tomodo provision standalone --name "mymongodb"
    ```

**`--ephemeral`**

- **Description:** Whether the deployment should be ephemeral and not persist data. 
- **Type:** Flag
- **Required:** No (default: `--no-ephemeral`)
- **Example:**

    ```shell
    tomodo provision standalone --ephemeral
    ```


**`--network-name`**

- **Description:** The Docker network to provision the deployment in; will create a new one or use an
    existing one with the same name if such network exists
- **Type:** String
- **Required:** No (default: `mongo_network`)
- **Example:**

    ```shell
    tomodo provision standalone --network-name "my-docker-net"
    ```

**`--username`**

- **Description:** Admin username; no authentication if not provided
- **Type:** String
- **Required:** No (default: `null`)
- **Example:**

    ```shell
    tomodo provision standalone --username "foo" --password "bar"
    ```

**`--password`**

- **Description:** Admin password; no authentication if not provided
- **Type:** String
- **Required:** No (default: `null`)
- **Example:**

    ```shell
    tomodo provision standalone --username "foo" --password "bar"
    ```

***

### tomodo provision replica-set

Provision a MongoDB replica set deployment

#### Usage

```shell
tomodo provision replica-set
```

#### Options and Flags

**`--port`**

- **Description:** The deployment's start port
- **Type:** Integer, between 0 and 65535
- **Required:** No (default: `27017`)
- **Example:**

    ```shell
    tomodo provision replica-set --port 27111
    ```

**`--image-repo`**

- **Description:** The MongoDB image name/repo (NOTE: you probably don't want to change it)
- **Type:** String
- **Required:** No (default: `mongo`)
- **Example:**

    ```shell
    tomodo provision replica-set --image-repo "mongo"
    ```

**`--image-tag`**

- **Description:** The MongoDB image tag, which determines the MongoDB version to install
- **Type:** String
- **Required:** No (default: `latest`)
- **Example:**

    ```shell
    tomodo provision replica-set --image-tag "7.0.7"
    ```

**`--name`**

- **Description:** The deployment's name; auto-generated if not provided
- **Type:** String
- **Required:** No (default: generated randomly)
- **Example:**

    ```shell
    tomodo provision replica-set --name "mymongodb"
    ```

**`--ephemeral`**

- **Description:** Whether the deployment should be ephemeral and not persist data. 
- **Type:** Flag
- **Required:** No (default: `--no-ephemeral`)
- **Example:**

    ```shell
    tomodo provision replica-set --ephemeral
    ```

**`--replicas`**

- **Description:** The number of replica set members to provision
- **Type:** Integer, Enum: `[1, 3, 5, 7]`
- **Required:** No (default: `3`)
- **Example:**

    ```shell
    tomodo provision replica-set --replicas 3
    ```

**`--arbiter`**

- **Description:** Add an arbiter node to the replica set
- **Type:** Flag
- **Required:** No (default: `--no-arbiter`)
- **Example:**

    ```shell
    tomodo provision replica-set --arbiter
    ```

**`--network-name`**

- **Description:** The Docker network to provision the deployment in; will create a new one or use an
    existing one with the same name if such network exists
- **Type:** String
- **Required:** No (default: `mongo_network`)
- **Example:**

    ```shell
    tomodo provision replica-set --network-name "my-docker-net"
    ```

**`--username`**

- **Description:** Admin username; no authentication if not provided
- **Type:** String
- **Required:** No (default: `null`)
- **Example:**

    ```shell
    tomodo provision replica-set --username "foo" --password "bar"
    ```

**`--password`**

- **Description:** Admin password; no authentication if not provided
- **Type:** String
- **Required:** No (default: `null`)
- **Example:**

    ```shell
    tomodo provision replica-set --username "foo" --password "bar"
    ```

***

### tomodo provision sharded

Provision a MongoDB sharded cluster

#### Usage

```shell
tomodo provision sharded
```

#### Options and Flags

**`--port`**

- **Description:** The deployment's start port
- **Type:** Integer, between 0 and 65535
- **Required:** No (default: `27017`)
- **Example:**

    ```shell
    tomodo provision sharded --port 27111
    ```

**`--image-repo`**

- **Description:** The MongoDB image name/repo (NOTE: you probably don't want to change it)
- **Type:** String
- **Required:** No (default: `mongo`)
- **Example:**

    ```shell
    tomodo provision sharded --image-repo "mongo"
    ```

**`--image-tag`**

- **Description:** The MongoDB image tag, which determines the MongoDB version to install
- **Type:** String
- **Required:** No (default: `latest`)
- **Example:**

    ```shell
    tomodo provision sharded --image-tag "7.0.7"
    ```

**`--name`**

- **Description:** The deployment's name; auto-generated if not provided
- **Type:** String
- **Required:** No (default: generated randomly)
- **Example:**

    ```shell
    tomodo provision sharded --name "mymongodb"
    ```

**`--ephemeral`**

- **Description:** Whether the deployment should be ephemeral and not persist data. 
- **Type:** Flag
- **Required:** No (default: `--no-ephemeral`)
- **Example:**

    ```shell
    tomodo provision sharded --ephemeral
    ```

**`--replicas`**

- **Description:** The number of replica set members to provision in each shard
- **Type:** Integer, Enum: `[1, 3, 5, 7]`
- **Required:** No (default: `3`)
- **Example:**

    ```shell
    tomodo provision sharded --replicas 3
    ```

**`--shards`**

- **Description:** The number of shards to provision
- **Type:** Integer
- **Required:** No (default: `2`)
- **Example:**

    ```shell
    tomodo provision sharded --shards 5
    ```

**`--mongos`**

- **Description:** The number of mongos routers
- **Type:** Integer
- **Required:** No (default: `1`)
- **Example:**

    ```shell
    tomodo provision sharded --mongos 2
    ```

**`--config-servers`**

- **Description:** The number of config server replica set members
- **Type:** Integer, Enum: `[1, 3, 5, 7]`
- **Required:** No (default: `1`)
- **Example:**

    ```shell
    tomodo provision sharded --config-servers 3
    ```

**`--arbiter`**

- **Description:** Add an arbiter node to each shard
- **Type:** Flag
- **Required:** No (default: `--no-arbiter`)
- **Example:**

    ```shell
    tomodo provision sharded --arbiter
    ```

**`--network-name`**

- **Description:** The Docker network to provision the deployment in; will create a new one or use an
    existing one with the same name if such network exists
- **Type:** String
- **Required:** No (default: `mongo_network`)
- **Example:**

    ```shell
    tomodo provision sharded --network-name "my-docker-net"
    ```

**`--username`**

- **Description:** Admin username; no authentication if not provided
- **Type:** String
- **Required:** No (default: `null`)
- **Example:**

    ```shell
    tomodo provision sharded --username "foo" --password "bar"
    ```

**`--password`**

- **Description:** Admin password; no authentication if not provided
- **Type:** String
- **Required:** No (default: `null`)
- **Example:**

    ```shell
    tomodo provision sharded --username "foo" --password "bar"
    ```

### tomodo provision atlas

Provision a local MongoDB Atlas deployment

#### Usage

```shell
tomodo provision atlas
```

#### Options and Flags

**`--port`**

- **Description:** The deployment's start port
- **Type:** Integer, between 0 and 65535
- **Required:** No (default: `27017`)
- **Example:**

    ```shell
    tomodo provision atlas --port 27111
    ```

**`--version`**

- **Description:** The MongoDB version to install
- **Type:** String, Enum: `["6.0", "7.0"]`
- **Required:** No (default: `ghcr.io/yuviherziger/tomodo`)
- **Example:**

    ```shell
    tomodo provision atlas --image-repo "ghcr.io/yuviherziger/tomodo"
    ```

**`--image-repo`**

- **Description:** The MongoDB Atlas image name/repo (note: you probably don't want to change it)
- **Type:** String
- **Required:** No (default: `ghcr.io/yuviherziger/tomodo`)
- **Example:**

    ```shell
    tomodo provision atlas --image-repo "ghcr.io/yuviherziger/tomodo"
    ```

**`--image-tag`**

- **Description:** The MongoDB Atlas image tag (note: you probably don't want to change it) 
- **Type:** String
- **Required:** No (default: `main`)
- **Example:**

    ```shell
    tomodo provision atlas --image-tag "main"
    ```

**`--name`**

- **Description:** The deployment's name; auto-generated if not provided
- **Type:** String
- **Required:** No (default: generated randomly)
- **Example:**

    ```shell
    tomodo provision atlas --name "mymongodb"
    ```

**`--network-name`**

- **Description:** The Docker network to provision the deployment in; will create a new one or use an
    existing one with the same name if such network exists
- **Type:** String
- **Required:** No (default: `mongo_network`)
- **Example:**

    ```shell
    tomodo provision atlas --network-name "my-docker-net"
    ```

**`--username`**

- **Description:** Admin username
- **Type:** String
- **Required:** No (default: `"admin"`)
- **Example:**

    ```shell
    tomodo provision atlas --username "foo" --password "bar"
    ```

**`--password`**

- **Description:** Admin password
- **Type:** String
- **Required:** No (default: `"admin"`)
- **Example:**

    ```shell
    tomodo provision standalone --username "foo" --password "bar"
    ```
