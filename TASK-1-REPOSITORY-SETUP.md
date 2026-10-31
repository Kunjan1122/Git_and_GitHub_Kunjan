# Task 1: Repository Setup and First Branch

## Assessment details

| Item | Result |
|---|---|
| GitHub account | `Kunjan1122` |
| Repository | [Git_and_GitHub_Kunjan](https://github.com/Kunjan1122/Git_and_GitHub_Kunjan) |
| Visibility | Public |
| Default branch | `main` |
| Assessment branch | `Kunjan1122` |
| Commit | `9647705` — `Add Flask project` |
| Remote protocol | SSH |

## Work completed

1. Checked the GitHub account and found that the requested repository already existed and was empty. Reused it rather than creating a duplicate.
2. Confirmed that an SSH key was already available and that SSH authentication to GitHub succeeded. No new key needed to be generated or added.
3. Initialized the existing Flask project folder as a Git repository and connected its `origin` remote using the GitHub SSH URL. This reused the project already on the computer rather than cloning a second copy into another folder.
4. Created the `Kunjan1122` branch and committed the Flask project files.
5. Created `main` at the same commit, fast-forward merged the assessment branch, and pushed both branches to GitHub.
6. Verified that GitHub has both branches and that the local `main` branch tracks `origin/main`.

> **Cloning note:** The project was already in the local folder, so it was initialized and connected to GitHub over SSH instead of cloning into a second folder. SSH was used for both the remote URL and the push.

## Commands used

Run these commands from the Flask project folder. The following reflects the repository setup performed for this project:

```powershell
# Confirm the GitHub CLI account and SSH access
gh auth status
ssh -T git@github.com

# Initialize Git and configure the SSH remote
git init -b main
git remote add origin git@github.com:Kunjan1122/Git_and_GitHub_Kunjan.git

# Create the assessment branch and stage the project
git switch -c Kunjan1122
git add .
git status

# Save the project in a commit
git commit -m "Add Flask project"

# Create main from the committed project and merge the assessment branch
git switch -c main
git merge --ff-only Kunjan1122

# Publish both branches using the SSH remote
git push -u origin main Kunjan1122

# Verify the final state
git status --short --branch
git log --oneline --decorate --graph -3
git remote -v
```

SSH authentication was successful. GitHub displays a message that it does not provide shell access; that is expected for `ssh -T` and does not indicate a failed authentication.

## Project files committed

- `.gitignore`
- `app.py`
- `data.json`
- `requirements.txt`
- `templates/index.html`
- `templates/success.html`

## Verification

The GitHub repository was checked after pushing:

- `main` and `Kunjan1122` are present on GitHub.
- Both branches point to commit `9647705` (`Add Flask project`).
- `main` is the repository's default branch.
- The local working tree is clean and `main` tracks `origin/main`.

## Screenshot evidence

Capture the following evidence and save the image files in a folder named `screenshots` next to this document. The image links below will display the screenshots after you save the files with these names.

1. **GitHub repository and default branch:** Open the repository page and capture the repository name, visibility, and `main` branch.
   - Save as `screenshots/github-repository.png`.
   - ![GitHub repository](screenshots/github-repository.png)
2. **Branches on GitHub:** Open the repository's branches page and capture `main` and `Kunjan1122`.
   - Save as `screenshots/github-branches.png`.
   - ![GitHub branches](screenshots/github-branches.png)
3. **SSH authentication and Git remote:** In PowerShell, run `ssh -T git@github.com` and `git remote -v`, then capture the terminal output.
   - Save as `screenshots/ssh-and-remote.png`.
   - ![SSH authentication and remote](screenshots/ssh-and-remote.png)
4. **Commit and clean working tree:** In PowerShell, run `git status --short --branch` and `git log --oneline --decorate --graph -3`, then capture the terminal output.
   - Save as `screenshots/commit-and-status.png`.
   - ![Commit and working tree](screenshots/commit-and-status.png)

On Windows, use **Win+Shift+S** to capture each screen. Keep the terminal and browser screenshots readable, and do not include passwords, tokens, or private SSH key contents.
