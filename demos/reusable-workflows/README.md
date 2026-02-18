# Reusable Workflows Demos

This directory contains demos for GitHub Actions reusable workflows feature.

## Demo 3: Simple Reusable Workflow

**Files**:
- `.github/workflows/reusable-simple.yml` (called workflow)
- `.github/workflows/demo-reusable-caller-simple.yml` (caller workflow)

Demonstrates basic reusable workflow:
- Defining a workflow with `workflow_call` trigger
- Calling a reusable workflow with `uses`
- Basic job execution in reusable workflow

**Key Concepts**:
- `on.workflow_call` trigger
- `uses: ./.github/workflows/reusable-simple.yml` syntax
- Workflow reusability within same repository

## Demo 4: Advanced Reusable Workflow

**Files**:
- `.github/workflows/reusable-advanced.yml` (called workflow)
- `.github/workflows/demo-reusable-caller-advanced.yml` (caller workflow)

Demonstrates advanced reusable workflow features:
- Defining inputs with types and defaults
- Defining outputs from jobs
- Passing secrets to reusable workflows
- Multiple calls to same workflow with different parameters
- Using outputs from reusable workflows

**Key Concepts**:
- Workflow inputs (string, boolean, number types)
- Workflow outputs
- Secrets passing
- Workflow composition
- Output consumption in caller workflow

## Running the Demos

Both demos can be triggered:
1. **Manually**: Go to Actions tab → Select caller workflow → Run workflow
2. **Automatically**: Push changes to files in `demos/reusable-workflows/` directory

## Best Practices

- Define clear input and output contracts
- Document required vs optional inputs
- Use semantic versioning for reusable workflows
- Keep workflows focused on single responsibility
- Can call workflows from other repositories with proper permissions
- Reusable workflows can be nested up to 4 levels deep
