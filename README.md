<!--
  <<< Author notes: Header of the course >>>
  Include a 1280×640 image, course title in sentence case, and a concise description in emphasis.
  In your repository settings: enable template repository, add your 1280×640 social image, auto delete head branches.
  Add your open source license, GitHub uses Creative Commons Attribution 4.0 International.
-->

# Secure your repository's supply chain

_Secure your supply chain, understand dependencies in your environment, know about vulnerabilities in those dependencies and patch them._

<!--
  <<< Author notes: Start of the course >>>
  Include start button, a note about Actions minutes,
  and tell the learner why they should take the course.
  Each step should be wrapped in <details>/<summary>, with an `id` set.
  The start <details> should have `open` as well.
  Do not use quotes on the <details> tag attributes.
-->

<details id=0 open>
<summary><h2>Welcome</h2></summary>

GitHub helps you secure your supply chain, from understanding the dependencies in your environment, to knowing about vulnerabilities in those dependencies and patching them.

- **Who this is for**: Developers, DevOps Engineers, Site Reliability Engineers, Security experts
- **What you'll learn**: How to view repository dependencies, view Dependabot alerts, and enable Dependabot security and version updates
- **What you'll build**: Repository dependencies, Dependabot alerts, pull requests to fix dependencies and version updates
- **Prerequisites**: None
- **Timing**: This course is four steps long and can be completed in under an hour

## How to start this course

1. Right-click **Start course** and open the link in a new tab.
   <br />[![start-course](https://user-images.githubusercontent.com/1221423/218596841-0645fe1a-4aaf-4f51-9ab3-8aa2d3fdd487.svg)](https://github.com/skills/secure-repository-supply-chain/generate)
2. In the new tab, follow the prompts to create a new repository.
   - For owner, choose your personal account or an organization to host the repository.
   - We recommend creating a public repository—private repositories will [use Actions minutes](https://docs.github.com/en/billing/managing-billing-for-github-actions/about-billing-for-github-actions).
   ![Create a new repository](https://user-images.githubusercontent.com/1221423/218594143-e60462b6-9f2a-4fa3-80de-063ac5429aab.png)
3. After your new repository is created, wait about 20 seconds, then refresh the page. Follow the step-by-step instructions in the new repository's README.

</details>

<details id=1>
<summary><h2>Step 1: Review and add dependencies using dependency graph</h2></summary>

_Welcome to "Secure your repository's supply chain"! :wave:_

**What's the big deal about securing your repository's supply chain?**: With the accelerated use of open source, most projects depend on hundreds of open-source dependencies. This poses a security problem: what if the dependencies you're using are vulnerable? You could be putting your users at risk of a supply chain attack. One of the most important things you can do to protect your supply chain is to patch your vulnerable dependencies and replace any malware.

GitHub offers a range of features to help you understand the dependencies in your environment, know about vulnerabilities in those dependencies, and patch them. The supply chain features on GitHub are:

- Dependency graph
- Dependency review
- Dependabot alerts
- Dependabot updates
  - Dependabot security updates
  - Dependabot version updates
   
**What is a dependency graph**: The dependency graph is a summary of the manifest and lock files stored in a repository and any dependencies that are submitted for the repository using the dependency submission API (beta). For each repository, it shows:

* Dependencies, the ecosystems and packages it depends on
* Dependents, the repositories and packages that depend on it

### :keyboard: Activity: Verify that dependency graph is enabled

**We recommend opening another browser tab to work through the following activities so you can keep these instructions open for reference.**

1. Navigate to the `Settings` tab.
1. Click `Code security and analysis`.
1. Verify/enable **Dependency graph**. (If the repo is private, you will enable it here. If the repo is public, it will be enabled by default)

### :keyboard: Activity: Add a new dependency and view your dependency graph

1. Navigate to the `Code` tab and locate the `code/src/AttendeeSite` folder.
1. Add the following content to the `package-lock.json` file after the third to last `}`
   ```
   ,
    "follow-redirects": {
      "version": "1.14.1",
      "resolved": "https://registry.npmjs.org/follow-redirects/-/follow-redirects-1.14.1.tgz",
      "integrity": "sha512-HWqDgT7ZEkqRzBvc2s64vSZ/hfOceEol3ac/7tKwzuvEyWx3/4UegXh5oBOIotkGsObyk3xznnSRVADBgWSQVg=="
    }
   ```
1. Navigate to the `Insights` tab.
1. Click `Dependency graph`.
1. Review all new dependencies on the `Dependencies` hub.
1. Search for `follow-redirects` and review the new dependency you just added.
   ![Screen Shot 2022-10-17 at 3 37 36 PM](https://user-images.githubusercontent.com/6351798/196288729-734e3319-c5d7-4f35-a19c-676c12f0e27d.png)

**Wait about 20 seconds then refresh this page for the next step**
</details>

<details id=2>
<summary><h2>Step 2: Enable and view Dependabot alerts</h2></summary>

_Nice work! :tada: You added and viewed a dependency with `dependency graph`!_

Given how many dependencies our repository is using, maintaining them needs to become an automated task. Keeping our code secure is a top priority, so one thing we need to do is set up a way to be notified when a dependency we are using is vulnerable or malware. We can do this by enabling Dependabot alerts!

**What are Dependabot alerts?**: Dependabot alerts tell you that your code depends on a package that is insecure. These Dependabot alerts reference the [GitHub Advisory Database](https://github.com/advisories), which contains a list of known security vulnerabilities and malware, grouped in two categories: **GitHub reviewed advisories** and **unreviewed advisories**.

If your code depends on a package that has a security vulnerability, this can cause a range of problems for your project or the people who use it. You should upgrade to a secure version of the package as soon as possible. If your code uses malware, you need to replace the package with a secure alternative.

Let's try this out with our newly added `follow-redirects` dependency!
 
### :keyboard: Activity: View security advisories in the GitHub Advisory Database

1. Navigate to the [GitHub Advisory Database](https://github.com/advisories).
1. Type or paste `follow-redirects` into the search box.
1. Click on any of the advisories that were found.
1. Note the packages, impact, patches, workaround, and references for the advisory.

Notice the list of advisories for our dependency! This can look scary but it's actually a good thing. It means that our dependency is actively being maintained and patches are being pushed to remove the vulnerability. If we had Dependabot alerts enabled, we could receive alerts when we need to update a dependency and act promptly to secure them.

Let's enable Dependabot alerts on our repository!

 ### :keyboard: Activity: Enable Dependabot alerts

1. Navigate to the `Settings` tab.
1. Click `Code security and analysis`.  
1. Click `Enable` Dependabot alerts (**Wait about 60 seconds and then click the `Security` tab at the top of the repository**).
1. Review each of the four `Dependabot` alerts under the `Vulnerability alerts` section.

Dependabot has alerted us of four vulnerabilities that need to be updated from the dependencies that we are using. Dependabot helps us address these vulnerabilities by creating pull requests for each one as we select and review the alert.

Let's see how this would work by using Dependabot to create a pull request for one of the alerts!

 ### :keyboard: Activity: Create a pull request based on a Dependabot alert

1. Select the `Prototype Pollution in minimist` alert under the `Dependabot alerts` section and click on the alert. 
1. Click the `Create Dependabot security update` button (**This will create a pull request for the fix and could take ~2 minutes**).
1. Click the `Review security update` button. The pull request will be displayed.
   - You can view the pull request and `Files changed` tab to review the update.
1. Navigate back to the `Conversation` tab and click the `Merge pull request` button.
1. Click `Confirm merge`.

**Wait about 20 seconds then refresh this page for the next step.**
 
</details>

<details id=3>
<summary><h2>Step 3: Enable and trigger Dependabot security updates</h2></summary>

_Nice work enabling, viewing, and creating Dependabot alerts :sparkles:_

Enabling Dependabot alerts on our repository was a great step toward improving our code security, but we still had to manually select an alert and then manually select the option to create the pull request. It would be nice to further improve the automation and maintenance of our dependencies! Well, with Dependabot security updates, we can do just that.

**What are Dependabot security updates?**: When enabled, Dependabot will detect and fix vulnerable dependencies for you by opening pull requests automatically to resolve Dependabot alerts when they arise.

We manually created the pull request for the `Prototype Pollution in minimist` alert, but let's now enable Dependabot security updates to automate this process with the next alert!

### :keyboard: Activity: Enable and trigger Dependabot security updates

1. Navigate to the `Settings` tab, select `Code security and analysis`, and enable the `Dependabot security updates`.
1. Navigate to the `Pull requests` repository tab and select the newly created pull request titled **Bump axios from 0.21.1 to 0.21.2 in /code/src/AttendeeSite**. 
   - You may need to wait 30-60 seconds.
1. Click the `Merge pull request` button.
1. Click `Confirm merge`.

**Wait about 20 seconds then refresh this page for the next step.**

</details>

<details id=4>
<summary><h2>Step 4: Enable and trigger Dependabot version updates</h2></summary>

_Nicely done!_ :partying_face:

You now have automated the process for Dependabot to alert and create pull requests to update your dependencies! At this point, you only need to review the pull request and then merge it to stay on top of your security alerts. 

The security updates feature helps automate the process to resolve alerts, but what about just keeping up-to-date with version updates? We can have the same automation to update our dependencies for updated versions using the Dependabot version updates feature. 

**What are Dependabot version updates?**: In addition to security alerts, Dependabot can also take the effort out of maintaining your dependencies. You can use it to ensure that your repository automatically keeps up with the latest releases of the packages and applications it depends on. Just like security alerts, Dependabot will identify an outdated dependency and create a pull request to update the manifest to the latest version of the dependency.

Let's see how this works!

### :keyboard: Activity: Enable and trigger Dependabot version updates

1. Navigate to the `Settings` tab, select `Code security and analysis`, and enable the `Dependabot version updates`.
   - A new file editor opens with pre-poplulated contents. The file is called `dependabot.yml`.
6. Add `nuget` to the `package-ecosystem`.
7. Change the `directory` to `/code/`. (The `dependabot.yml` file should look like this)
   ![Screen Shot 2022-09-27 at 6 52 45 AM](https://user-images.githubusercontent.com/26442605/192545528-dfc33648-94ce-4421-8710-c5bb0a41b0ec.png)
9. Click `Commit changes` directly to the main branch.

**Wait about 20 seconds then refresh this page for the next step.**


</details>

<details id=X>
<summary><h2>Finish</h2></summary>

_Congratulations friend, you've completed this course!_

<img src="https://octodex.github.com/images/welcometocat.png" alt=celebrate width=300 align=right>

Here's a recap of all the tasks you've accomplished in your repository:

* You've learned how to view and use dependency graph.
* You've learned how to enable and use Dependabot alerts.
* You've learned how to enable and use Dependabot secuirty updates.
* You've learned how to enable and use Dependabot version updates.

### Additional learning and resources

- [Dependency graph](https://docs.github.com/en/code-security/supply-chain-security/understanding-your-software-supply-chain/about-the-dependency-graph)
- [Exploring the dependencies of a repository](https://docs.github.com/en/code-security/supply-chain-security/understanding-your-software-supply-chain/exploring-the-dependencies-of-a-repository)
- [About supply chain security](https://docs.github.com/en/code-security/supply-chain-security/understanding-your-software-supply-chain/about-supply-chain-security)
- [Dependabot alerts](https://docs.github.com/en/code-security/dependabot/dependabot-alerts/about-dependabot-alerts)
- [GitHub Advisory Database](https://docs.github.com/en/code-security/dependabot/dependabot-alerts/browsing-security-advisories-in-the-github-advisory-database)


### What's next?

- Learn more about securing your supply chain by reading: [Securing your supply chain](https://docs.github.com/en/code-security/supply-chain-security/understanding-your-software-supply-chain/about-supply-chain-security).
- [We'd love to hear what you thought of this course](https://github.com/skills/.github/discussions).
- [Learn another GitHub skill](https://github.com/skills).
- [Read the Get started with GitHub docs](https://docs.github.com/en/get-started).
- To find projects to contribute to, check out [GitHub Explore](https://github.com/explore).

</details>

<!--
  <<< Author notes: Footer >>>
  Add a link to get support, GitHub status page, code of conduct, license link.
-->

---

Get help: [Post in our discussion board](https://github.com/skills/.github/discussions) &bull; [Review the GitHub status page](https://www.githubstatus.com/)

&copy; 2022 GitHub &bull; [Code of Conduct](https://www.contributor-covenant.org/version/2/1/code_of_conduct/code_of_conduct.md) &bull; [MIT License](https://gh.io/mit)
