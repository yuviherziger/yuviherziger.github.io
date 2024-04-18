# tomodo list

List deployments.

## Options and Flags

**`--exclude-stopped`**

- **Description:** Exclude stopped deployments
- **Type:** Boolean
- **Required:** No (default: `--no-exclude-stopped`)
- **Example:**

    ```shell
    tomodo list --exclude-stopped
    ```

**`--output`**

- **Description:** The format of the output printed to stdout.
- **Type:** String, Enum: `["json", "table", "yaml"]`
- **Required:** No (default: `"table"`)
- **Example:**

    ```shell
    tomodo list --output json
    ```
