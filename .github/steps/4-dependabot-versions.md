## Step 4: Enable and trigger Dependabot version updates

_Nicely done!_ :partying_face:

You now have automated the process for Dependabot to alert and create pull requests to update your dependencies! At this point, you only need to review the pull request and then merge it to stay on top of your security alerts.

The security updates feature helps automate the process to resolve alerts, but what about just keeping up-to-date with version updates? We can have the same automation to update our dependencies for updated versions using the Dependabot version updates feature.

**What are Dependabot version updates?**: In addition to security alerts, Dependabot can also take the effort out of maintaining your dependencies. You can use it to ensure that your repository automatically keeps up with the latest releases of the packages and applications it depends on. Just like security alerts, Dependabot will identify an outdated dependency and create a pull request to update the manifest to the latest version of the dependency.

Let's see how this works!

### :keyboard: Activity: Enable and trigger Dependabot version updates

1. Navigate to the `Settings` tab, select `Code security and analysis`, and enable the `Dependabot version updates`.
   - A new file editor opens with pre-poplulated contents. The file is called `dependabot.yml`.
1. Add `nuget` to the `package-ecosystem`.
1. Change the `directory` to `/code/`. (The `dependabot.yml` file should look like this)
   ![Screen Shot 2022-09-27 at 6 52 45 AM](https://user-images.githubusercontent.com/26442605/192545528-dfc33648-94ce-4421-8710-c5bb0a41b0ec.png)
1. Click `Commit changes` directly to the main branch.
1. Wait about 20 seconds then refresh this page (the one you're following instructions from). [GitHub Actions](https://docs.github.com/en/actions) will automatically update to the next step.
