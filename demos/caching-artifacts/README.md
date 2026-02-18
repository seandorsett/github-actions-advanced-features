# Caching & Artifacts Demos

This directory contains demos for GitHub Actions caching and artifacts features.

## Demo 9: Simple Caching

**File**: `.github/workflows/demo-cache-simple.yml`

Demonstrates basic dependency caching:
- Caching npm dependencies
- Using cache keys with file hashes
- Cache hit/miss detection
- Restore keys for fallback caching

**Key Concepts**:
- `actions/cache@v3` action
- Cache key generation with `hashFiles()`
- Cache path configuration
- `restore-keys` for partial matches
- Cache status via `steps.cache.outputs.cache-hit`

## Demo 10: Advanced Caching & Artifacts

**File**: `.github/workflows/demo-cache-advanced.yml`

Demonstrates advanced caching and artifacts:
- Multi-level caching (dependencies + build output)
- Uploading build artifacts
- Downloading artifacts in downstream jobs
- Multi-stage deployment using artifacts
- Artifact retention policies
- Using same build across multiple jobs

**Key Concepts**:
- Multiple cache layers
- `actions/upload-artifact@v3` action
- `actions/download-artifact@v3` action
- Artifact retention days
- Sharing build outputs between jobs
- Build once, deploy many pattern

## Caching vs Artifacts

### Caching (actions/cache)
- **Purpose**: Speed up workflows by storing dependencies
- **Scope**: Shared across workflow runs (within same repository)
- **Lifetime**: 7 days of inactivity, or 10 GB limit per repository
- **Use for**: Dependencies (node_modules, pip packages, Maven dependencies)
- **Best for**: Data that doesn't change often

### Artifacts (actions/upload-artifact)
- **Purpose**: Share data between jobs and store build outputs
- **Scope**: Within a single workflow run
- **Lifetime**: 90 days default (configurable 1-90 days)
- **Use for**: Build outputs, test reports, logs
- **Best for**: Data specific to a workflow run

## Running the Demos

Both demos can be triggered:
1. **Manually**: Go to Actions tab → Select workflow → Run workflow
2. **Automatically**: Push changes to files in `demos/caching-artifacts/` directory

## Best Practices

### Caching
- Include dependency lock files in cache key (`hashFiles('**/package-lock.json')`)
- Use OS in cache key for multi-platform builds
- Use `restore-keys` for partial cache hits
- Keep cache size reasonable (large caches slow down restore)
- Cache early in workflow to benefit all jobs
- Monitor cache hit rates

### Artifacts
- Set appropriate retention periods (don't use 90 days if not needed)
- Use descriptive artifact names
- Upload only necessary files
- Clean up artifacts programmatically if needed
- Consider artifact size limits (500 MB per file, 2 GB per artifact)
- Download artifacts only when needed

## Example Cache Keys

```yaml
# Basic cache key with OS and lock file
key: ${{ runner.os }}-node-${{ hashFiles('**/package-lock.json') }}

# Cache key with Node version
key: ${{ runner.os }}-node-${{ matrix.node }}-${{ hashFiles('**/package-lock.json') }}

# Cache key with multiple lock files
key: ${{ runner.os }}-${{ hashFiles('**/package-lock.json', '**/yarn.lock') }}

# Cache key with branch name
key: ${{ runner.os }}-${{ github.ref_name }}-${{ hashFiles('**/package-lock.json') }}
```

## Common Patterns

### Build Once, Deploy Many
```yaml
jobs:
  build:
    - run: npm run build
    - uses: actions/upload-artifact@v3
      with:
        name: dist
        path: dist/
  
  deploy-staging:
    needs: build
    - uses: actions/download-artifact@v3
      with:
        name: dist
  
  deploy-production:
    needs: deploy-staging
    - uses: actions/download-artifact@v3
      with:
        name: dist
```

### Multi-level Caching
```yaml
- uses: actions/cache@v3
  with:
    path: node_modules
    key: deps-${{ hashFiles('package-lock.json') }}

- uses: actions/cache@v3
  with:
    path: dist
    key: build-${{ github.sha }}
```
