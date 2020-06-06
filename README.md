# azure agent
# How to use

1. First, you need a token for `PAT` authentication. You can get the token from one user's "Security Settings".

2. Then, run this command:

`docker run -d -e AZP_URL="{azure host}/{organization name}" -e AZP_TOKEN={your token} -e AZP_POOL={pool name} -e AZP_AGENT_NAME={agent name} -e VSS_ALLOW_UNSAFE_BASICAUTH=true --name azureagent --restart unless-stopped daoye/azureagent:latest`


3. If you need run docker in docker:

`docker run -d -e AZP_URL="{azure host}/{organization name}" -e AZP_TOKEN={your token} -e AZP_POOL={pool name} -e AZP_AGENT_NAME={agent name} -e VSS_ALLOW_UNSAFE_BASICAUTH=true --name azureagent --restart unless-stopped --privileged -v /var/run/docker.sock:/var/run/docker.sock -v $(which docker):/bin/docker daoye/azureagent:latest`


For more information visit:

https://docs.microsoft.com/en-us/azure/devops/pipelines/agents/docker?view=azure-devops#linux
