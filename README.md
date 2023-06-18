Introduction to Git workflows ALL TIERS
With Git, you can use a variety of branching strategies and workflows. Having a structured workflow for collaboration in complex projects is crucial for several reasons:

Code organization: Keep the codebase organized, prevent overlapping work, and ensure focused efforts towards a common goal.

Version control: Allow simultaneous work on different features without conflicts, maintaining code stability.

Code quality: A code review and approval process helps maintain high code quality and adherence to coding standards.

Traceability and accountability: Enable tracking of changes and their authors, simplifying issue identification and responsibility assignment.

Easier onboarding: Help new team members quickly grasp the development process, and start contributing effectively.

Time and resource management: Enable better planning, resource allocation, and meeting deadlines, ensuring an efficient development process.

CI/CD: Incorporate automated testing and deployment processes, streamlining the release cycle and delivering high-quality software consistently.

A structured workflow promotes organization, efficiency, and code quality, leading to a more successful and streamlined development process.

If the default workflow is not specifically defined, many organizations end up with workflows that are:

Too complicated.
Not clearly defined.
Not integrated with their issue tracking systems.
Your organization can use GitLab with any workflow you choose.
Workflow types
Here are some of the most common Git workflows.

Centralized workflow
Best suited for small teams transitioning from a centralized version control system like SVN. All team members work on a single branch, usually main, and push their changes directly to the central repository.

Feature branch workflow
Developers create separate branches for each feature or bugfix, keeping the ‘main’ branch stable. When a feature is complete, the developer submits a merge request to integrate the changes back into main after a code review.

Forking workflow
Commonly used in open-source projects, this workflow allows external contributors to work without direct access to the main repository. Developers create a fork (personal copy) of the main repository and make changes in it. They then submit a merge request to have those changes integrated into the main repository.

Git flow workflow
This workflow is best for projects with a structured release cycle. It introduces two long-lived branches: main for production-ready code and develop for integrating features. Additional branches like feature, release, and hotfix are used for specific purposes, ensuring a strict and organized development process.

GitLab/GitHub flow
A simplified workflow primarily used for web development and continuous deployment. It combines aspects of the Feature branch workflow and the Git flow workflow. Developers create feature branches from main, and after the changes are complete, they are merged back into the main branch, which is then immediately deployed.

Each of these Git workflows has its advantages and is suited to different project types and team structures. Below the most popular workflows are reviewed in more details.

Git workflow
Most version control systems have only one step: committing from the working copy to a shared server.

When you convert to Git, you have to get used to the fact that it takes three steps to share a commit with colleagues.

In Git, you add files from the working copy to the staging area. After that, you commit them to your local repository. The third step is pushing to a shared remote repository.

![image](https://github.com/BiberIdolik/GitLab-flow/assets/136133677/786b8292-eef8-469d-81f6-e5e55caca383)
After getting used to these three steps, the next challenge is the branching model.

Because many organizations new to Git have no conventions for how to work with it, their repositories can quickly become messy. The biggest problem is that many long-running branches emerge that all contain part of the changes. People have a hard time figuring out which branch has the latest code, or which branch to deploy to production. Frequently, the reaction to this problem is to adopt a standardized pattern such as Git flow and GitHub flow.

We think there is still room for improvement, and so we’ve proposed a set of practices called the GitLab Flow.

For a video introduction of this workflow in GitLab, see GitLab Flow.

Problems with the Git flow
Git flow was one of the first proposals to use Git branches, and it has received a lot of attention. It suggests a main branch and a separate develop branch, with supporting branches for features, releases, and hotfixes. The development happens on the develop branch, moves to a release branch, and is finally merged into the main branch.

Git flow is a well-defined standard, but its complexity introduces two problems. The first problem is that developers must use the develop branch and not main. main is reserved for code that is released to production. It is a convention to call your default branch main and to mostly branch from and merge to this. Because most tools automatically use the main branch as the default, it is annoying to have to switch to another branch.

The second problem of Git flow is the complexity introduced by the hotfix and release branches. These branches can be a good idea for some organizations but are overkill for the vast majority of them. Nowadays, most organizations practice continuous delivery, which means that your default branch can be deployed. Continuous delivery removes the need for hotfix and release branches, including all the ceremony they introduce. An example of this ceremony is the merging back of release branches. Though specialized tools do exist to solve this, they require documentation and add complexity. Frequently, developers make mistakes such as merging changes only into main and not into the develop branch. The reason for these errors is that Git flow is too complicated for most use cases. For example, many projects do releases but don’t need to do hotfixes.

![image](https://github.com/BiberIdolik/GitLab-flow/assets/136133677/50dd7090-17de-4f7d-b8f3-b1e698605e47)

