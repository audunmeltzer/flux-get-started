fluxctl identity --k8s-fwd-ns flux

fluxctl sync --k8s-fwd-ns flux

kubectl -n demo port-forward deployment/podinfo 9898:9898