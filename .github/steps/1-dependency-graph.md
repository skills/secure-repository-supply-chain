## Step 1: Review and add dependencies using dependency graph

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

- Dependencies, the ecosystems and packages it depends on
- Dependents, the repositories and packages that depend on it

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
1. Wait about 20 seconds then refresh this page (the one you're following instructions from). [GitHub Actions](https://docs.github.com/en/actions) will automatically update to the next step.
