# tomodo describe

Describe a single deployment or all deployments

## Usage

```shell
tomodo describe --name my-deployment --output json
```

## Options and Flags

**`--name`**

- **Description:** A specific deployment name;  will describe all deployments if not provided.
- **Type:** String
- **Required:** No
- **Example:**

    ```shell
    tomodo describe --name my-mongodb-deployment
    ```

**`--exclude-stopped`**

- **Description:** Exclude stopped deployments
- **Type:** Boolean
- **Required:** No (default: `--no-exclude-stopped`)
- **Example:**

    ```shell
    tomodo describe --exclude-stopped
    ```

**`--output`**

- **Description:** The format of the output printed to stdout.
- **Type:** String, Enum: `["json", "table", "yaml"]`
- **Required:** No (default: `"table"`)
- **Example:**

    ```shell
    tomodo describe --output json
    ```
