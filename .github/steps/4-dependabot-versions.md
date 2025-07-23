## Step 4: Enable and trigger Dependabot version updates

_Nicely done!_ :partying_face:

You now have automated the process for Dependabot to alert you to vulnerabilities with your dependencies and to create pull requests to update them to secure versions! At this point, you only need to review the pull request and then merge it to stay on top of security problems with Dependencies.

The security updates feature helps automate the process to resolve alerts, but what about just keeping up-to-date with version updates? We can also automate pull request generation for updated versions of dependencies using the Dependabot version updates feature.

**What are Dependabot version updates?**: In addition to security alerts, Dependabot can also take the effort out of maintaining your dependencies. You can use it to ensure that your repository automatically keeps up with the latest releases of the packages and applications it depends on. Similar to security alerts, Dependabot will identify an outdated dependency and create a pull request to update the manifest to the latest version of the dependency.

Let's see how this works!

### :keyboard: Activity 4.1: Enable and trigger Dependabot version updates

1. Navigate to the **Settings** tab and select **Code security and analysis**.
1. Locate "Dependabot version updates" and click **Configure** to open a new file editor with pre-poplulated contents. The file is called `dependabot.yml`.
1. Notice that the file is prepopulated to update the GitHub actions in the repository, the `github-actions` package ecosystem.
1. Copy the lines that define the GitHub actions updates and append them to the file.
1. Edit your copy of the content:
   - Change the `package-ecosystem` to `nuget`.
   - Change the `directory` to `/code/`.
   - Change the `interval` to `weekly`.
   
   The `dependabot.yml` file should now look like this.
   ```yaml
   version: 2
   updates:
     - package-ecosystem: "github-actions"
       directory: "/"
       schedule:
         interval: "monthly"
     - package-ecosystem: "nuget"
       directory: "/code/"
       schedule:
         interval: "weekly"
    ```
1. Commit your changes directly to the `main` branch.

You have now configured Dependabot version updates to run and check for updates as follows:
- Check once a month for updates to GitHub Actions and create pull requests to update any that are out of date.
- Check once a week for updates to .NET packages and create pull requests to update any that are out of date. By default, this check runs on a Monday, to run the check on a different day, see [schedule.day](https://docs.github.com/en/code-security/dependabot/dependabot-version-updates/configuration-options-for-the-dependabot.yml-file#scheduleday).

Wait about 20 seconds then refresh this page (the one you're following instructions from). [GitHub Actions](https://docs.github.com/en/actions) will automatically update to display the next step.
