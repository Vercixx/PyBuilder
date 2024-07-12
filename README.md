# PyDeployer
Small library for building Python projects from Git and running them
# Where this can be used? 
* When you can't access SSH for your server. 
* When you can't download and upload all files from git repository to your server.
* If you just need automation or you update your project too often
# Usage
```python
from pydeployer import GitDeploy, RunStep

# Not an actual user/repo here
repo = 'https://github.com/me/my-awesome-program'

pyproject = GitDeploy(url=repo, auth=['user', 'personal_token'])

for step in pyproject.steps:
	RunStep(step)
	print(f'Step {step} completed')

pyproject.check()
# By default GitDeploy.run() runs main.py, but that can be changed
pyproject.run('app.py')
```
