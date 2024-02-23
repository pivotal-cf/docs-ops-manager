# Tanzu Operations Manager Documentation

This repository contains content for the Ops Manager documentation. We publish the Ops Manager documentation at
https://docs.vmware.com/en/VMware-Tanzu-Operations-Manager/index.html.

In this README:

- [Tanzu Operations Manager Documentation](#tanzu-operations-manager-documentation)
  - [How To Contribute](#how-to-contribute)
  - [ Versions and Branches](#-versions-and-branches)
  - [Publishing Docs (2.10 and later)](#publishing-docs-210-and-later)
    - [Prepare Markdown Files](#prepare-markdown-files)
    - [In DocWorks](#in-docworks)
    - [In Docsdash](#in-docsdash)
    - [Promoting to Pre-Prod and Prod](#promoting-to-pre-prod-and-prod)


## How To Contribute

Please help us improve the accuracy and completeness of the Ops Manager documentation by
contributing content, editing, or expertise.

A common way to contribute is to file a pull request through GitHub.

Every topic in the Ops Manager documentation has a corresponding file in this repository. To locate
the source file for a topic, navigate to the topic on the Ops Manager documentation site and click
"View the source for this page in GitHub" at the bottom of the topic.

[Bookbinder](https://github.com/pivotal-cf/bookbinder/) uses the contents of this repository and others as sources to assemble the documentation for Ops Manager.

## <a name='version-branch'></a> Versions and Branches

| **Branch** | **Status** | **Published URL** |
|------------|------------|-------------------|
|      `3.0` | Published  | https://docs.vmware.com/en/VMware-Tanzu-Operations-Manager/3.0/vmware-tanzu-ops-manager/index.html  |
|     `2.10` | Published  | https://docs.vmware.com/en/VMware-Tanzu-Operations-Manager/2.10/vmware-tanzu-ops-manager/index.html |
|      `2.9` | EOGS       | https://docs.vmware.com/en/VMware-Tanzu-Operations-Manager/2.9/vmware-tanzu-operations-manager-2-9.pdf |
|      `2.8` | EOGS       | https://docs.vmware.com/en/VMware-Tanzu-Operations-Manager/2.8/vmware-tanzu-operations-manager-2-8.pdf |
|      `2.7` | EOGS       | https://docs.vmware.com/en/VMware-Tanzu-Operations-Manager/2.7/vmware-tanzu-operations-manager-2-7.pdf |

**3.0**: The `3.0` branch is used to publish the v3.0 site. Create pull requests on `3.0` to contribute or
correct technical inaccuracies in the Ops Manager v3.0 documentation.

**2.10**: The `2.10` branch is used to publish the v2.10 site. Create pull requests on `2.10` to contribute or
correct technical inaccuracies in the Ops Manager v2.10 documentation.

## Publishing Docs (2.10 and later)

The 2.10 and later docs have been migrated to docs.vmware.com and are now published using the following tools:

- [docworks](https://docworks.vmware.com/) is the main tool for managing docs used by writers.
- [docsdash](https://docsdash.vmware.com/) is a deployment UI which manages the promotion from
staging to pre-prod to production. The process below describes how to upload our docs to staging,
replacing the publication with the same version.

### Prepare Markdown Files

This repo contains the following files:

- Markdown files live in this repo.
- The table of contents is now in this repo in the [toc.md](toc.md) file. Each page requires an entry in the TOC.
- Variables also live in this repo in the [template_variables.yml](template_variables.yml).

### In DocWorks

1. Run a build of the "VMware Tanzu Ops Manager" project to upload the docs to Docs Dash.
2. Review your changes on the staging site https://docs-staging.vmware.com/...

### In Docsdash

1. Wait about 1 minute for processing to complete after uploading.
2. Go to https://docsdash.vmware.com/deployment-stage.

### Promoting to Pre-Prod and Prod

**Prerequisite** Needs additional privileges - reach out to a manager on the docs team [#tanzu-docs](https://vmware.slack.com/archives/C055V2M0H) or ask a writer to do this step for you.

1. Go to Staging publications in docsdash  
  https://docsdash.vmware.com/deployment-stage

2. Select a publication (make sure it's the latest version)

3. Click "Deploy selected to Pre-Prod" and wait for the pop to turn green (refresh if necessary after about 10s)

4. Go to Pre-Prod list  
  https://docsdash.vmware.com/deployment-pre-prod

5. Select a publication

6. Click "Sign off for Release"

7. Wait for your username to show up in the "Signed off by" column

8. Select the publication again

9. Click "Deploy selected to Prod"
