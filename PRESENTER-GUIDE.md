# Quick Reference Guide for Presenters

## 📋 Pre-Presentation Checklist (5 min)

- [ ] Open `presentation/index.html` in browser (full screen F11)
- [ ] Open GitHub Actions tab in separate window
- [ ] Test internet connection
- [ ] Have backup: screenshots of working demos
- [ ] Run 1-2 key demos to verify they work

## ⏱️ Timing Breakdown (50 minutes content)

| Time | Topic | What to Show |
|------|-------|--------------|
| 0:00-0:02 | Intro | Title slide, introduce yourself |
| 0:02-0:04 | Agenda | Set expectations, timing |
| 0:04-0:06 | Matrix Intro | Explain concept |
| 0:06-0:09 | Matrix Simple | Show workflow, run/results |
| 0:09-0:12 | Matrix Advanced | Show include/exclude |
| 0:12-0:14 | Reusable Intro | Explain DRY principle |
| 0:14-0:17 | Reusable Simple | Show caller/called pattern |
| 0:17-0:22 | Reusable Advanced | Show inputs/outputs/secrets |
| 0:22-0:24 | Composite Intro | Actions vs workflows |
| 0:24-0:27 | Composite Simple | Show action.yml |
| 0:27-0:32 | Composite Advanced | Show inputs/outputs |
| 0:32-0:34 | Environment Intro | Explain protection rules |
| 0:34-0:37 | Environment Simple | Show basic deployment |
| 0:37-0:42 | Environment Advanced | Show multi-stage + settings |
| 0:42-0:44 | Caching Intro | Cache vs artifacts |
| 0:44-0:47 | Caching Simple | Show cache key/hit |
| 0:47-0:52 | Caching Advanced | Show artifacts workflow |
| 0:52-0:55 | Best Practices | Quick recap |
| 0:55-1:00 | Q&A | Answer questions |

## 🎯 Key Points to Emphasize

### Matrix Builds
- ⭐ Automatic job generation (3×3 = 9 jobs)
- ⭐ Parallel execution saves time
- ⭐ Include/exclude for flexibility

### Reusable Workflows
- ⭐ DRY principle for workflows
- ⭐ Can call across repositories
- ⭐ Inputs/outputs like functions

### Composite Actions  
- ⭐ Lower level than workflows
- ⭐ Bundle steps, not jobs
- ⭐ Must specify shell

### Environment Protection
- ⭐ Configured in Settings (show this!)
- ⭐ Manual approvals possible
- ⭐ Critical for production

### Caching & Artifacts
- ⭐ Cache: speed up builds (7 days)
- ⭐ Artifacts: share between jobs (90 days)
- ⭐ Different purposes, both important

## 💡 Demo Tips

### For Each Demo:
1. **Show the workflow file** - Point out key syntax
2. **Show the Actions tab** - Point out visualization
3. **Highlight results** - What actually happened
4. **Time check** - Stay on schedule

### Navigation:
- **Ctrl+Tab**: Switch between presentation and Actions tab
- **F11**: Full screen presentation
- **F5**: Refresh Actions tab to see updates

## 🚨 Troubleshooting

### If demo fails:
1. Stay calm - it happens
2. Explain what should have happened
3. Show the workflow code instead
4. Move to next demo
5. Come back if time permits

### Common issues:
- **Slow loading**: GitHub might be slow, have backup screenshots
- **Workflow queued**: Other workflows running, explain queuing
- **Unexpected failure**: Check logs, might be transient issue

## 🎤 Speaking Tips

### Opening:
"Today we'll explore 5 advanced GitHub Actions features that will make your CI/CD pipelines more powerful and maintainable. Each topic has simple and advanced demos - all runnable in this repository."

### Transitions:
- "Now that we've seen matrix builds, let's move to reusable workflows..."
- "Building on what we learned, let's look at..."
- "This next feature complements what we just saw..."

### Closing:
"These features work great together. You might have a reusable workflow that uses composite actions, matrix builds, caching, and deploys to protected environments. Start small and build up."

## 📝 Notes Section Usage

Each slide has yellow presenter notes. They include:
- What to say
- What to show
- How long to spend
- Common questions

Read these before presenting!

## ❓ Common Q&A Topics

**Q: How much do matrix builds cost?**
A: You pay for all job minutes. 3×3 matrix = 9 jobs. Use max-parallel to control concurrency.

**Q: Can reusable workflows call other reusable workflows?**
A: Yes! Up to 4 levels deep.

**Q: What's difference between composite actions and reusable workflows?**
A: Actions = steps (use within a job). Workflows = jobs (use as a job).

**Q: How many approvers can I have?**
A: Up to 6 required reviewers per environment.

**Q: What happens when cache is full?**
A: GitHub automatically evicts least recently used cache. 10 GB limit per repo.

## 🎓 Backup Information

If questions go deep, reference:
- Demo READMEs in each `demos/` directory
- Main README.md for overview
- GitHub Actions docs at docs.github.com/actions

## ✅ Success Indicators

You're doing well if:
- Audience is engaged and asking questions
- Demos are running successfully
- On time (check at 25 min mark)
- Energy is high
- Examples resonate with audience

## 🔄 Adaptive Presentation

**If running behind:**
- Skip some demo details
- Focus on one demo per topic
- Shorten best practices section

**If have extra time:**
- Dive deeper into logs
- Show Settings configurations
- Take more questions
- Show how features combine

**If audience is advanced:**
- Less explanation of basics
- More on advanced features
- More technical depth
- Show edge cases

**If audience is beginner:**
- More explanation of concepts
- Slower demo pace
- More context for each feature
- Relate to real-world scenarios

## 📱 Follow-up

End with:
"All these demos are in the repository - fork it, try them yourself, and adapt them to your needs. I'm available for questions after."

Good luck! 🎉
