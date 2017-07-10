If you don't already have a docker hub account, you'll need one for this lab. Sign up here:

[https://hub.docker.com/](https://hub.docker.com/)

~/asb-oc.sh
```bash
#!/bin/bash
~/cleanup-oc.sh
curl https://bootstrap.pypa.io/get-pip.py | sudo python -
sudo pip install virtualenv
cd ~/ && virtualenv --clear --system-site-packages ansible
source ~/ansible/bin/activate
pip install -U docker ansible
git clone https://github.com/tchughesiv/catasb
cd catasb/local/linux/
git checkout aws-loft
./run_setup_local.sh
```
at prompt...

enter personal docker hub user/pass and use `ansibleplaybookbundle` for org.

To interact w/ new cluster via command line -
```bash
$ source ~/ansible/bin/activate
$ export PATH=~/bin:$PATH
$ oc version
oc v3.6.136
kubernetes v1.6.1+5115d708d7
features: Basic-Auth GSSAPI Kerberos SPNEGO

#$ oc login -u developer -p developer
#$ oc login -u admin -p admin
$ oc cluster status
Web console URL: https://ec2-xx.xx.xxx.xx.us-west-1.compute.amazonaws.com:8443
```

### ask student to login as developer & go through guided tour on right menu first...

### have them do hello-world apb deploy... view site landing page... then have them run postgres apb w/ bind to hello-world app.  redeploy hello-world & show same landing page w/ postgres connection showing.

### explore on their own ... maybe logout and back in as admin?