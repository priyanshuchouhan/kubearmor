# KubeArmor Zero Trust Policy for Wisecow

## Overview

As part of the optional security enhancement task, a Zero Trust security policy was created for the Wisecow Kubernetes workload using KubeArmor.

## Objective

The goal of this policy is to restrict unauthorized process execution inside the Wisecow container and demonstrate runtime security enforcement.

## Policy Details

The policy blocks execution of the following shells inside the container:

* /usr/bin/bash
* /bin/sh

This follows the Zero Trust principle where only explicitly allowed actions are permitted.

## Files Included

* kubearmor-policy.yaml
* kubearmor-violation-screenshot.png (if available)

## Deployment Environment

* Kubernetes: Minikube
* Workload: Wisecow Application
* Security Tool: KubeArmor

## Policy YAML

The KubeArmor policy is available in:

```text
kubearmor-policy.yaml
```

## Expected Behaviour

When a user attempts to execute a blocked shell inside the Wisecow pod, KubeArmor generates a policy violation event and prevents the action.

Example:

```bash
kubectl exec -it <wisecow-pod> -- /usr/bin/bash
```

## Status

* KubeArmor Operator Installed
* Zero Trust Policy Created
* Policy YAML Added to Repository
* Security Validation Attempted
