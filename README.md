# Remote Dependency Management

Centralized repository for managing Gradle dependencies remotely.

## Usage

Add to your `build.gradle`:

```gradle
import groovy.json.JsonSlurper

def remoteDeps = new JsonSlurper().parse(
    new URL('https://raw.githubusercontent.com/liqiyucn/dep/main/dependencies.json')
)

repositories {
    remoteDeps.repositories.each { /* configure */ }
}

dependencies {
    // Load from selected profile
}
```

## Profiles

- `minimal` - Core utilities and logging
- `standard` - Adds JSON processing
- `web` - Adds HTTP clients
