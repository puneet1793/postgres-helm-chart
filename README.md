a668977@vc2crtp1698098n:~/postgres-helm-chart$ vi ~/.kube/config
a668977@vc2crtp1698098n:~/postgres-helm-chart$ vi ~/.kube/config
a668977@vc2crtp1698098n:~/postgres-helm-chart$ helm install pg .
Error: INSTALLATION FAILED: Kubernetes cluster unreachable: exec plugin: invalid apiVersion "client.authentication.k8s.io/v1alpha1"
a668977@vc2crtp1698098n:~/postgres-helm-chart$ helm install pg .^C
a668977@vc2crtp1698098n:~/postgres-helm-chart$ cat ~/.kube/config | grep "client.authentication.k8s.io/v1alpha1
> ^C
a668977@vc2crtp1698098n:~/postgres-helm-chart$ cat ~/.kube/config | grep "client.authentication.k8s.io/v1alpha1"
      apiVersion: client.authentication.k8s.io/v1alpha1
      apiVersion: client.authentication.k8s.io/v1alpha1
      apiVersion: client.authentication.k8s.io/v1alpha1
a668977@vc2crtp1698098n:~/postgres-helm-chart$ cat ~/.kube/config | grep "client.authentication.k8s.io/v1beta1"
      apiVersion: client.authentication.k8s.io/v1beta1
a668977@vc2crtp1698098n:~/postgres-helm-chart$ sed -i "s/client.authentication.k8s.io\/v1alpha1/client.authentication.k8s.io\/v1beta1/g" ~/.kube/config
a668977@vc2crtp1698098n:~/postgres-helm-chart$ cat ~/.kube/config | grep "client.authentication.k8s.io/v1beta1"
      apiVersion: client.authentication.k8s.io/v1beta1
      apiVersion: client.authentication.k8s.io/v1beta1
      apiVersion: client.authentication.k8s.io/v1beta1
      apiVersion: client.authentication.k8s.io/v1beta1
a668977@vc2crtp1698098n:~/postgres-helm-chart$ helm install pg .
Error: INSTALLATION FAILED: Kubernetes cluster unreachable: Get "https://054C2B3A876D05461E8DFCB236D4CED7.gr7.us-east-2.eks.amazonaws.com/version": getting credentials: decoding stdout: no kind "ExecCredential" is registered for version "client.authentication.k8s.io/v1alpha1" in scheme "pkg/runtime/scheme.go:100"
a668977@vc2crtp1698098n:~/postgres-helm-chart$ cat ~/.kube/config | grep "client.authentication.k8s.io/v1beta1"
      apiVersion: client.authentication.k8s.io/v1beta1
      apiVersion: client.authentication.k8s.io/v1beta1
      apiVersion: client.authentication.k8s.io/v1beta1
      apiVersion: client.authentication.k8s.io/v1beta1
a668977@vc2crtp1698098n:~/postgres-helm-chart$





