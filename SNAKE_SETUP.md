# GitHub Contribution Snake Setup Guide

## ✅ What Was Installed

A GitHub Actions workflow that automatically generates an animated snake eating your GitHub contributions.

### Files Created:
- `.github/workflows/snake.yml` - GitHub Actions workflow configuration

---

## 🚀 How It Works

### Automatic Generation
The snake animation is generated automatically:
1. **Daily** - Every day at midnight (UTC)
2. **On Push** - Every time you push to the main branch
3. **Manual** - Can be triggered manually from GitHub Actions tab

### Output
The workflow creates two versions:
- **Light theme**: `github-contribution-grid-snake.svg`
- **Dark theme**: `github-contribution-grid-snake-dark.svg`

These files are saved to the `output` branch of your repository.

---

## 📋 How to Verify It's Working

### Step 1: Check GitHub Actions

1. Go to your repository: https://github.com/Trittton/Trittton
2. Click the **"Actions"** tab at the top
3. You should see a workflow called **"Generate Snake"**
4. Click on it to see the workflow runs

### Step 2: Trigger First Run (Manual)

Since you just added the workflow, trigger it manually:

1. Go to **Actions** tab
2. Click **"Generate Snake"** on the left sidebar
3. Click **"Run workflow"** button on the right
4. Click the green **"Run workflow"** button in the dropdown
5. Wait ~1 minute for it to complete (green checkmark = success)

### Step 3: Verify Output Branch

After the workflow runs successfully:

1. Go to your repository main page
2. Click the branch dropdown (shows "main")
3. You should see a new branch called **"output"**
4. Click on "output" branch
5. You should see two files:
   - `github-contribution-grid-snake.svg`
   - `github-contribution-grid-snake-dark.svg`

---

## 🎨 How to Use in README

The README.md file is already configured to show the snake! The relevant section is:

```markdown
<p align="center">
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Trittton/Trittton/output/github-contribution-grid-snake-dark.svg" />
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Trittton/Trittton/output/github-contribution-grid-snake.svg" />
  <img alt="github-snake" src="github-snake.svg" />
</picture>
</p>
```

This code automatically shows:
- **Dark snake** when viewing in dark mode
- **Light snake** when viewing in light mode

---

## 🔧 Workflow Configuration

### Current Schedule
```yaml
schedule:
  - cron: "0 0 * * *"  # Runs daily at midnight UTC
```

### Triggers
- ✅ Scheduled (daily)
- ✅ Manual dispatch (can trigger from Actions tab)
- ✅ On push to main branch

### Customization Options

If you want to change when it runs, edit `.github/workflows/snake.yml`:

```yaml
schedule:
  - cron: "0 */12 * * *"  # Every 12 hours
  - cron: "0 */6 * * *"   # Every 6 hours
  - cron: "0 0 * * 1"     # Every Monday at midnight
```

---

## ❌ Troubleshooting

### Workflow Fails with "Permission Denied"

**Solution**: Enable workflow permissions

1. Go to repository **Settings**
2. Click **Actions** → **General** (left sidebar)
3. Scroll to **Workflow permissions**
4. Select **"Read and write permissions"**
5. Check **"Allow GitHub Actions to create and approve pull requests"**
6. Click **Save**
7. Re-run the workflow

### Snake Not Showing on Profile

**Possible causes:**

1. **Workflow hasn't run yet**
   - Go to Actions tab and manually trigger it

2. **Output branch not created**
   - Check if "output" branch exists
   - Re-run the workflow

3. **README URLs incorrect**
   - Verify URLs point to: `https://raw.githubusercontent.com/Trittton/Trittton/output/...`
   - Make sure repository name is correct (case-sensitive)

4. **Browser cache**
   - Hard refresh the page (Ctrl+F5 or Cmd+Shift+R)
   - Try viewing in incognito/private mode

### Snake Animation Broken/Not Animating

- SVG files may take time to load
- Try viewing your profile in a different browser
- Check if the SVG files exist in the output branch
- Verify the files are not empty (should be ~50-100KB each)

---

## 📊 What the Snake Shows

The snake animation displays:
- **Green squares** = Your GitHub contributions
- **Snake path** = Animated snake eating the contributions
- **Animation** = Snake moves around the contribution graph

More contributions = more food for the snake! 🐍

---

## 🎯 Next Steps

1. ✅ **Trigger the workflow manually** (Actions tab → Run workflow)
2. ✅ **Wait ~1 minute** for it to complete
3. ✅ **Check output branch** (should see 2 SVG files)
4. ✅ **View your profile** (https://github.com/Trittton)
5. ✅ **See the snake!** (scroll to bottom of README)

---

## 📚 Additional Resources

- [Platane/snk](https://github.com/Platane/snk) - The snake generator action
- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [Cron Expression Generator](https://crontab.guru/) - Create custom schedules

---

## 🔄 Automatic Updates

The snake will automatically update:
- ✅ Every day at midnight
- ✅ Whenever you push to main branch
- ✅ You can also manually trigger it anytime

No maintenance required! 🎉
