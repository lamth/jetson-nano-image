Instructions here:
```
sudo yum install git
 sudo apt install software-properties-common
 sudo apt-add-repository --yes --update ppa:ansible/ansible
 sudo apt install ansible

export JETSON_ROOTFS_DIR=/hom/mdt/jetson/rootfs
sudo -E ./create-rootfs.sh
cd ansible
sudo -E $(which ansible-playbook) jetson.yaml
export JETSON_BUILD_DIR=/home/mdt/jetson/build_dir
sudo -E ./create-image.sh
cat <<EOF> $JETSON_ROOTFS_DIR/etc/resolv.conf
nameserver 8.8.8.8
EOF

```
