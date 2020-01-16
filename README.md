# kustomization
## Base
Basically contain the resources that will be re-used/ override by the different environments (overlays) and a kustomization.yaml file which describe the resources we have in each kustomization(directory).

A kustomization is called base if it's referred by another kustomization and thus, Overlays (described in the next section) being referred by other kustomization are also base.



## Overlays
The way we override the base resources, typically we have different overlays for different environments: prod, dev, staging... Details shall be discussed in the next Usage section.

An overlay is a kustomization that depends on another kustomization, in our structure, dev and prod overlays depend on the base kustomization.

## Install
Since v1.14 the kustomize build system has been included in kubectl. Before v1.14, we have to install kustomize separately. 

To use kubectl v1.14 we need k8s cluster version to be → 1.13

kubectl is supported within one minor version (older or newer) of kube-apiserver.

Example:

kube-apiserver is at 1.13
kubectl is supported at 1.14, 1.13, and 1.12


For Mac user, simply run 
```console
brew install kustomize
```
## Build
```
kubectl getkustomize build . | kubectl apply -f -
```
