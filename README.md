# Redis Helm Chart

[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](https://github.com/Scalified/helm-redis/blob/master/LICENSE)
[![Release](https://img.shields.io/github/v/release/Scalified/helm-redis?style=flat-square)](https://github.com/Scalified/helm-redis/releases/latest)
[![Artifact Hub](https://img.shields.io/endpoint?url=https://artifacthub.io/badge/repository/scalified-redis)](https://artifacthub.io/packages/helm/scalified-redis/redis)

## Requirements

* [Helm 3+](https://helm.sh)

## Installation

```bash
helm repo add scalified-redis https://scalified.github.io/helm-redis/
helm upgrade --install redis scalified-redis/redis --create-namespace --namespace redis
```

## Usage

### Configuration

Configuration files can be mounted as follows:

```yaml
redis:
  containers:
    redis:
      volumeMounts:
        - name: redis-custom-config
          mountPath: /usr/local/etc/redis/conf.d/02-custom.conf
          subPath: 02-custom.conf
  volumes:
    - name: redis-custom-config
      configMap:
        name: redis-custom-config
```

---

**Made with ❤️ by [Scalified](http://www.scalified.com)**
