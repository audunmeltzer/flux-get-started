fluxctl identity --k8s-fwd-ns flux

fluxctl sync --k8s-fwd-ns flux

kubectl -n demo port-forward deployment/podinfo 9898:9898


fluxctl install \
--git-user=${GHUSER} \
--git-email=${GHUSER}@users.noreply.github.com \
--git-url=git@github.com:${GHUSER}/flux-get-started \
--git-path=namespaces,workloads \
--git-label=flux-sync \
--namespace=flux | kubectl apply -f -