# Docker Tags Buildkite Plugin

A [Buildkite plugin](https://buildkite.com/docs/agent/v3/plugins) to tag and push containers.

Adds the following tags to container:

* Git commit e.g. `d453423b225bb5f32234d17771e8ff74f888a7cc`
* Git branch e.g. `feature_foo`
* Git describe e.g. `v1.0.0-6-g2681315`
* Buildkite build number e.g. `199`

## Example

```yml
- label: ':docker: Package'
  command:
  - docker build -t ${REPOSITORY_URI}:${BUILDKITE_BUILD_ID} .
  plugins:
    healthforge/docker-tags:
      registry: "${REPOSITORY_URI}"
      tag: "${BUILDKITE_BUILD_ID}"
```

## Options

### `registry`

URL of docker registry.

### `tag`

Tag for build that you want to push.
