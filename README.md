# Docker Tags Buildkite Plugin

A [Buildkite plugin](https://buildkite.com/docs/agent/v3/plugins) to tag and push containers.

Adds the following tags to container:

* Git branch e.g. `branch-feature-foo`
* Unique git branch for lifecycle management e.g. `branch-feature-foo-bb5f3223`
* Buildkite build number e.g. `build-199`
* Git commit e.g. `commit-d453423`

## Example

```yml
- label: ':docker: Package'
  command:
  - docker build -t foo .
  plugins:
    - healthforge/docker-tags:
        registries:
          - "${REPOSITORY_URI}"
        src: foo
        tags:
          - latest
```

## Options

### `registries`

Array of docker registry URLs.

### `tags`

Array of additional tags to push.

### `src`

Docker tag for build that you want to push (must be qualified).
