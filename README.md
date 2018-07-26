# Luzifer / reg-clean

Cleanup S3 based Docker registry v2:

- Delete all non-tagged manifests
- Garbage-collection can remove the blobs

## Usage

```bash
## Build container (optional)
$ docker build -t quay.io/luzifer/reg-clean .

## Define AWS credentials
$ cat env
AWS_ACCESS_KEY_ID=myaccesskey
AWS_SECRET_ACCESS_KEY=mysecretaccesskey
AWS_DEFAULT_REGION=eu-west-1

AUTH=gitlabuser:gitlab-access-token
BUCKET=example-docker-registry
REGISTRY=https://registry.gitlab.example.com
GITLAB=https://gitlab.example.com

## Execute script
$ docker run --rm -ti --env-file=env tiennt/gitlab-reg-clean

## Run garbage collector
$ gitlab-ctl registry-garbage-collect
```
