# Composite Actions Demos

This directory contains demos for GitHub Actions composite actions feature.

## Demo 5: Simple Composite Action

**Files**:
- `.github/actions/setup-node-simple/action.yml` (action definition)
- `.github/workflows/demo-composite-simple.yml` (workflow using the action)

Demonstrates basic composite action:
- Bundling multiple steps into reusable action
- Using `composite` action type
- Calling other actions within composite action
- Shell script execution in composite actions

**Key Concepts**:
- `runs.using: 'composite'` configuration
- Required `shell` parameter for run steps
- Action reusability
- Local action usage with `uses: ./.github/actions/action-name`

## Demo 6: Advanced Composite Action

**Files**:
- `.github/actions/setup-node-advanced/action.yml` (action definition)
- `.github/workflows/demo-composite-advanced.yml` (workflow using the action)

Demonstrates advanced composite action features:
- Defining inputs with descriptions and defaults
- Defining outputs from composite actions
- Using inputs within action steps
- Returning values via outputs
- Caching within composite actions
- Step IDs for output passing

**Key Concepts**:
- Action inputs configuration
- Action outputs configuration
- Using `${{ inputs.input-name }}` in steps
- Using `${{ steps.step-id.outputs.output-name }}` for outputs
- Conditional step execution
- Complex logic encapsulation

## Running the Demos

Both demos can be triggered:
1. **Manually**: Go to Actions tab → Select workflow → Run workflow
2. **Automatically**: Push changes to files in `demos/composite-actions/` or `.github/actions/` directories

## Best Practices

- Keep actions focused and single-purpose
- Always specify `shell` in run steps
- Document inputs and outputs clearly
- Use meaningful input/output names
- Set sensible defaults for optional inputs
- Composite actions can call other actions
- Test actions thoroughly before publishing
- Consider creating public actions for common patterns

## Composite Actions vs Reusable Workflows

- **Composite Actions**: Groups of steps, called within a job
- **Reusable Workflows**: Complete workflows with jobs, called as a job
- Use composite actions for step-level reuse
- Use reusable workflows for job-level reuse
