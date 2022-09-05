
name: Latest blog post workflow
on:
  schedule: # Run workflow automatically
    - cron: '0 0 * * *' # Runs every day at 12 am
  workflow_dispatch: # Run workflow manually (without waiting for the cron to be called), through the Github Actions Workflow page directly
jobs:
  update-readme-with-blog:
    name: Update this repo's README with latest blog posts
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: gautamkrishnar/blog-post-workflow@master
        with:
          feed_list: "https://medium.com/feed/@56faisal"
