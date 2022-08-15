[![ci](https://github.com/scurid-inc/docs/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/scurid-inc/docs/actions/workflows/ci.yml)

# Readme

Contains documentation for Scurid platform

### Important
* Scurid projects uses calVer versioning scheme
* Branch used for deployment is `gh-pages`

## To Deploy
* Make note of whether you are deploying for major or minor release, based on that adjust the version for deployment


### Before deploying

Since `mike` which we use for versioning our doc won't do it automatically. 
```shell
git fetch
```

Deploy

```shell
mike deploy --push --update-aliases <release number> latest
```

example :
Use rebase if there are git issues with remote branch
```shell
mike deploy --push --update-aliases v22.0.0-alpha.2 latest --rebase
```

Default doc version setup
```shell
mike set-default --push latest --rebase
```

## Generating docs from Proto

```shell
docker run --rm -v /Users/sushantpandey/go/src/bitbucket.org/scurid/scurid-apis/pkg/grpc/examples/doc:/out -v /Users/sushantpandey/go/src/bitbucket.org/scurid/scurid-apis/pkg/grpc/proto:/protos pseudomuto/protoc-gen-doc --doc_opt=markdown,docs.md
```
