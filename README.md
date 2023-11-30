# latte

latte works with [Brew](https://docs.engineering.redhat.com/pages/viewpage.action?spaceKey=Brew&title=Using+Brew#UsingBrew-Overview) to make your devops life easier.

Find out the build, image, and commit-id of the containers included in the bundle build.

Ptp bundle builds can be found at the brew page:
https://brewweb.engineering.redhat.com/brew/packageinfo?packageID=73558

### Install
Make sure you have python 3 and koji or brew installed, then download the latte and run.
```
sudo dnf install python
sudo dnf install koji
```

### Usage
```
Usage: latte <nvr or build-id>
Example: latte ose-ptp-operator-metadata-container-v4.15.0.202311290506.p0.gefb34f0.assembly.stream-1
Example: latte 2799521
```

### Example
```
$ latte ose-ptp-operator-metadata-container-v4.15.0.202311290506.p0.gefb34f0.assembly.stream-1

found related build cloud-event-proxy-container-v4.15.0-202311290506.p0.g91c6d4b.assembly.stream
 image: ose-cloud-event-proxy-rhel9@sha256:4dab285cc785e70a5980dd49348fbeb43fbc5504dabe729379cc3594bded43a5
 commit: https://github.com/redhat-cne/cloud-event-proxy/commit/91c6d4b

found related build kube-rbac-proxy-container-v4.15.0-202311290506.p0.ge8e8c84.assembly.stream
 image: ose-kube-rbac-proxy@sha256:ac4305e1830e71178ec601f6a50cb60b0b0f9c6ca6f2ccc660a05c6b6d284c98
 commit: https://github.com/openshift/kube-rbac-proxy/commit/e8e8c84

found related build ose-ptp-operator-container-v4.15.0-202311290506.p0.gefb34f0.assembly.stream
 image: ose-ptp-rhel9-operator@sha256:93698428961ba101db95789b30c54a10e7a2d3014f4591ca93ddb66c56eb6af3
 commit: https://github.com/openshift/ptp-operator/commit/efb34f0

found related build ose-linuxptp-daemon-container-v4.15.0-202311290506.p0.g2d3c843.assembly.stream
 image: ose-ptp-rhel9@sha256:b2991d2898727a085890d6f9acbdc1e1df442066f5e78b6bfa0a91b7586c7b46
 commit: https://github.com/openshift/linuxptp-daemon/commit/2d3c843

$ latte 2799521

found related build cloud-event-proxy-container-v4.15.0-202311290506.p0.g91c6d4b.assembly.stream
 image: ose-cloud-event-proxy-rhel9@sha256:4dab285cc785e70a5980dd49348fbeb43fbc5504dabe729379cc3594bded43a5
 commit: https://github.com/redhat-cne/cloud-event-proxy/commit/91c6d4b

found related build kube-rbac-proxy-container-v4.15.0-202311290506.p0.ge8e8c84.assembly.stream
 image: ose-kube-rbac-proxy@sha256:ac4305e1830e71178ec601f6a50cb60b0b0f9c6ca6f2ccc660a05c6b6d284c98
 commit: https://github.com/openshift/kube-rbac-proxy/commit/e8e8c84

found related build ose-ptp-operator-container-v4.15.0-202311290506.p0.gefb34f0.assembly.stream
 image: ose-ptp-rhel9-operator@sha256:93698428961ba101db95789b30c54a10e7a2d3014f4591ca93ddb66c56eb6af3
 commit: https://github.com/openshift/ptp-operator/commit/efb34f0

found related build ose-linuxptp-daemon-container-v4.15.0-202311290506.p0.g2d3c843.assembly.stream
 image: ose-ptp-rhel9@sha256:b2991d2898727a085890d6f9acbdc1e1df442066f5e78b6bfa0a91b7586c7b46
 commit: https://github.com/openshift/linuxptp-daemon/commit/2d3c843

```