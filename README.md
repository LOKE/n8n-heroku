# n8n-heroku

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://dashboard.heroku.com/new?template=https://github.com/LOKE/n8n-heroku/tree/main)

## n8n - Free and open fair-code licensed node based Workflow Automation Tool.

This is a [Heroku](https://heroku.com/)-focused container implementation of [n8n](https://n8n.io/).

Use the **Deploy to Heroku** button above to launch n8n on Heroku. When deploying, make sure to check all configuration options and adjust them to your needs. It's especially important to set `N8N_ENCRYPTION_KEY` to a random secure value. 

Refer to the [Heroku n8n tutorial](https://docs.n8n.io/deploy/host-n8n/install-options/use-a-cloud-provider/deploy-to-heroku) for more information.

If you have questions after trying the tutorials, check out the [forums](https://community.n8n.io/).

## Updating n8n

The n8n image is pinned in the [`Dockerfile`](Dockerfile) so deploys are reproducible. To upgrade, bump the tag to the current stable release and redeploy:

```dockerfile
FROM n8nio/n8n:2.35.7
```

Available tags are listed on [Docker Hub](https://hub.docker.com/r/n8nio/n8n/tags) — `stable` points at the latest release, `beta` at the next minor. Check the [release notes](https://docs.n8n.io/changelog/release-notes-2.x) for breaking changes before jumping several minor versions.

## Merging upstream changes

To merge changes from the upstream n8n repository, you can use the following commands:

```bash
git remote add upstream https://github.com/n8n-io/n8n-heroku.git
git fetch upstream
git merge upstream/main
git push origin main
```

## Pushing to Heroku

```bash
heroku git:remote -a loke-ops-n8n
git push heroku main
```

