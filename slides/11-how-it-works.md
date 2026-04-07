# How it works?

- **Workflows:** It's an automated procedure composed of one or more jobs that is added to a repository and can be activated by an event. They are defined by YAML files and with it you can build, test, package, relay or deploy a project.
- **Events:** Is a specific activity in a repository that triggers a workflow run. 
- **Jobs:** Is a set of steps in a workflow that execute on the same runner.
- **Actions:**  Is a custom application for the GitHub Actions platform that performs a complex but frequently repeated task.
- **Runners:** It is a machine with the GitHub Actions application already installed, whose function is to wait for the work to be available and then be able to execute the actions and report the progress and the results.

**Create an example workflow**
1. In your repository, create the <kbd>.github/workflows/</kbd> directory to store your workflow files.
2. In the <kbd>.github/workflows/</kbd> directory, create a new file called <kbd>learn-github-actions.yml</kbd> and add the following code.
  
<link href="styles/style.css" rel="stylesheet" type="text/css" />

<!--
- Workflows: an automated process that runs one or more jobs.
- Events: a specific activity in a repository that triggers a workflow run.
- Jobs: a set of steps in a workflow that run on the same runner. Steps run in order and depend on each other.
- Actions: a custom application for GitHub Actions that performs a complex but frequently repeated task.
- Runners: a server that runs your workflows when triggered. Each runner can run one job at a time. GitHub provides Ubuntu, Windows, and macOS runners. You can also host your own runners if you need a different OS or specific hardware.
-->