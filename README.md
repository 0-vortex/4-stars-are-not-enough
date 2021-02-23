# octokit action schedule

[![Commitizen friendly](https://img.shields.io/badge/commitizen-friendly-brightgreen.svg)](http://commitizen.github.io/cz-cli/)

This is an efficient octokit action schedule demonstration meant to satisfy different scenarios like:
- serverless runner
- cron schedule
- ability to integrate many repositories
- resilient to high traffic

As mentioned in the [documentation](https://docs.github.com/en/actions/reference/events-that-trigger-workflows#schedule):

>  The shortest interval you can run scheduled workflows is once every 5 minutes.

If your requirement is for higher availability at low cost I suggest two solutions:
- a bare bones rewrite of the logic inside the stars action to bash, git and curl by 
leveraging a stripped container outside of github actions
- an edge [Cloudflare Workers](https://developers.cloudflare.com/workers/) instance with 
the rewrite of the repository context inside the stars action to 
[durable objects](https://developers.cloudflare.com/workers/learning/using-durable-objects)
