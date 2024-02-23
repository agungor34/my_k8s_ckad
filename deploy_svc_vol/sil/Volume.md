# Example about Kubernetes Objects: storageclass, persistentvolume, persistentvolumeclaim

## The following examples are made here:
- Yaml file that creates persistentvolume containing 2 "hostpath" type storage classes.
- 1 yaml file that takes persistent volumeclaim from storageclass
- 1 yaml file that takes persistentvolumeclaim from persistentvolume of "hostpath" type
- 1 yaml file that creates a pod that takes volume from both "hostpath" type pvc and storageclass type pvc.