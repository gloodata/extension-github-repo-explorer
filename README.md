# Github Repo Explorer (Gloodata Extension)

A sample gloodata extension in python using glootil to explore a gituhub repository from a sqlite database

# Setup

First you need to generate the `githubrepo.db` file using the scripts in `tools/github-repo-to-sqlite`.

Feel free to change the exported repository, here we are going to export the [facebook/react](https://github.com/facebook/react) repo:

```sh
cd tools/github-repo-to-sqlite
# get your token here https://github.com/settings/tokens
export GIHUB_TOKEN="YOUR TOKEN HERE"
bun run dumpRepo.js facebook react react-issues.json react-releases.json
bun run issuesToSqlite.js react-issues.json react-releases.json ../../githubrepo.db
```

# Run

```sh
uv run src/main.py
```

Environment variables and their defaults:

- `EXTENSION_PORT`: `9876`
- `EXTENSION_HOST`: `localhost`
- `EXTENSION_DB_PATH`: `./githubrepo.db`

For example, to change the port:

```sh
EXTENSION_PORT=6677 uv run src/main.py
```
