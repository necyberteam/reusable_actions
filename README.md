# Reusable github actions used on [cyberteam_drupal](https://github.com/necyberteam/cyberteam_drupal)

## behat.yml

This will action will:

- Install Lando
- Start Lando
- Install the current website and load the database and files
- Run the behat tests against the site specified upstream
- Send screenshots if there are any failures

This action requires the following secrets to be sent by the upstream action:
- **slack_token**: API token for slack
- **site**: Site to run tests on
- **database**: Database to pull in, normally blank
- **prnum**: Pull request number
- **gh_token**: A github token
- **LANDO_ENV**: Lando environment variables
- **SLACK_WEBHOOK**: Slack webhook to communicate with api
- **REPO**: Get current repo for gh cli command to comment on PR

This action is called for each site in a seprate job. This allows necyberteam to call the same action easily for each site instead of repeating all of the code in one action.
