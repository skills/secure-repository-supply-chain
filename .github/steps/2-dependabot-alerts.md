## Step 2: Enable and view Dependabot alerts

_Nice work! :tada: You added and viewed a dependency using Dependency graph!_

Given how many dependencies our repository uses, maintaining them needs to become an automated task. Keeping our code secure is a top priority, so the first thing we need to do is set up a way to be notified when a dependency we are using is vulnerable or malware. We can do this by enabling Dependabot alerts.

**What are Dependabot alerts?**

Dependabot alerts tell you that your code depends on a package that is insecure. These Dependabot alerts reference the [GitHub Advisory Database](https://github.com/advisories), which contains a list of known security vulnerabilities and malware, grouped in two categories: **GitHub reviewed advisories** and **unreviewed advisories**.

If your code depends on a package that has a security vulnerability, this can cause a range of problems for your project or the people who use it. You should upgrade to a secure version of the package as soon as possible. If your code uses malware, you need to replace the package with a secure alternative.

Let's try this out with our newly added `follow-redirects` dependency!

### :keyboard: Activity 2.1: View security advisories in the GitHub Advisory Database

1. Navigate to [GitHub Advisory Database](https://github.com/advisories).
1. Type or paste `follow-redirects` into the advisory search box.
1. Click on any of the advisories that were found to see more information.
1. You'll see the packages, impact, patches, workaround, and references for the advisory.

Notice the long list of advisories for our dependency! This can look scary but it's actually a good thing. It means that our dependency is actively being maintained and patches are being pushed to remove the vulnerability. If we had Dependabot alerts enabled, we could receive alerts when we need to update a dependency and act promptly to secure them.

Let's enable Dependabot alerts on our repository!

### :keyboard: Activity 2.2: Enable Dependabot alerts

1. Navigate to the **Settings** tab.
1. Display the settings for **Advanced Security**.
1. **Enable** Dependabot alerts.
1. **Wait about 60 seconds for Dependabot to check for alerts.**
1. Navigate to the **Security** tab.
1. Under "Vulnerability alerts" in the side bar, select **Dependabot** to view a list of the Dependabot alerts for the default branch.

Dependabot has alerted us to vulnerabilities in the dependencies that we use. We can also use Dependabot to help us address these vulnerabilities by creating pull requests to update the dependency to a safe version.

Let's see how this would work by using Dependabot to create a pull request for one of the alerts!

### :keyboard: Activity 2.3: Create a pull request based on a Dependabot alert

1. In the list of Dependabot alerts, click the "Prototype Pollution in minimist" to display more information.
1. Click the **Create Dependabot security update** button to create a pull request to update the dependency. This could take up to 2 minutes.
1. When the pull request is open, the alert page is updated to show a **Review security update** button.
1. Click the **Review security update** button to display the pull request.
   - You can view the pull request and **Files changed** tab to review the update.
1. Navigate back to the **Conversation** tab and merge the pull request.
1. With the pull request merged, Mona should already be busy checking your work. Give her a moment and keep watch in the comments. You will see her respond with progress info and the next lesson.