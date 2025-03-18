# Including Private Repository Contributions in GitHub Statistics

This guide explains how to set up your GitHub profile to show contributions from private repositories in your GitHub statistics.

## Setup Process

### 1. Create a Personal Access Token (PAT)

1. Go to your GitHub Settings > [Developer Settings](https://github.com/settings/tokens) > Personal access tokens > Generate new token (classic)
2. Give it a descriptive name (e.g., "GitHub Stats")
3. Set the expiration as needed (recommend at least 90 days)
4. Select these scopes:
   - `repo` (Full control of private repositories)
   - `read:user` (Read all user profile data)
   - `user:email` (Access user email addresses)
   - `read:packages` (Optional, if you want to include package statistics)
5. Click "Generate token" and copy your token

### 2. Add the Token to Repository Secrets

1. Go to your profile repository (the one named `<your-username>/<your-username>`)
2. Navigate to Settings > Secrets and variables > Actions
3. Click "New repository secret"
4. Name: `GH_TOKEN`
5. Value: Paste your Personal Access Token
6. Click "Add secret"

### 3. Set Up WakaTime (For Coding Time Statistics)

1. Sign up for a [WakaTime](https://wakatime.com/) account
2. Install the WakaTime plugin in your preferred code editor(s)
3. Get your WakaTime API Key from your [WakaTime Settings](https://wakatime.com/settings/account)
4. Add it as another secret in your repository:
   - Name: `WAKATIME_API_KEY`
   - Value: Your WakaTime API Key

### 4. GitHub Actions Workflow

The GitHub Actions workflow is already set up in `.github/workflows/github-stats.yml`. It will automatically update your README with:

- Total contributions (including private)
- Weekly coding activity
- Languages used
- Editors used
- Coding time distribution

## Troubleshooting

- If statistics aren't showing up, check your Actions tab for any workflow errors
- Ensure your README has the proper comments for the WakaTime integration:
  ```md
  <!--START_SECTION:waka-->
  <!--END_SECTION:waka-->
  ```
- Make sure your PAT hasn't expired

## Additional Resources

- [GitHub README Stats](https://github.com/anuraghazra/github-readme-stats)
- [WakaTime README Stats](https://github.com/anmol098/waka-readme-stats)
- [GitHub Streak Stats](https://github.com/DenverCoder1/github-readme-streak-stats) 