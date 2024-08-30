# Usage Examples

## Create a sharded cluster

```shell
# Overriding some of the default values
tomodo provision sharded \
  --replicas 3 \
  --shards 4 \
  --mongos 3 \
  --config-servers 3
```

## Create an Atlas deployment

```shell
tomodo provision atlas \
  --username admin \
  --password supersecret
```

## Create an Ops Manager deployment and add servers

Run the following command:

```shell
tomodo ops-manager create --name my-mms
```

Log into your Ops Manager deployment via [http://localhost:80/account/register](http://localhost:80/account/register),
create your first Ops Manager user, and then go ahead and create an Agent API key
(see [instructions](https://www.mongodb.com/docs/ops-manager/current/tutorial/manage-agent-api-key/)).

Keep your project ID and agent API key, then create as many empty deployment servers as you like. For example:

```shell
tomodo ops-manager add-server my-mms --count 3 \
  --project-id <PROJECT_ID> \
  --api-key <AGENT_API_KEY>
```

Take note of the ports displayed in the logs of the command above.  These are the ports you can use in your
deployment.
