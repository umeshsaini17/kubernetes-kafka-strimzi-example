## Installation

Installing k3d (Brew)

```cmd
brew install k3d
```

Creating a cluster

```cmd
k3d cluster create lunchlearn --agents 4 --servers 1
```

Add lunchlearn namespace

```cmd
kubectl create ns lunchlearn
```

Installing Strimzi operator (Installs operator & CRDs in given namespace)

```cmd
kubectl apply -f 'https://strimzi.io/install/latest?namespace=lunchlearn' -n lunchlearn
```

Adding Kafka Custom Resource

```cmd
kubectl apply -f kafka.yaml -n lunchlearn
```

Edit Kafka CLuster

```cmd
kubectl edit kafka my-cluster -n lunchlearn
```

Adding a topic

```cmd
kubectl apply -f kafka-topic.yaml -n lunchlearn
```

Creating a user

```cmd
kubectl apply -f kafka-user.yaml -n lunchlearn
```
