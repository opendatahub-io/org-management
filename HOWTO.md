* Initial seed of the GitHub origanization
```bash
$ peribolos --dump-full --dump ${GITHUB_ORGANIZATION} --github-token-path ${GITHUB_ACCESS_TOKEN_FILENAME} | tee ${PERIBOLOS_GITHUB_ORG_CONFIG_FILE}
```

* Dry run to see what would change if you synchronized the organization to the yaml file
```bash
$ peribolos --github-token-path ${GITHUB_ACCESS_TOKEN_FILENAME} --config-path ${PERIBOLOS_GITHUB_ORG_CONFIG_FILE}
```

* Run peribolos AND commit the changes to GitHub

```bash
$ peribolos --github-token-path ${GITHUB_ACCESS_TOKEN_FILENAME} --config-path ${PERIBOLOS_GITHUB_ORG_CONFIG_FILE}  --fix-org --fix-org-members --fix-teams --fix-team-members --fix-team-repos --fix-repos --confirm
```
