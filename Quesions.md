
1) Diffrence between volumes and volumeMounts in AKS

   **Volumes** - 
   Defined at the Pod level (under spec > volumes).
   It creates or references a volume that will be available to one or more containers in the Pod.

   **volumeMounts** -
   Defined within each container (under spec.containers[].volumeMounts).
   It tells the container where to mount the volume inside the container's filesystem.

2) What is the difference between PersistentVolume and PersistentVolumeClaim

  **PersistentVolume (PV)** A physical hard drive in a datacenter
    A cluster-level resource that represents actual physical storage.
    Created by admins or via StorageClass and dynamic provisioning.
    Can be backed by NFS, AWS EBS, GCE PD, Azure Disk, etc.
    
    It defines:
    Capacity
    Access Modes (ReadWriteOnce, ReadOnlyMany, etc.)
    Reclaim Policy (Retain, Delete, Recycle)
    Storage clas

  **PersistentVolumeClaim (PVC)** A request to use part of that hard drive
    A request for storage by a user or pod.    
    It specifies:
    How much storage is needed
    What access mode is required
