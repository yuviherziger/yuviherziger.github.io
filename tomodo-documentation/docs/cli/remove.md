# tomodo remove

Removes a single deployment or all deployments permanently.

## Usage

```shell
tomodo remove --name my-deployment
```

## Options and Flags

**`--name`**

- **Description:** A specific deployment name to remove;  will remove all deployments if not provided.
- **Type:** String
- **Required:** No
- **Example:**

    ```shell
    tomodo remove --name my-mongodb-deployment
    ```

**`--auto-confirm`**

- **Description:** Determines whether the confirmation prompt will be presented before execution
- **Type:** Boolean
- **Required:** No (default: `--no-auto-confirm`)
- **Example:**

    ```shell
    # Remove all deployments
    tomodo remove --auto-confirm
    # Remove a specific deployment by name
    tomodo remove --name my-mongodb-deployment --auto-confirm
    ```
