# tomodo ops-manager

Manage MongoDB Ops Manager deployments

## Subcommands

***

### tomodo ops-manager create

Provision an Ops Manager instance

#### Usage

```shell
tomodo ops-manager create
```

#### Options and Flags

**`--name`**

- **Description:** The deployment's name; auto-generated if not provided.
- **Type:** String
- **Required:** No
- **Example:**

    ```shell
    tomodo ops-manager create --name my-ops-manager
    ```

**`--port`**

- **Description:** The port that Ops Manager server should expose.
- **Type:** Integer
- **Required:** No (default: `8080`)
- **Example:**

    ```shell
    tomodo ops-manager create --port 8080
    ```

**`--app-db-port`**

- **Description:** The start port that App DB server should expose.
- **Type:** Integer
- **Required:** No (default: `20000`)
- **Example:**

    ```shell
    tomodo ops-manager create --app-db-port 27000
    ```

**`--replicate-app-db`**

- **Description:** Whether or not to use a 3-member replica set for Ops Manager's App DB.
- **Type:** Boolean
- **Required:** No (default: `--no-replicate-app-db`)
- **Example:**

    ```shell
    tomodo ops-manager create --replicate-app-db
    ```


***

### tomodo ops-manager add-server

Add one of more servers to Ops Manager. These servers can then be used in Ops Manager
to deploy MongoDB instances.

#### Usage

```shell
tomodo ops-manager add-server <OPS_MANAGER_NAME>
```

#### Options and Flags

**`--name`**

- **Description:** The nodes' name; auto-generated if not provided.
- **Type:** String
- **Required:** No
- **Example:**

    ```shell
    tomodo ops-manager add-server my-ops-manager --name mongonode
    ```

**`--port`**

- **Description:** The port range that the server should expose. If another container is already listening to any of the ports in the range, the action will fail.
- **Type:** Integer
- **Required:** No (default: `27017`)
- **Example:**

    ```shell
    tomodo ops-manager add-server my-ops-manager --port 27017
    ```

**`--count`**

- **Description:** The number of servers to provision.
- **Type:** Integer
- **Required:** No (default: `1`)
- **Example:**

    ```shell
    tomodo ops-manager add-server my-ops-manager --count 3
    ```

**`--project-id`**

- **Description:** The Ops Manager project ID.
- **Type:** String
- **Required:** Yes
- **Example:**

    ```shell
    tomodo ops-manager add-server my-ops-manager \
      --project-id 66d0b5864b2501271f521ad9 \
      --api-key 66d0b5984b2501271f521b1c4720cd6cc47e2d838639800ca0dd7e19
    ```

**`--api-key`**

- **Description:** The Ops Manager project ID.
- **Type:** String
- **Required:** Yes
- **Example:**

    ```shell
    tomodo ops-manager add-server my-ops-manager \
      --project-id 66d0b5864b2501271f521ad9 \
      --api-key 66d0b5984b2501271f521b1c4720cd6cc47e2d838639800ca0dd7e19
    ```
