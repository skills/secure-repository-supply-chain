## Step 2: Enable and view Dependabot alerts

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
1. Review each of the `Dependabot` alerts under the `Vulnerability alerts` section.

Dependabot has alerted us of vulnerabilities that need to be updated from the dependencies that we are using. Dependabot helps us address these vulnerabilities by creating pull requests for each one as we select and review the alert.

Let's see how this would work by using Dependabot to create a pull request for one of the alerts!

### :keyboard: Activity: Create a pull request based on a Dependabot alert

1. Select the `Prototype Pollution in minimist` alert under the `Dependabot alerts` section and click on the alert.
1. Click the `Create Dependabot security update` button (**This will create a pull request for the fix and could take ~2 minutes**).
1. Click the `Review security update` button. The pull request will be displayed.
   - You can view the pull request and `Files changed` tab to review the update.
1. Navigate back to the `Conversation` tab and click the `Merge pull request` button.
1. Click `Confirm merge`.
1. Wait about 20 seconds then refresh this page (the one you're following instructions from). [GitHub Actions](https://docs.github.com/en/actions) will automatically update to the next step.
