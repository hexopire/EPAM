name: Generate README

on:
  push:
    branches: [main] # Or your main branch name

jobs:
  generate-readme:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Generate README
        uses: eli64s/readme-ai@v1 # Use the latest version
        with:
          output_path: "." # Output to the root directory
      - name: Commit changes
        uses: stefanzweifel/git-auto-commit-action@v4
        with:
          commit_message: "Updated README.md"
