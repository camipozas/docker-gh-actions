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
- **Workflows:** es un proceso automatizado configurable que ejecutará uno o más jobs.
- **Events:** Un evento es una actividad específica en un repositorio, la cual activa una ejecución de flujo de trabajo.
- **Jobs:** es un conjunto de pasos en un flujo de trabajo, los cuales se ejecutan en el mismo ejecutor. Los pasos se ejecutarán en orden y serán dependientes uno del otro.
- **Actions:** es una aplicación personalizada para la plataforma de GitHub Actions que realiza una tarea compleja pero que se repite frecuentemente.
- **Runners:** es un servidor que ejecuta tus flujos de trabajo cuando se activan. Cada ejecutor puede ejecutar un job individual a la vez. GitHub proporciona ejecutores de Ubuntu Linux, Microsoft Windows y macOS para ejecutar tus flujos de trabajo; cada flujo de trabajo se ejecuta en una máquina virtual nueva y recién aprovisionada. Si necesitas un sistema operativo diferente o si requieres una configuración de hardware específica, puedes hospedar tus propios ejecutores. 
-->