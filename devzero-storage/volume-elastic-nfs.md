---
title: Volume (elastic NFS)
---
# Volume (elastic NFS)

DevZero's volumes are multi-attach multi-read-write capable volumes (similar to AWS EFS).
Volumes are regional in nature and can be attached to any workspace in that region.

## Creating a volume

### In your default region

{% code %}
```
$ dz storage volume create --name=my-fancy-volume --size=50
ID                                       Name             Total size (GB)  Region         
volume-7947b1c8881c49fbb5c7c3e0367a76f2  my-fancy-volume  50               Portland, USA  
```
{% endcode %}

### In an arbitrary region

{% code %}
```
$ dz storage volume create --name=other-fancy-volume --size=50 --region=eu-north-1
ID                                       Name                        Total size (GB)  Region         
volume-e71e024eba0a443ab452c931e8ce39a5  other-fancy-volume          50               Stockholm, Sweden  
```
{% endcode %}

## Listing your volumes

{% code %}
```
$ dz storage volume list
ID                                       Name                        Total size (GB)  Region             
volume-7947b1c8881c49fbb5c7c3e0367a76f2  my-fancy-volume             50               Portland, USA      
volume-e71e024eba0a443ab452c931e8ce39a5  other-fancy-volume          50               Stockholm, Sweden  
```
{% endcode %}

## Launching a workspace with a volume

The volume is mounted at the path specified by the `--mount` flag.

{% code %}
```
$ dz workspace launch "My Recipe Name" --region=us-west-2 --mount /mnt/my-shared-volume=volume-7947b1c8881c49fbb5c7c3e0367a76f2
Your workspace is currently being built... please wait!
🚀 workspace launch: success
Successfully deployed workspace dear-filly-ubhg
To connect to this workspace, run:
dz workspace connect dear-filly-ubhg

# OR

$ dz workspace launch "My Recipe Name" --region=eu-north-1 --mount /mnt/my-shared-volume=volume-e71e024eba0a443ab452c931e8ce39a5
Your workspace is currently being built... please wait!
🚀 workspace launch: success
Successfully deployed workspace abominal-monkey-ytui
To connect to this workspace, run:
dz workspace connect abominal-monkey-ytui
```
{% endcode %}

### Verifying mounted volumes inside a workspace

{% code %}
```
$ dz workspace connect dear-filly-ubhg
....
....

dear-filly-ubhg $ ls /mnt
my-shared-volume

dear-filly-ubhg $ df -a
Filesystem      K-blocks     Used Available Use% Mounted on
/dev/nvme6n1    51290592    16500  51257708   1% /home/devzero
[some path..]   10485760        0  10485760   0% /mnt/my-shared-volume
```
{% endcode %}

## Resizing a volume

To change the size of a volume, you can run:
{% code %}
```
$ dz storage volume edit volume-7947b1c8881c49fbb5c7c3e0367a76f2 --size 100
ID                                       Name                        Total size (GB)  Region            
volume-7947b1c8881c49fbb5c7c3e0367a76f2  my-fancy-volume             100              Portland, USA      
```
{% endcode %}