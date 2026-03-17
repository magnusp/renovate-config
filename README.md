# renovate-config

Shared [Renovate](https://docs.renovatebot.com/) configuration presets covering the **npm** and **maven** ecosystems.

## Available Presets

### `default`

The main preset that extends both the `npm` and `maven` presets along with Renovate's recommended base config and semantic commits.

**Usage:**

```json
{
  "extends": ["github>magnusp/renovate-config"]
}
```

### `npm`

Preset with rules specific to the npm ecosystem:

- Automerges patch and minor updates for `devDependencies`
- Groups related packages (eslint, jest, typescript) into single PRs
- Sets `rangeStrategy` to `bump`
- Adds `dependencies` and `npm` labels to PRs

**Usage:**

```json
{
  "extends": ["github>magnusp/renovate-config:npm"]
}
```

### `maven`

Preset with rules specific to the maven ecosystem:

- Groups Spring Boot dependencies into a single PR
- Groups Spring Framework dependencies into a single PR
- Automerges patch updates for test-scope dependencies
- Adds `dependencies` and `maven` labels to PRs

**Usage:**

```json
{
  "extends": ["github>magnusp/renovate-config:maven"]
}
```

## Using Multiple Presets

You can compose presets as needed:

```json
{
  "extends": [
    "github>magnusp/renovate-config:npm",
    "github>magnusp/renovate-config:maven"
  ]
}
```
