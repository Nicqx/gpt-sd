kubectl -n lan-sd delete deploy sd-proxy

kubectl -n lan-sd get pods -w

kubectl get namespaces

kubectl apply -f 00-namespace.yaml

kubectl apply -f 01-pvc-workspace.yaml

# template -> átnevezed és kitöltöd:

kubectl apply -f 02-basic-auth.secret.yaml

kubectl apply -f 03-nginx-configmap.yaml

kubectl apply -f 04-sd-webui.yaml

kubectl apply -f 05-sd-proxy.yaml

# jelszó csere:
kubectl -n lan-sd rollout restart deploy/sd-proxy

kubectl -n lan-sd rollout status deploy/sd-proxy

http://localhost:9988/
