docs-pcf-install
==========

Installation docs for Ops Manager and VMware Tanzu Application Service for VMs.

**Note:** If you see PRs made against the `backup-restore` directory, move the corresponding Tracker story
to the PCF Docs Services tracker and notify the Services Docs PM.

## Which book repos publish this repo?

Currently only the [docs-book-pivotalcf](https://github.com/pivotal-cf/docs-partials) repo publishes this repo.

## Which branch to use?

**Note**: Provide instructions in your PRs to indicate which branches you want Docs to apply your commits to.

| Branch name | Use for… | |
|-------------| ---------|-|
| master      | Not used | |
| 3.0         | v3.0.x   | https://docs.vmware.com/en/VMware-Tanzu-Operations-Manager/3.0/vmware-tanzu-ops-manager/index.html |
| 2.10        | v2.10.x  | https://docs.vmware.com/en/VMware-Tanzu-Operations-Manager/2.10/vmware-tanzu-ops-manager/index.html |


## Partials

Cross-product and repo partials are single sourced from the [docs-partials](https://github.com/pivotal-cf/docs-partials) repo.

## Style Guide

See [Word and Phrase List](https://docs.google.com/spreadsheets/d/1hkadtxR1hY57kK7h5HN4ITHLJleZixCDH_RJPUpNq_A/edit#gid=0).

## Steps for local development
```
$ git clone git@github.com:pivotal-cf/docs-layout-repo
$ git clone git@github.com:pivotal-cf/docs-pcf-install
$ cd docs-pcf-install && git checkout <branch> && cd -
$ git clone git@github.com:pivotal-cf/docs-book-pivotalcf
$ cd docs-book-pivotalcf && git checkout <branch>
$ bundle install
$ bundle exec bookbinder watch
$ open http://127.0.0.1:XXXX/platform/<version, such as `2-10`>/customizing
```
