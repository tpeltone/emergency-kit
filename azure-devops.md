# Azure DevOps

## Agents

Configure your account by following the steps outlined here.

### Linux

Download the agent

```bash
curl https://vstsagentpackage.azureedge.net/agent/2.165.2/vsts-agent-linux-x64-2.165.2.tar.gz --output vsts-agent-linux-x64-2.165.2.tar.gz
```

Create the agent

```bash
~/$ mkdir agent && cd agent
~/agent$ tar zxvf ~/vsts-agent-linux-x64-2.165.2.tar.gz
```

Configure the agent [Detailed Instructions](https://docs.microsoft.com/en-us/azure/devops/pipelines/agents/v2-linux?view=azure-devops)

```bash
~/agent$ ./config.sh
```

Optionally run the agent interactively
If you didn't run as a service above:

```bash
~/agent$ ./run.sh
```

That's it!  
[More Information](https://github.com/microsoft/azure-pipelines-agent/blob/master/README.md)
