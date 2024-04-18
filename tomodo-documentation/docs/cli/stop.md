# tomodo stop

Stop a single deployment or all deployments

## Usage

```shell
tomodo stop --name my-deployment
```

## Options and Flags

**`--name`**

- **Description:** A specific deployment name to stop;  will stop all deployments if not provided.
- **Type:** String
- **Required:** No
- **Example:**

    ```shell
    tomodo stop --name my-mongodb-deployment
    ```

**`--auto-confirm`**

- **Description:** Determines whether the confirmation prompt will be presented before execution
- **Type:** Boolean
- **Required:** No (default: `--no-auto-confirm`)
- **Example:**

    ```shell
    # Stop all deployments
    tomodo stop --auto-confirm
    # Stop a specific deployment by name
    tomodo stop --name my-mongodb-deployment --auto-confirm
    ```
