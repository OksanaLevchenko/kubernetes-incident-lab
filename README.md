# Kubernetes Incident Lab

This project is a hands on troubleshooting lab for common Kubernetes failure scenarios. I use it to reproduce problems, inspect what Kubernetes is reporting, and work through the recovery path instead of only reading about the error.

## Scenarios

### ImagePullBackOff

A pod cannot start because Kubernetes cannot pull the container image.

Typical causes include:

* invalid image names
* missing or incorrect image pull secrets
* private registry authentication problems

The useful part of this scenario is learning to inspect pod events and separate an image problem from an application problem.

### CrashLoopBackOff

A container starts, fails, and Kubernetes keeps restarting it.

This scenario is useful for practicing:

* pod and container status inspection
* logs from the current and previous container
* configuration and startup failures
* readiness and liveness related issues

### Pods not schedulable

A pod remains pending because the scheduler cannot place it on a node.

The lab covers common scheduling controls such as:

* node selectors
* node affinity
* taints
* tolerations

## Why I keep this lab

Kubernetes troubleshooting is easier when I can reproduce a failure and follow the evidence from pod status, events, logs, scheduling rules, and node conditions. I use this repository as a practical incident sandbox for that workflow.

## Next improvements

I plan to add more scenarios around resource pressure, probes, networking, DNS, storage, and autoscaling so the repository becomes a broader production troubleshooting lab.
