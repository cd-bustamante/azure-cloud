# Azure DevOps

## Azure DevOps Services

A suite of services that adress every stage of the software development lifcycle.

- **Azure Repos** centralized source-code repository where software development, DevOps engineering, and documentation professionals can publish their code for review and collaboration.
- **Azure Boards** an agile project management suite that includes Kanban boards, reporting and tracking ideas and work from high-level epis to work items and issues.
- **Azure Pipelines** is a CI/CD pipeline automation tool.
- **Azure Artifacts** repository for hosting artifacts, such as compiles source code, which can be fed into testing or deployment pipeline steps.
- **Azure Test Plans** is an automated test tool that can be used in a CI/CD pipeline to ensure quality before a software release.

Azure DevOps is a mature tool with a large feature set that began as on-premises server software and evolved into a software as a services (SaaS) offering from Microsoft.

## GitHub and GitHub Actions

The worlds most popular code repository for open-source software. Decentralized source-code management tool, and GitHub is a hosted version of Git that serves as the primary remote. Builds on top of Git to provide related services for coordinating work, reporting and discussing issues, providing documentation, and more. It offers the following functionality:

- Shared source-code repository, including tools that enable developers to perform code reviews by adding comments and question in a web view of the source code befire it can be merged into the main code base.
- Failitates project management, including Kanban boards.
- Supports issue reporting, discussion and tracking.
- Features Cu/CD pipeline automation tooling
- Includes a wiki for collaborative documentation.
- Can be run from the cloud or on-premises.

GitHub Actions enables workflow automation with triggers for many lifecycle events. One such example would be automating a CI/CD toolchain.

## Azure DevTest Labs

Azure DevTest Labs provides an automated means of managing the process of building, setting up, and tearing down virtual machines (VMs) that contain builds of your software projects. This way, developers and testers can perform tests across a variety of environments and builds. And this capability isn't limited to VMs. Anything you can deploy in Azure via an ARM template can be provisioned through DevTest Labs. Provisioning pre-created lab environments with their required configurations and tools already installed is a huge time saver for quality assurance professionals and developers.

Suppose you need to test a new feature on an old version of an operating system. Azure DevTest Labs can set up everything automatically upon request. After the testing is complete, DevTest Labs can shut down and deprovision the VM, which saves money when it's not in use. To control costs, the management team can restrict how many labs can be created, how long they run, and so on.
