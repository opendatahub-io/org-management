# opendatahub-io GitHub organization

This repository contains the metadata [configuration](/config) for the opendatahub-io Github
Organizations. The data here is consumed by the
[peribolos](https://docs.prow.k8s.io/docs/components/cli-tools/peribolos/)
tool to organization and team membership, as well as team creation and deletion.

Membership in the opendatahub-io project is governed by our
[community guidelines](https://github.com/opendatahub-io/opendatahub-community/blob/main/community-membership.md).

NOTE: The opendatahub-io organization and team membership list will be managed by this repo only.  Any differences between the actual opendatahub-io organzation membership and the [org.yaml](config/opendatahub-io/org.yaml) may result in a loss of org or team membership settings with the peribolos command is executed 

The application for membership in the opendatahub-io organization can be made by opening an [issue](https://github.com/opendatahub-io/org-management/issues/new/choose).
However, if you are already part of the opendatahub-io organization, you do not need to do this and can add yourself directly to the appropriate files.
For example, to also add yourself to the opendatahub-io organization, you can navigate to `config/opendatahub-io/org.yaml` and add your GitHub username to the list of members (in alphabetical order)

Requirements

* Add only one new member per commit (if you add two members separate it in two commits
* Commit message format `Add <USERNAME> to <opendatahub-io, mlops-sig, ...> org`. 

* New GitHub team requests can only come from an existing opendatahub-io member who will function as the maintainer of the team. Each additional member will follow the same requirements for adding new members
* Commit message format `Create <TEAMNAME>`

## Community, discussion, contribution, and support

Learn how to engage with the opendatahub-io community on the
[community page](http://github.com/opendatahub-io/opendatahub-community/).

You can reach the maintainers of this project at:

- [#sig-platform](https://odh-io.slack.com/messages/sig-platform) on slack

To report any sensitive information, please email the private github@kubernetes.io list.

### Code of conduct

Participation in the Open Data Hub community is governed by the
[Open Data Hub Code of Conduct](https://github.com/opendatahub-io/opendatahub-community/blob/main/CODE_OF_CONDUCT.md).
