## Step 3: Enable and trigger Dependabot security updates

_Nice work enabling, viewing, and creating Dependabot alerts :sparkles:_

Enabling Dependabot alerts on our repository was a great step toward improving our code security, but we still had to manually select an alert and then manually select the option to create the pull request. It would be nice to further improve the automation and maintenance of our dependencies! Well, with Dependabot security updates, we can do just that.

**What are Dependabot security updates?**: When this feature is enabled, Dependabot detects *and* fixes vulnerable dependencies for you by opening pull requests automatically to resolve Dependabot alerts.

We manually created a pull request to fix the "Prototype Pollution in minimist" alert, but let's enable Dependabot security updates to automate this process for future alerts!

### :keyboard: Activity 3.1: Enable and trigger Dependabot security updates

1. Navigate to the **Settings** tab and select **Code security and analysis**.
1. Enable Dependabot security updates. You may need to wait 30-60 seconds before you see any new pull requests.
1. Navigate to the **Pull requests** repository tab and select the newly created pull request that updates axios from version 0.21.1 to a patched version.
1. Review and merge the pull request.

Wait about 20 seconds then refresh this page (the one you're following instructions from). [GitHub Actions](https://docs.github.com/en/actions) will automatically update this page to display the next step.
