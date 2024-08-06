# Programmatic Usage

You can install tomodo in your Python (>=3.8) projects using `pip` or any other Python package manager, and use it
programmatically.

## Deploy a Standalone Instance

You can deploy a standalone MongoDB instance by using the `provision_standalone_instance()` function:

```python
from tomodo.common.models import Mongod
from tomodo.functional import provision_standalone_instance

deployment: Mongod = provision_standalone_instance(
    name="curious-zebra",
    port=27017,
    username="foo", password="bar",
    image_repo="mongo",
    image_tag="latest",
    network_name="mongo_network"
)
```

## Deploy a Replica Set

You can deploy a standalone MongoDB instance by using the `provision_replica_set()` function:

```python
from tomodo.common.models import ReplicaSet
from tomodo.functional import provision_replica_set

deployment: ReplicaSet = provision_replica_set(
    name="hungry-fly",
    replicas=3,
    arbiter=False,
    port=27017,
    username="foo", password="bar",
    image_repo="mongo",
    image_tag="latest",
    network_name="mongo_network"
)
```

## Deploy a Sharded Cluster

You can deploy a sharded cluster by using the `provision_sharded_cluster()` function:

```python
from tomodo.common.models import ShardedCluster
from tomodo.functional import provision_sharded_cluster

deployment: ShardedCluster = provision_sharded_cluster(
    name="lone-bobcat",
    replicas=3,
    shards=3,
    mongos=2,
    config_servers=3,
    arbiter=False,
    port=27017,
    username="foo", password="bar",
    image_repo="mongo",
    image_tag="latest",
    network_name="mongo_network"
)
```

## Deploy a Local Atlas Instance

You can deploy a local MongoDB Atlas instance by using the `provision_atlas_instance()` function:

```python
from tomodo.common.models import AtlasDeployment
from tomodo.functional import provision_atlas_instance

deployment: AtlasDeployment = provision_atlas_instance(
    name="dazzling-mosquito",
    port=27017,
    version="7.0",
    username="foo", password="bar",
    image_repo="ghcr.io/yuvalherziger/tomodo",
    image_tag="main",
    network_name="mongo_network"
)
```

## Find a Deployment by Name

Find a deployment by its name using the `get_deployment()` function:

```python
from tomodo.common.errors import DeploymentNotFound
from tomodo.functional import get_deployment

try:
    deployment = get_deployment(name="elegant-leopard", include_stopped=True)
except DeploymentNotFound:
    # Do something with the exception
    raise
```

## List Deployments

Find a deployment by its name using the `get_deployment()` function, which returns a dictionary of `Deployment`
instances keyed by their names:

```python
from typing import Dict

from tomodo.common.models import Deployment
from tomodo.functional import list_deployments

deployments: Dict = list_deployments(include_stopped=True)
for name in deployments.keys():
    deployment: Deployment = deployments[name]
    print(f"Deployment {name} is {deployment.last_known_state}")
```

## Stop a Deployment

You can stop a deployment using its `stop()` method:

```python
from tomodo.common.errors import DeploymentNotFound

try:
    deployment.stop()
except DeploymentNotFound as exc:
    # Do something with the exception
    raise
```

## Start a Stopped Deployment

You can restart a stopped a deployment using its `start()` method:

```python
from tomodo.common.errors import DeploymentNotFound

try:
    deployment.start()
except DeploymentNotFound as exc:
    # Do something with the exception
    raise
```

## Remove a Deployment

You permanently remove a deployment using its `remove()` method:

```python
from tomodo.common.errors import DeploymentNotFound

try:
    deployment.remove()
except DeploymentNotFound as exc:
    # Do something with the exception
    raise
```
