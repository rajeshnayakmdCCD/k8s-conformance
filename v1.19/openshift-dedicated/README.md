This conformance report is generated by the OpenShift CI infrastructure. The canonical source location for this test script is located at https://github.com/openshift/origin/blob/master/test/extended/conformance-k8s.sh

This file was generated by:

  Commit 8768214666804b99f738f6aef0190a82d220926c

To recreate these results

# Create an [OpenShift Dedicated cluster](https://docs.openshift.com/dedicated/4/getting_started/accessing-your-services.html)

* Log in to https://cloud.redhat.com/openshift
* Select *Create Cluster* -> *Red Hat OpenShift Dedicated*.
* Enter your *Cluster name*, number of *Compute nodes*, and select an *AWS Region*.
* Select your *Node Type*. The number and types of nodes available to you depend
upon your OpenShift Dedicated subscription.
* If you want to configure your networking IP ranges under *Advanced Options*, the
following are the default ranges available to use:
** Node CIDR: 10.0.0.0/16
** Service CIDR: 172.30.0.0/16
** Pod CIDR: 10.128.0.0/14
* Add your Identity provider by clicking the *Add OAuth Configuration* link.
** Add a user by clicking the *Users* tab, then *Add User*. Input the user's name, then click *Add*.
** In the *Overview* tab under the *Details* heading will have a *Status* indicator. This will indicate that your cluster is *Ready* for use.

# Accessing your cluster

To access your OpenShift Dedicated cluster:

* From https://cloud.redhat.com/openshift, click on the cluster you want to access.
* Click *Launch Console*.
* Retrieve a `.kubeconfig` file with administrator credentials on that cluster and set the environment variable KUBECONFIG

    export KUBECONFIG=PATH_TO_KUBECONFIG

** It is currently not possible for OpenShift Dedicated users to obtain the cluster-administrator level permissions required to run `test/extended/conformance-k8s.sh`.

* Clone the OpenShift source repository and change to that directory:

    git clone https://github.com/openshift/origin.git
    cd origin

* Place the `oc` binary for that cluster in your PATH
* Run the conformance test:

    test/extended/conformance-k8s.sh