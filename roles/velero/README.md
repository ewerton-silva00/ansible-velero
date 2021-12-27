Role Name
=========

velero

Requirements
------------

- An Kubernetes cluster up and running;
- Helm binary installed;

Role Variables
--------------

```
velero_kubeconfig_file_path: '/home/ewerton/.kube/kind.yaml'

# Whether to install helm3 binary or not.
velero_binary_install: false

# Velero version number.
velero_version: 1.7.1

# Namespace that will be created for velero deployment.
velero_namespace: velero

velero_storage_s3url: http://minio.minio.svc.cluster.local:9000

velero_aws_access_key: AKIAIOSFODNN7EXAMPLE

velero_aws_secret_key: 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

velero_bucket_name: velero

# Which namespaces will be backed up.
velero_backup_namespaces:
  - namespace:  dojot
    cron_expression: "0 */1 * * *"
    ttl: "24h"
  - namespace: dojot-monitoring
    cron_expression: "0 */1 * * *"
    ttl: "24h"

# Whether active the monitoring. Must have Prometheus Operator installed and working.
velero_prometheus_monitoring: true
```
> The values above are default.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
- hosts: localhost
  any_errors_fatal: true
  roles:
    - role: velero
      tags:
        - velero
```

License
-------

MIT

Author Information
------------------

Francisco Ewerton (DevOps Engineer)
