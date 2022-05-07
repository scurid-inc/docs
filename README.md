[![ci](https://github.com/scurid-inc/docs/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/scurid-inc/docs/actions/workflows/ci.yml)

# Readme

Contains documentation for Scurid platform

## To Deploy

* Make note of whether you are deploying for major or minor release.
* Scurid projects uses calVer versioning scheme

Deploy

```shell
mike deploy --push --update-aliases <release number> latest
```

example :
```shell
mike deploy --push --update-aliases v22.0.0-alpha.2 latest
```

Default doc version setup

```shell
mike set-default --push latest
```

## Generating docs from Proto

```shell
docker run --rm \
  -v $(pwd)/examples/doc:/out \
  -v $(pwd)/proto:/protos \
  pseudomuto/protoc-gen-doc --doc_opt=markdown,docs.md
```
