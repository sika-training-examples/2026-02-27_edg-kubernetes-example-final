# Setup

```bash
oc apply -f clusters/egd_ocp/_system/argocd/manifests/01_ns.yaml
oc apply -f clusters/egd_ocp/_system/argocd/manifests/02_operatorgroup.yaml
oc apply -f clusters/egd_ocp/_system/argocd/manifests/03_subscription.yaml
oc apply -f clusters/egd_ocp/_system/argocd/manifests/04_rbac.yaml
sleep 60
oc apply -f clusters/egd_ocp/_system/argocd/manifests/05_argocd_config.yaml
sleep 60
oc apply -f clusters/egd_ocp/_app_of_apps/
```
