# How to run the peribolos

The peribolos source code is located at https://github.com/kubernetes/test-infra/tree/master/prow/cmd/peribolos

The peribolos binary can be run in the official peribolos container image at [gcr.io/k8s-prow/peribolos](gcr.io/k8s-prow/peribolos)

### Peribolos workflow commands

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
# --confirm is required to for any command to commit the changes to the github organization
$ peribolos --github-token-path ${GITHUB_ACCESS_TOKEN_FILENAME} --config-path ${PERIBOLOS_GITHUB_ORG_CONFIG_FILE}  --fix-org --fix-org-members --fix-teams --fix-team-members --fix-team-repos --fix-repos --confirm
```
