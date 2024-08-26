# org-management

Configuration of organization membership and automation to apply this
membership via GitHub Actions automation.

## Making Changes to Organization Membership

Addition or removal of users to/from the organization should be made by editing
the [membership config][membership_config].

To add an individual to the organization, open a pull request adding the
individual's GitHub username to the membership config file. *Note* Please
add individuals in alphabetical order.

## Automation Setup

We use [Peribolos](https://docs.prow.k8s.io/docs/components/cli-tools/peribolos/) to manage
organization membership. The membership is defined in [config/organization_members.yaml][membership_config].
We then use a GitHub action, defined in [.github/workflows/apply-org-membership.yaml](.github/workflows/apply-org-membership.yaml)
to automatically apply the membership after any change to the membership config.

This automation depends on a GitHub personal access token with read and write
permissions to organization members. The token value is saved in this repository as a
repository secret with name `ORG_MANAGEMENT_TOKEN`.

## CI/CD

We use GitHub actions to automate the functionality of this repository. To validate
new changes to this repository, we have a workflow called [Verify Pull Requests](.github/workflows/verify-pull-requests.yaml).
For every pull request to this repository, this will:

  * Lint all YAML files
  * Check that the list of organization users is alphabetical
  * Ensure that there are no duplicate individuals
  * Ensure that changes to organization owners are not being made

When changes to the membership config file are merged to main, an additional workflow
called [Apply Organization Membership](.github/workflows/apply-org-membership.yaml) is run. This
workflow runs the Peribolos tool and reconciles the state of the org membership to
the contencts of the config file.

## Managing Organization Owners

We want to prevent changes to the org management file that result in the state of organization owners
changing. The Peribolos tool currently requires that you specify owners when running it. To get around this
limitation we've split the organizational config into an [admin config](config/organization_admins.yaml) and
a [members config][membership_config]. These two configs are merged at apply time
and the merged config file is passed to Peribolos.

[membership_config]: config/organization_members.yaml