# GitHub Actions Advanced Features

A comprehensive presentation and demo repository for learning GitHub Actions advanced features.

## 🎯 Overview

This repository contains a 55-minute presentation (50 minutes content + 5 minutes Q&A) covering 5 advanced GitHub Actions features with 10 runnable, self-contained, realistic demos.

## 📊 Presentation

Open `presentation/index.html` in a web browser to view the full presentation with speaker notes.

## 📚 Topics Covered

### 1. Matrix Builds (10 minutes)
Parallelize your workflows across multiple versions, platforms, and configurations.

- **Demo 1 - Simple**: Basic matrix with 3 OS × 3 Node versions (9 jobs)
- **Demo 2 - Advanced**: Matrix with include/exclude, fail-fast, and max-parallel

[View Matrix Builds Demos](demos/matrix-builds/)

### 2. Reusable Workflows (10 minutes)
Apply the DRY principle to your workflows by creating reusable workflow components.

- **Demo 3 - Simple**: Basic reusable workflow with workflow_call
- **Demo 4 - Advanced**: Reusable workflow with inputs, outputs, and secrets

[View Reusable Workflows Demos](demos/reusable-workflows/)

### 3. Composite Actions (10 minutes)
Build custom actions by bundling multiple steps into reusable components.

- **Demo 5 - Simple**: Basic composite action for Node.js setup
- **Demo 6 - Advanced**: Composite action with inputs, outputs, and caching

[View Composite Actions Demos](demos/composite-actions/)

### 4. Environment Protection Rules (10 minutes)
Control deployments with approval gates, wait timers, and branch restrictions.

- **Demo 7 - Simple**: Basic environment deployment with URL tracking
- **Demo 8 - Advanced**: Multi-stage deployment with production protection

[View Environment Protection Demos](demos/environment-protection/)

### 5. Caching & Artifacts (10 minutes)
Speed up workflows with intelligent caching and artifact sharing between jobs.

- **Demo 9 - Simple**: Basic dependency caching with npm
- **Demo 10 - Advanced**: Multi-level caching with artifacts and multi-stage deployment

[View Caching & Artifacts Demos](demos/caching-artifacts/)

## 🚀 Running the Demos

All demos are fully runnable and can be triggered in two ways:

### Method 1: Manual Trigger
1. Navigate to the **Actions** tab in GitHub
2. Select the demo workflow you want to run
3. Click **Run workflow** button
4. Watch the demo execute in real-time

### Method 2: Automatic Trigger
1. Make changes to files in the respective demo directory
2. Push to the `main` branch
3. The corresponding workflow will trigger automatically

## 📁 Repository Structure

```
.
├── presentation/
│   └── index.html              # Main presentation file
├── demos/
│   ├── matrix-builds/          # Matrix build demos
│   ├── reusable-workflows/     # Reusable workflow demos
│   ├── composite-actions/      # Composite action demos
│   ├── environment-protection/ # Environment protection demos
│   └── caching-artifacts/      # Caching and artifacts demos
└── .github/
    ├── workflows/              # All demo workflows
    └── actions/                # Composite action definitions
```

## 🎓 Learning Path

If you're new to these features, we recommend following this order:

1. **Start with Matrix Builds** - Learn to parallelize your testing
2. **Move to Caching & Artifacts** - Speed up your workflows
3. **Learn Composite Actions** - Create reusable step groups
4. **Explore Reusable Workflows** - Create reusable job flows
5. **Master Environment Protection** - Secure your deployments

## 💡 Best Practices Summary

### Matrix Builds
- Use `fail-fast: false` for comprehensive CI testing
- Use `max-parallel` to control costs
- Use `include` for special configurations
- Use `exclude` to remove unsupported combinations

### Reusable Workflows
- Document inputs and outputs clearly
- Use semantic versioning
- Keep workflows focused on single responsibility
- Can be nested up to 4 levels deep

### Composite Actions
- Always specify `shell` in run steps
- Keep actions focused and single-purpose
- Set sensible defaults for inputs
- Test thoroughly before publishing

### Environment Protection
- Always use for production deployments
- Set up required reviewers for critical environments
- Use deployment branches to restrict access
- Use environment-specific secrets

### Caching & Artifacts
- Include lock files in cache keys
- Use `restore-keys` for fallback
- Set appropriate artifact retention periods
- Use artifacts to share data between jobs

## 🔗 Additional Resources

- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [Actions Marketplace](https://github.com/marketplace?type=actions)
- [GitHub Actions Community](https://github.community/c/code-to-cloud/github-actions)

## 📝 Presentation Timeline

- **00:00-02:00** - Introduction and Agenda
- **02:00-12:00** - Matrix Builds (2 min intro + 8 min demos)
- **12:00-22:00** - Reusable Workflows (2 min intro + 8 min demos)
- **22:00-32:00** - Composite Actions (2 min intro + 8 min demos)
- **32:00-42:00** - Environment Protection (2 min intro + 8 min demos)
- **42:00-52:00** - Caching & Artifacts (2 min intro + 8 min demos)
- **52:00-55:00** - Best Practices Summary
- **55:00-60:00** - Q&A (5 minutes)

## 🎬 Presenting Tips

1. **Before the presentation**: Run all demos once to ensure they work
2. **During demos**: Keep the Actions tab open in a separate browser tab
3. **Time management**: Use the built-in presenter notes in the HTML
4. **Interactive elements**: Encourage questions during demos
5. **Backup plan**: All workflow files are available if live demos fail

## 🤝 Contributing

This is a demo repository for educational purposes. Feel free to fork and adapt for your own presentations!

## 📄 License

MIT License - Feel free to use this material for your own presentations and training.
