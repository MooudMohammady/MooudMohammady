name: Daily Contributions

on:
  schedule:
    - cron: '0 0 * * 1-5'

jobs:
  make-contribution:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v2
        with:
          # Checkout with full commit history
          fetch-depth: 0
      - name: Make daily contribution
        run: |
          # Replace this command with your own command or script that makes the changes
          echo "Making daily contribution"
          echo "$(date)" >> README.md
      - name: Commit changes
        uses: EndBug/add-and-commit@v7
        with:
          author_name: "GitHub Actions"
          author_email: "actions@github.com"
          message: "Daily contribution"
          # Set the files to commit - replace this with your own file paths
          add: "README.md"
      - name: Push changes
        uses: ad-m/github-push-action@master
        with:
          branch: daily-contribution
          # Set the Git credentials - replace this with your own secrets
          github_token: ${{ secrets.GITHUB_TOKEN }}
      - name: Open pull request
        uses: peter-evans/create-pull-request@v3
        with:
          title: "Daily Contribution"
          commit-message: "Daily contribution"
          branch: daily-contribution
          base: main
          # Set the pull request body - replace this with your own content
          body: "This pull request was created automatically by a GitHub Actions workflow to make a daily contribution."
          # Set the Git credentials - replace this with your own secrets
          token: ${{ secrets.GITHUB_TOKEN }}
