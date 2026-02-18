# Testing Guide

This guide helps you test all demos before presenting.

## Pre-Presentation Checklist

### 1. Test Workflows (15 minutes before presentation)

Run each workflow manually to ensure they work:

```bash
# Navigate to Actions tab in GitHub
# For each workflow:
# 1. Click on the workflow name
# 2. Click "Run workflow" button
# 3. Select branch (usually 'main')
# 4. Click "Run workflow" to execute
# 5. Wait for completion (usually 1-3 minutes)
# 6. Verify success (green checkmark)
```

### 2. Workflow Testing Order

Test in this order to build confidence:

1. ✅ **Demo 1: Matrix Builds - Simple** (quick, should complete in ~2 min)
2. ✅ **Demo 2: Matrix Builds - Advanced** (slightly longer)
3. ✅ **Demo 3: Reusable Workflows - Simple** (very quick)
4. ✅ **Demo 4: Reusable Workflows - Advanced** (quick)
5. ✅ **Demo 5: Composite Actions - Simple** (quick)
6. ✅ **Demo 6: Composite Actions - Advanced** (quick)
7. ✅ **Demo 7: Environment Protection - Simple** (quick)
8. ✅ **Demo 8: Environment Protection - Advanced** (quick)
9. ✅ **Demo 9: Caching - Simple** (quick, creates cache)
10. ✅ **Demo 10: Caching & Artifacts - Advanced** (demonstrates artifacts)

### 3. What to Verify

For each workflow run:
- ✓ Workflow triggers successfully
- ✓ All jobs complete (green checkmarks)
- ✓ No error messages in logs
- ✓ Expected outputs are visible
- ✓ Matrix jobs show correct expansion (for matrix demos)
- ✓ Artifacts are created (for artifact demos)
- ✓ Cache is utilized (for caching demos - run twice to see cache hit)

### 4. Common Issues and Fixes

**Issue: Workflow doesn't trigger**
- Solution: Check the `on:` trigger configuration
- Ensure `workflow_dispatch` is present for manual triggering

**Issue: Matrix jobs fail**
- Solution: Check that all matrix combinations are valid
- Review excluded/included configurations

**Issue: Reusable workflow not found**
- Solution: Verify path to reusable workflow is correct
- Ensure reusable workflow has `workflow_call` trigger

**Issue: Composite action not found**
- Solution: Check action.yml file exists in correct directory
- Verify `uses: ./.github/actions/action-name` path is correct

**Issue: Cache not working**
- Solution: Run workflow twice - first run creates cache, second uses it
- Check cache key includes hash of lock file

**Issue: Artifacts not visible**
- Solution: Ensure `actions/upload-artifact@v3` step completes
- Check artifact name matches in download step

## During Presentation Testing

### Quick Smoke Test (5 minutes)

If time is limited, test these key workflows:

1. **Demo 1: Matrix Simple** - Shows parallel execution
2. **Demo 4: Reusable Advanced** - Shows inputs/outputs
3. **Demo 10: Caching Advanced** - Shows artifacts

These three cover the most complex features and if they work, others likely will too.

### Live Demo Tips

1. **Have workflows pre-run**: Don't wait for completion during presentation
2. **Keep Actions tab open**: Switch to it when showing demos
3. **Highlight key features**: 
   - Matrix visualization
   - Reusable workflow calls in the graph
   - Artifact downloads
   - Cache hit logs
4. **Have backup screenshots**: In case live demos fail

## Automated Testing (Optional)

You can trigger all demos at once by pushing to the repository:

```bash
# Create a test file that triggers all workflows
mkdir -p demos/matrix-builds demos/reusable-workflows demos/composite-actions demos/environment-protection demos/caching-artifacts

# Add test files
echo "Test trigger" > demos/matrix-builds/test.txt
echo "Test trigger" > demos/reusable-workflows/test.txt
echo "Test trigger" > demos/composite-actions/test.txt
echo "Test trigger" > demos/environment-protection/test.txt
echo "Test trigger" > demos/caching-artifacts/test.txt

# Commit and push
git add demos/
git commit -m "Test: Trigger all demos"
git push

# Check Actions tab - all workflows should trigger
```

## Post-Presentation

After the presentation, verify:
- All demos still work (in case of GitHub Actions updates)
- No failed workflow runs visible in Actions tab
- Artifacts and cache entries are reasonable size

## Environment Setup (One-time)

Some demos reference environments. While demos work without configuration, for the full experience:

1. Go to Settings → Environments
2. Create two environments:
   - **staging** (no protection rules)
   - **production** (add protection rules):
     - Required reviewers: Add yourself or team members
     - Wait timer: 0 minutes (for demo purposes)
     - Deployment branches: Selected branches → main

This shows how protection rules pause workflow execution until approval.

## Troubleshooting Commands

```bash
# Check workflow syntax locally (requires act or similar)
# Not required but useful for development

# List all workflows
find .github/workflows -name "*.yml"

# Validate YAML syntax
for file in .github/workflows/*.yml; do
  echo "Checking $file"
  python3 -c "import yaml; yaml.safe_load(open('$file'))" && echo "✓ Valid" || echo "✗ Invalid"
done

# Check for common issues
grep -n "uses: actions/" .github/workflows/*.yml | grep -v "@v3\|@v4"  # Check action versions
```

## Success Criteria

Before presenting, ensure:
- [ ] All 10 workflows run successfully
- [ ] No red X's in Actions tab
- [ ] Presentation HTML opens correctly
- [ ] All demo README files are clear
- [ ] Main README is comprehensive
- [ ] You understand the flow of each demo
- [ ] You can explain the key concepts
- [ ] You have timing down for each section

## Time Estimates

- Full test of all workflows: ~15 minutes
- Quick smoke test: ~5 minutes
- Reviewing workflow logs: ~10 minutes
- **Total preparation time**: ~30 minutes

Good luck with your presentation! 🚀
