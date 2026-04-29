# platform-services
eval "$(ssh-agent -s)"
ssh-add -K /Users/mac/.ssh/id_rsa_techbeing
git push -u origin main --force
# argocd
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
# nexus
kubectl exec -it nexus-nexus-repository-manager-74f65d5978-q94n6 -n nexus -- /bin/bash
cat /nexus-data/admin.password

# grafana
kubectl -n monitoring get secret monitoring-grafana -o jsonpath="{.data.admin-password}" | base64 -d