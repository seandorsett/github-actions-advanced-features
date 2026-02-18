# Environment Protection Rules Demos

This directory contains demos for GitHub Actions environment protection feature.

## Demo 7: Simple Environment

**File**: `.github/workflows/demo-environment-simple.yml`

Demonstrates basic environment usage:
- Deploying to a named environment (staging)
- Setting environment URL
- Basic deployment workflow

**Key Concepts**:
- `environment.name` configuration
- `environment.url` for deployment tracking
- Environment visibility in Actions UI

## Demo 8: Advanced Environment with Protection

**File**: `.github/workflows/demo-environment-advanced.yml`

Demonstrates advanced environment protection:
- Multiple environments (staging, production)
- Sequential deployment flow (build → staging → production)
- Production environment ready for protection rules
- Environment-specific URLs

**Key Concepts**:
- Multi-stage deployment
- Job dependencies with environments
- Environment protection rules (configured in repository settings)
- Deployment gates and approvals

## Setting Up Environment Protection

Environment protection rules are configured in repository Settings, not in workflow files:

1. Go to **Settings** → **Environments**
2. Click **New environment** or select existing environment
3. Configure protection rules:
   - **Required reviewers**: Select up to 6 reviewers who must approve
   - **Wait timer**: Set delay before deployment (0-43,200 minutes)
   - **Deployment branches**: Restrict which branches can deploy
   - **Environment secrets**: Add environment-specific secrets

## Running the Demos

Both demos can be triggered:
1. **Manually**: Go to Actions tab → Select workflow → Run workflow
2. **Automatically**: Push changes to files in `demos/environment-protection/` directory

## Best Practices

- Always use environments for production deployments
- Set up required reviewers for production
- Use deployment branches to restrict deployments to main/release branches
- Use environment-specific secrets
- Consider wait timers for time-based controls
- Use environment URLs to track deployments
- Review deployment history in Environments page

## Typical Setup

### Staging Environment
- No required reviewers (automatic deployment)
- Accessible from feature branches
- Used for testing before production

### Production Environment
- Required reviewers (1-2 senior developers)
- Only main/release branches can deploy
- Wait timer for off-hours deployments (optional)
- Strict environment secrets

## Benefits

- Human oversight for critical deployments
- Audit trail of who approved deployments
- Compliance with change management policies
- Prevents accidental production deployments
- Branch-based deployment controls
