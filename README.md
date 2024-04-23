Here's a compact guide to setting up a Telegram bot hosted on Heroku, using GitHub for version control, and deploying via automatic builds:

Replace 'mybot' with desired bot name if you want. Don't forget about mybot.py entry point file.

### Step 1: Register on Heroku and Create an App

-   Sign Up: Go to [Heroku](https://heroku.com/) and sign up for an account.
-   Create App: In the Heroku dashboard, click "New" -> "Create new app". Choose a name and region.

### Step 2: Set Up Your Repository on GitHub

-   Create a New Repository: If you don't already have a repo, create one on [GitHub](https://github.com/).
-   Clone this Repository: If you prefer to use an existing template, clone it into your GitHub account.

### Step 3: Obtain a Telegram Bot Token

-   BotFather: Message @BotFather on Telegram to create a new bot. Use the `/newbot` command and follow the instructions to get your bot token.

### Step 4: Configure Your Heroku App

-   Add Buildpacks:

    -   Go to your app's "Settings" tab in Heroku.
    -   Under "Buildpacks", click "Add buildpack".
    -   Add the Heroku CLI buildpack: `https://github.com/heroku/heroku-buildpack-cli`
    -   Add the Python buildpack by selecting it from the list or entering `heroku/python`.
-   Set Config Vars:

    -   Still in the "Settings" tab, find the "Config Vars" section and click "Reveal Config Vars".
    -   Add a new Config Var:
        -   Key: `TELEGRAM_BOT_TOKEN`
        -   Value: `<your-telegram-bot-token>`

### Step 5: Deploy Using GitHub

-   Connect Repository:

    -   Go to the "Deploy" tab in your Heroku app dashboard.
    -   Select "GitHub" as the deployment method.
    -   Connect your GitHub account if not already done.
    -   Search for your repository and connect to it.
    -   Choose the branch you want to deploy from (usually `main` or `master`).
-   Automatic Deploys:

    -   Enable automatic deploys for your chosen branch if you want updates to deploy automatically when you push to GitHub.

### Step 6: Ensure Your Worker Dyno is Running

-   Activate Worker:
    -   Navigate to the "Resources" tab.
    -   Look for the line that resembles your worker (e.g., `worker: python your_script.py`).
    -   If it's toggled off, click the pencil icon and toggle it to "on", then confirm by clicking "Confirm".

### Step 7: Perform the Initial Deployment and Monitor Logs

-   Manual Deployment:
    -   If you haven't enabled automatic deploys, you can trigger a manual deploy in the "Deploy" tab by clicking "Deploy Branch".
-   View Logs:
    -   Go to "More" (top-right corner) in your Heroku dashboard and select "View logs" to monitor the deployment and see your bot in action.

This guide should help you set up your Telegram bot on Heroku, making it easy to manage and deploy changes directly from your GitHub repository.
