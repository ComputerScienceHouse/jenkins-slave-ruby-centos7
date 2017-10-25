# Ruby Jenkins Slave

This repository contains a Dockerfile for a Jenkins Slave image intended for use with OpenShift Origin.

The image is pushed to DockerHub as computersciencehouse/jenkins-slave-ruby-centos7.

For more information about using this image with OpenShift, please see the official [OpenShift Documentation](https://docs.openshift.org/latest/using_images/other_images/jenkins.html#using-the-jenkins-kubernetes-plug-in-to-run-jobs).

## Usage

To use this slave in your Pipeline build, import the image into your project:

```
oc import-image computersciencehouse/jenkins-slave-ruby-centos7:latest --confirm
oc label is/jenkins-slave-ruby-centos7 role=jenkins-slave
```

Then, specify the image as the node type in your `Jenkinsfile`:

```
node('jenkins-slave-ruby-centos7') {
    [...]
}
```
