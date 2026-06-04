# Build Tool Cache Orb

Experimental orb to provide first-class remote cache integration with a selection of popular build tools.

## Supported Tools
- Bazel
- Gradle

## Usage

```yaml
version: 2.1
orbs:
  cache: https://raw.githubusercontent.com/circleci-petri/caching/refs/heads/main/orbs/build-tool-cache.yml
jobs:
  build:
    docker:
      - image: cimg/base:current
    steps:
      - cache/with_build_tool_cache:
          tool: gradle
          steps:
            - run: ./gradlew build
workflows:
  use-cache-orb:
    jobs:
      - build
```
