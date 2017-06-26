# GlusterFS Cheatsheet

## Cluster management

**Add peer to cluster:**

```bash
gluster peer probe <ip>
```

**NOTE: new nodes must be always firstly probed from node which is already in the cluster,**

**Get cluster status:**

```bash
gluster peer status
```

## Volume management

**Create volume:**

```bash
gluster volume create <name> replica 2 <addr + path> <addr + path> [force]
gluster volume start <name>
```

**Replace brick:**

```bash
gluster volume replace-brick <name> <old addr + path> <new addr + path> commit force
gluster volume heal <name> full
```

**Add new brick to volume:**

```bash
gluster volume add-brick <name> replica 3 <new repliace addr + path>
```

**Stop volume:**

```bash
gluster volume stop <name>
```

**Delete volume:**

```bash
gluster volume delete <name>
```

**Reset volume:**

Clears all data and meta-data, usefull for broken bricks.

```bash
gluster volume reset <name>
```

## Troubleshooting cluster

Delete entire node config without UID file(s)!!!

```bash
systemctl stop glusterfs-server
cd /var/lib/glusterd
# manually remove files
systemctl stop glusterfs-start

# probe node from remote peer
systemctl restart glusterfs-server
```