# Ops Manager Documentation

This repository contains content for the Ops Manager documentation. We publish the Ops Manager documentation at
https://docs.pivotal.io/ops-manager/index.html.

## How To Contribute

Please help us improve the accuracy and completeness of the Ops Manager documentation by
contributing content, editing, or expertise.

A common way to contribute is to file a pull request through GitHub.

Every topic in the Ops Manager documentation has a corresponding file in this repository. To locate
the source file for a topic, navigate to the topic on the Ops Manager documentation site and click
"View the source for this page in GitHub" at the bottom of the topic.

[Bookbinder](https://github.com/pivotal-cf/bookbinder/) uses the contents of this repository and others as sources to assemble the documentation for Ops Manager.

## <a name="version-branch"></a> Versions and Branches

| **Book Branch** | **Content Branch** | **Published URL** |
|-----------------|--------------------|-------------------|
|          `2.10` |             `2.10` | https://docs.pivotal.io/ops-manager/2-10/index.html |
|           `2.9` |              `2.9` | https://docs.pivotal.io/ops-manager/2-9/index.html  |
|           `2.8` |              `2.8` | https://docs.pivotal.io/ops-manager/2-8/index.html  |
|           `2.7` |              `2.7` | https://docs.pivotal.io/ops-manager/2-7/index.html  |
|          `edge` |           `master` |          not used |
|        `master` |           `master` |          not used |
| `om-previous-versions` | `2.6` | https://docs.pivotal.io/ops-manager/2-6/index.html |
| `om-previous-versions` | `2.5` | https://docs.pivotal.io/ops-manager/2-5/index.html |
| `om-previous-versions` | `2.4` | https://docs.pivotal.io/ops-manager/2-4/index.html |
| `om-previous-versions` | `2.3` | https://docs.pivotal.io/ops-manager/2-3/index.html |
| `om-previous-versions` | `2.2` | https://docs.pivotal.io/ops-manager/2-2/index.html |
| `om-previous-versions` | `2.1` | https://docs.pivotal.io/ops-manager/2-1/index.html |
| `om-previous-versions` | `2.0` | https://docs.pivotal.io/ops-manager/2-0/index.html |


**2.10**: The `2.10` branch is used to publish the v2.10 site. Create pull requests on `2.10` to contribute or
correct technical inaccuracies in the Ops Manager v2.10 documentation.

**2.9**: The `2.9` branch is used to publish the v2.9 site. Create pull requests on `2.9` to contribute or
correct technical inaccuracies in the Ops Manager v2.9 documentation.

**2.8**: The `2.8` branch is used to publish the v2.8 site. Create pull requests on `2.8` to contribute or
correct technical inaccuracies in the Ops Manager v2.8 documentation.

**2.7**: The `2.7` branch is used to publish the v2.7 site. Create pull requests on `2.7` to contribute or
correct technical inaccuracies in the Ops Manager v2.7 documentation.

**2.6**: The `2.6` branch is used to publish the v2.6 site. Create pull requests on `2.6` to contribute or
correct technical inaccuracies in the Ops Manager v2.6 documentation.

**2.5**: The `2.5` branch is used to publish the v2.5 site. The `2.5` branch has reached End of General Support and is
no longer being updated.

**2.4**: The `2.4` branch is used to publish the v2.4 site. The `2.4` branch has reached End of General Support and is
no longer being updated.

**2.3**: The `2.3` branch is used to publish the v2.3 site. The `2.3` branch has reached End of General Support and is
no longer being updated.

**2.2**: The `2.2` branch is used to publish the v2.2 site. The `2.2` branch has reached End of General Support and is
no longer being updated.

**2.1**: The `2.1` branch is used to publish the v2.1 site. The `2.1` branch has reached End of General Support and is
no longer being updated.

**2.0**: The `2.0` branch is used to publish the v2.0 site. The `2.0` branch has reached End of General Support and is
no longer being updated.

## How To Use Bookbinder To View Your Documentation

[Bookbinder](https://github.com/pivotal-cf/bookbinder/blob/master/README.md) is a command-line
utility for stitching Markdown documents into a hostable web app. The documentation team uses
Bookbinder to publish our documentation sites, but you can also use Bookbinder to view a live
version of your documentation on your local machine.

Bookbinder draws the content for the site from this repository, the left navigation menu ("subnav")
from [docs-book-om](https://github.com/pivotal-cf/docs-book-om), and various layout
configuration and assets from [docs-layout-repo](https://github.com/pivotal-cf/docs-layout-repo).

To use Bookbinder to view your documentation, perform the following steps:

1. Clone this repository to the `~/workspace` directory on your local machine.
1. Clone the following repositories to the `~/workspace` directory on your
local machine:
    * [docs-book-om](https://github.com/pivotal-cf/docs-book-om)
    * [docs-layout-repo](https://github.com/pivotal-cf/docs-layout-repo)
    * [docs-partials](https://github.com/pivotal-cf/docs-partials)
1. Use the **Versions and Branching** table above to determine which branch of `docs-ops-manager` that you need to `git checkout` to build the version of the documentation that you want. If necessary, navigate to the `docs-ops-manager` directory and `git checkout BRANCH-NAME`. 
1. Navigate in the `docs-book-om` directory.
1. Run `bundle install` to install all of the necessary gems, including Bookbinder.
1. Run `bundle exec bookbinder bind local` to build a Rack web-app of the book. After the bind has completed, navigate
into the `final_app` directory and run `rackup`. Then navigate to `localhost:9292/platform/ops-manager/index.html` in a
browser.

## Continuous Integration and Continuous Delivery

We use Concourse pipelines to provide continuous integration and continuous delivery. Any change made to this repository
or the [https://github.com/pivotal-cf/docs-book-om](https://github.com/pivotal-cf/docs-book-om) Book repository trigger a
"bind" where the disparate parts of the Ops Manager documentation are assembled into a single web app. A successful bind
triggers pushing the app to the staging site,
[https://docs-pcf-staging.cfapps.io/platform/ops-manager](http://docs-pcf-staging.cfapps.io/platform/ops-manager). After
review, the staging site is manually pushed to the production site,
[https://docs.pivotal.io/platform/ops-manager/](https://docs.pivotal.io/platform/ops-manager/).

Concourse Pipelines:

* **master**: https://concourse.run.pivotal.io/teams/cf-docs/pipelines/om
* **edge**: https://concourse.run.pivotal.io/teams/cf-docs/pipelines/om?group=edge
