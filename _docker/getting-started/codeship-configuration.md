---
title: Configuring the project on Codeship
layout: page
weight: 84
tags:
  - docker
  - jet
  - introduction
  - getting started
  - project configuration
  - tutorial
category: Getting Started
redirect_from:
  - /docker/codeship-configuration/
---

<div class="info-block">
The configuration information below is specific to Codeship's Docker based infrastructure. For more information see [codeship.com](https://codeship.com/enterprise)
</div>

Once you have your [project running locally]({{ site.baseurl }}{% link _docker/getting-started/getting-started.md %}) you can configure the repository on Codeship and have the builds run on each push.

If you already worked with Codeship the process will be familiar (and if not, it should be very simple nonetheless).

1. Click on the _Select Project_ dropdown in the top bar and select the _Create a new project_ button.
2. Select the repository provider you want to host your repositories with.
3. Select the repository you want to build on Codeship. You can filter the list via the search form. (If a repository belonging to an organization on GitHub isn't listed, please take a look at [3rd party restrictions]({{ site.baseurl }}{% link _general/account/github-3rd-party-restrictions.md %}).)

	So far these are the standard steps to add a new project on Codeship.

4. You can now choose between a standard Codeship build or a build based on the Docker Infrastructure. Choose the latter.
	![Select Docker Infrastructure]({{ site.baseurl }}/images/docker/setup_select_docker.png)
5. You will be presented with a screen offering basic setup instructions, as well as a link to the documentation for the Codeship Docker Infrastructure.
	![Docker Project Help Screen]({{ site.baseurl }}/images/docker/setup_docker_setup.png)

	As we already added all the required information to the [repository](https://github.com/codeship/jet-tutorial), you can simply push a new commit and this will trigger a new build on Codeship.
6. Once you trigger a (couple) new builds, you'll see the standard Codeship build listing page.
	![Build Listing]({{ site.baseurl }}/images/docker/build_listing.png)
7. Clicking on a single build takes you to the build details.
	![Build Details]({{ site.baseurl }}/images/docker/build_details.png)

	The page is split in two panes. On the left hand side you will find basic build details, including the commit message, who triggered the build and which branch (or tag) triggered the build.

	You will also see the [services]({% link _docker/getting-started/services.md %}) defined in your _codeship-services.yml_ file (if you click on the _Services_ header as this section is hidden by default).

	The main portion of the left pane is dedicated to listing the [steps]({% link _docker/getting-started/steps.md %}) you have defined. Clicking on a single step will open the step log in the right pane. Each step includes the following information:

	* the command you are running
	* the service the step is running on (on the right hand side)
	* the status indicated by an icon

8. The remaining project configuration (e.g. team management or notifications) is identical to a standard Codeship project and accessible via the _Project Settings_ dropdown at the top.
