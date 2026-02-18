# Matrix Builds Demos

This directory contains demos for GitHub Actions matrix builds feature.

## Demo 1: Simple Matrix Build

**File**: `.github/workflows/demo-matrix-simple.yml`

Demonstrates basic matrix build functionality:
- Tests across 3 operating systems (Ubuntu, Windows, macOS)
- Tests with 3 Node.js versions (16, 18, 20)
- Creates 9 jobs automatically (3 × 3 combinations)

**Key Concepts**:
- `strategy.matrix` configuration
- Using `${{ matrix.os }}` and `${{ matrix.node }}` in workflow
- Parallel execution of all matrix jobs

## Demo 2: Advanced Matrix Build

**File**: `.github/workflows/demo-matrix-advanced.yml`

Demonstrates advanced matrix features:
- Using `exclude` to remove specific combinations
- Using `include` to add special configurations
- Using `fail-fast: false` to continue all jobs even if one fails
- Using `max-parallel` to limit concurrent jobs
- Using `continue-on-error` for experimental builds

**Key Concepts**:
- Matrix exclusions (e.g., Windows + Node 16)
- Matrix inclusions (e.g., experimental builds with extra features)
- Job failure handling strategies
- Cost control with max-parallel

## Running the Demos

Both demos can be triggered:
1. **Manually**: Go to Actions tab → Select workflow → Run workflow
2. **Automatically**: Push changes to files in `demos/matrix-builds/` directory

## Best Practices

- Use matrix builds for cross-platform testing
- Use `fail-fast: false` for comprehensive CI testing
- Use `max-parallel` to control costs with large matrices
- Add descriptive job names with matrix variables
- Use `include` to add edge cases without full matrix expansion
