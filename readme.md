# Installation

## Flux runtime

```sh
flux install
kubectl create -f bootstrap/source.yaml
kubectl create -f bootstrap/kustomization-full.yaml
kubectl create -f bootstrap/kustomization-playground.yaml
```

## sealed secrets

Install kubeseal

```sh
go install github.com/bitnami-labs/sealed-secrets/cmd/kubeseal@main
```

Fetch public key:

```sh
kubeseal --fetch-cert --controller-name=sealed-secrets --controller-namespace=sealed-secrets > pub-sealed-secrets.pem
```