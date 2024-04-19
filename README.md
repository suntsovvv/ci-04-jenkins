# Домашнее задание к занятию 10 «Jenkins»
## Подготовка к выполнению
![image](https://github.com/suntsovvv/ci-04-jenkins/assets/154943765/a65dd365-f129-42ec-86e9-a23c6ab76e34)   
![image](https://github.com/suntsovvv/ci-04-jenkins/assets/154943765/4976d299-131e-4c64-a6da-54ff6b96885f)  
## Основная часть
### 1
```
Started by user Suntsov V.V.
Running as SYSTEM
Building remotely on agent1 (linux ansible) in workspace /opt/jenkins_agent/workspace/Freestyle Job
The recommended git tool is: NONE
No credentials specified
 > git rev-parse --resolve-git-dir /opt/jenkins_agent/workspace/Freestyle Job/.git # timeout=10
Fetching changes from the remote Git repository
 > git config remote.origin.url https://github.com/suntsovvv/vector-role.git # timeout=10
Fetching upstream changes from https://github.com/suntsovvv/vector-role.git
 > git --version # timeout=10
 > git --version # 'git version 2.43.0'
 > git fetch --tags --force --progress -- https://github.com/suntsovvv/vector-role.git +refs/heads/*:refs/remotes/origin/* # timeout=10
 > git rev-parse refs/remotes/origin/master^{commit} # timeout=10
Checking out Revision 03994a915633f37fe1588b7d9cc240815b0e4739 (refs/remotes/origin/master)
 > git config core.sparsecheckout # timeout=10
 > git checkout -f 03994a915633f37fe1588b7d9cc240815b0e4739 # timeout=10
Commit message: "Update molecule.yml"
 > git rev-list --no-walk 03994a915633f37fe1588b7d9cc240815b0e4739 # timeout=10
[Freestyle Job] $ /bin/sh -xe /tmp/jenkins14046572099664453810.sh
+ pip3 install molecule molecule-docker yamllint ansible-lint
Defaulting to user installation because normal site-packages is not writeable
Requirement already satisfied: molecule in /home/jenkins/.local/lib/python3.6/site-packages (3.6.1)
Requirement already satisfied: molecule-docker in /home/jenkins/.local/lib/python3.6/site-packages (1.1.0)
Requirement already satisfied: yamllint in /home/jenkins/.local/lib/python3.6/site-packages (1.28.0)
Collecting ansible-lint
  Downloading ansible_lint-5.4.0-py3-none-any.whl (119 kB)
Requirement already satisfied: dataclasses in /usr/local/lib/python3.6/site-packages (from molecule) (0.8)
Requirement already satisfied: importlib-metadata in /usr/local/lib/python3.6/site-packages (from molecule) (4.8.3)
Requirement already satisfied: cookiecutter>=1.7.3 in /home/jenkins/.local/lib/python3.6/site-packages (from molecule) (1.7.3)
Requirement already satisfied: Jinja2>=2.11.3 in /usr/local/lib/python3.6/site-packages (from molecule) (3.0.3)
Requirement already satisfied: rich>=9.5.1 in /usr/local/lib/python3.6/site-packages (from molecule) (12.6.0)
Requirement already satisfied: ansible-compat>=1.0.0 in /home/jenkins/.local/lib/python3.6/site-packages (from molecule) (1.0.0)
Requirement already satisfied: pluggy<2.0,>=0.7.1 in /home/jenkins/.local/lib/python3.6/site-packages (from molecule) (1.0.0)
Requirement already satisfied: enrich>=1.2.7 in /home/jenkins/.local/lib/python3.6/site-packages (from molecule) (1.2.7)
Requirement already satisfied: click<9,>=8.0 in /home/jenkins/.local/lib/python3.6/site-packages (from molecule) (8.0.4)
Requirement already satisfied: paramiko<3,>=2.5.0 in /home/jenkins/.local/lib/python3.6/site-packages (from molecule) (2.12.0)
Requirement already satisfied: packaging in /usr/local/lib/python3.6/site-packages (from molecule) (21.3)
Requirement already satisfied: click-help-colors>=0.9 in /home/jenkins/.local/lib/python3.6/site-packages (from molecule) (0.9.4)
Requirement already satisfied: PyYAML>=5.1 in /home/jenkins/.local/lib/python3.6/site-packages (from molecule) (6.0.1)
Requirement already satisfied: cerberus!=1.3.3,!=1.3.4,>=1.3.1 in /home/jenkins/.local/lib/python3.6/site-packages (from molecule) (1.3.5)
Requirement already satisfied: requests in /usr/local/lib/python3.6/site-packages (from molecule-docker) (2.27.1)
Requirement already satisfied: docker>=4.3.1 in /home/jenkins/.local/lib/python3.6/site-packages (from molecule-docker) (5.0.3)
Requirement already satisfied: selinux in /usr/lib64/python3.6/site-packages (from molecule-docker) (2.9)
Requirement already satisfied: pathspec>=0.5.3 in /home/jenkins/.local/lib/python3.6/site-packages (from yamllint) (0.9.0)
Requirement already satisfied: setuptools in /usr/lib/python3.6/site-packages (from yamllint) (39.2.0)
Collecting tenacity
  Downloading tenacity-8.2.2-py3-none-any.whl (24 kB)
Requirement already satisfied: typing-extensions in /usr/local/lib/python3.6/site-packages (from ansible-lint) (4.1.1)
Collecting ruamel.yaml<1,>=0.15.34
  Downloading ruamel.yaml-0.18.3-py3-none-any.whl (114 kB)
Collecting wcmatch>=7.0
  Downloading wcmatch-8.3-py3-none-any.whl (42 kB)
Requirement already satisfied: cached-property~=1.5 in /home/jenkins/.local/lib/python3.6/site-packages (from ansible-compat>=1.0.0->molecule) (1.5.2)
Requirement already satisfied: subprocess-tee>=0.3.5 in /usr/local/lib/python3.6/site-packages (from ansible-compat>=1.0.0->molecule) (0.3.5)
Requirement already satisfied: poyo>=0.5.0 in /home/jenkins/.local/lib/python3.6/site-packages (from cookiecutter>=1.7.3->molecule) (0.5.0)
Requirement already satisfied: binaryornot>=0.4.4 in /home/jenkins/.local/lib/python3.6/site-packages (from cookiecutter>=1.7.3->molecule) (0.4.4)
Requirement already satisfied: jinja2-time>=0.2.0 in /home/jenkins/.local/lib/python3.6/site-packages (from cookiecutter>=1.7.3->molecule) (0.2.0)
Requirement already satisfied: python-slugify>=4.0.0 in /home/jenkins/.local/lib/python3.6/site-packages (from cookiecutter>=1.7.3->molecule) (6.1.2)
Requirement already satisfied: six>=1.10 in /usr/lib/python3.6/site-packages (from cookiecutter>=1.7.3->molecule) (1.11.0)
Requirement already satisfied: websocket-client>=0.32.0 in /home/jenkins/.local/lib/python3.6/site-packages (from docker>=4.3.1->molecule-docker) (1.3.1)
Requirement already satisfied: MarkupSafe>=2.0 in /usr/local/lib64/python3.6/site-packages (from Jinja2>=2.11.3->molecule) (2.0.1)
Requirement already satisfied: bcrypt>=3.1.3 in /home/jenkins/.local/lib/python3.6/site-packages (from paramiko<3,>=2.5.0->molecule) (4.0.1)
Requirement already satisfied: pynacl>=1.0.1 in /home/jenkins/.local/lib/python3.6/site-packages (from paramiko<3,>=2.5.0->molecule) (1.5.0)
Requirement already satisfied: cryptography>=2.5 in /usr/lib64/python3.6/site-packages (from paramiko<3,>=2.5.0->molecule) (3.2.1)
Requirement already satisfied: zipp>=0.5 in /usr/local/lib/python3.6/site-packages (from importlib-metadata->molecule) (3.6.0)
Requirement already satisfied: charset-normalizer~=2.0.0 in /usr/local/lib/python3.6/site-packages (from requests->molecule-docker) (2.0.12)
Requirement already satisfied: certifi>=2017.4.17 in /usr/local/lib/python3.6/site-packages (from requests->molecule-docker) (2024.2.2)
Requirement already satisfied: idna<4,>=2.5 in /usr/lib/python3.6/site-packages (from requests->molecule-docker) (2.5)
Requirement already satisfied: urllib3<1.27,>=1.21.1 in /usr/lib/python3.6/site-packages (from requests->molecule-docker) (1.24.2)
Requirement already satisfied: commonmark<0.10.0,>=0.9.0 in /usr/local/lib/python3.6/site-packages (from rich>=9.5.1->molecule) (0.9.1)
Requirement already satisfied: pygments<3.0.0,>=2.6.0 in /usr/local/lib/python3.6/site-packages (from rich>=9.5.1->molecule) (2.14.0)
Collecting ruamel.yaml.clib>=0.2.7
  Downloading ruamel.yaml.clib-0.2.8-cp36-cp36m-manylinux_2_5_x86_64.manylinux1_x86_64.whl (546 kB)
Collecting bracex>=2.1.1
  Downloading bracex-2.2.1-py3-none-any.whl (12 kB)
Requirement already satisfied: pyparsing!=3.0.5,>=2.0.2 in /usr/local/lib/python3.6/site-packages (from packaging->molecule) (3.1.2)
Requirement already satisfied: chardet>=3.0.2 in /usr/lib/python3.6/site-packages (from binaryornot>=0.4.4->cookiecutter>=1.7.3->molecule) (3.0.4)
Requirement already satisfied: cffi!=1.11.3,>=1.8 in /usr/lib64/python3.6/site-packages (from cryptography>=2.5->paramiko<3,>=2.5.0->molecule) (1.11.5)
Requirement already satisfied: arrow in /usr/local/lib/python3.6/site-packages (from jinja2-time>=0.2.0->cookiecutter>=1.7.3->molecule) (1.2.3)
Requirement already satisfied: text-unidecode>=1.3 in /usr/local/lib/python3.6/site-packages (from python-slugify>=4.0.0->cookiecutter>=1.7.3->molecule) (1.3)
Requirement already satisfied: pycparser in /usr/lib/python3.6/site-packages (from cffi!=1.11.3,>=1.8->cryptography>=2.5->paramiko<3,>=2.5.0->molecule) (2.14)
Requirement already satisfied: python-dateutil>=2.7.0 in /usr/local/lib/python3.6/site-packages (from arrow->jinja2-time>=0.2.0->cookiecutter>=1.7.3->molecule) (2.9.0.post0)
Installing collected packages: ruamel.yaml.clib, bracex, wcmatch, tenacity, ruamel.yaml, ansible-lint
Successfully installed ansible-lint-5.4.0 bracex-2.2.1 ruamel.yaml-0.18.3 ruamel.yaml.clib-0.2.8 tenacity-8.2.2 wcmatch-8.3
+ molecule test
INFO     default scenario test matrix: dependency, lint, cleanup, destroy, syntax, create, prepare, converge, idempotence, side_effect, verify, cleanup, destroy
INFO     Performing prerun...
INFO     Set ANSIBLE_LIBRARY=/home/jenkins/.cache/ansible-compat/f78241/modules:/home/jenkins/.ansible/plugins/modules:/usr/share/ansible/plugins/modules
INFO     Set ANSIBLE_COLLECTIONS_PATH=/home/jenkins/.cache/ansible-compat/f78241/collections:/home/jenkins/.ansible/collections:/usr/share/ansible/collections
INFO     Set ANSIBLE_ROLES_PATH=/home/jenkins/.cache/ansible-compat/f78241/roles:/home/jenkins/.ansible/roles:/usr/share/ansible/roles:/etc/ansible/roles
INFO     Using /home/jenkins/.ansible/roles/my_galaxy_namespace.my_name symlink to current repository in order to enable Ansible to find the role using its expected full name.
INFO     Running default > dependency
WARNING  Skipping, missing the requirements file.
WARNING  Skipping, missing the requirements file.
INFO     Running default > lint
WARNING: PATH altered to include /usr/bin
WARNING  Listing 12 violation(s) that are fatal
yaml: trailing spaces (trailing-spaces)
handlers/main.yml:6

meta-incorrect: Should change default metadata: license
meta/main.yml:1

yaml: wrong indentation: expected 4 but found 3 (indentation)
meta/main.yml:32

yaml: wrong indentation: expected 7 but found 5 (indentation)
meta/main.yml:34

yaml: wrong indentation: expected 6 but found 5 (indentation)
tasks/main.yml:13

yaml: truthy value should be one of [false, true] (truthy)
tasks/main.yml:14

risky-file-permissions: File permissions unset or incorrect
tasks/main.yml:49 Task/Handler: Generate vector config

yaml: trailing spaces (trailing-spaces)
tasks/main.yml:50

yaml: trailing spaces (trailing-spaces)
tasks/main.yml:51

yaml: too many blank lines (3 > 2) (empty-lines)
tasks/main.yml:56

yaml: trailing spaces (trailing-spaces)
tasks/main.yml:107

yaml: trailing spaces (trailing-spaces)
tasks/main.yml:108

You can skip specific rules or tags by adding them to your configuration file:
# .ansible-lint
warn_list:  # or 'skip_list' to silence them completely
  - experimental  # all rules tagged as experimental
  - meta-incorrect  # meta/main.yml default values should be changed
  - yaml  # Violations reported by yamllint

Finished with 11 failure(s), 1 warning(s) on 6 files.
./handlers/main.yml
  3:1       warning  comment not indented like content  (comments-indentation)
  6:1       error    trailing spaces  (trailing-spaces)

./meta/main.yml
  1:1       warning  missing document start "---"  (document-start)
  22:81     error    line too long (84 > 80 characters)  (line-length)
  26:81     error    line too long (84 > 80 characters)  (line-length)
  27:81     error    line too long (85 > 80 characters)  (line-length)
  32:4      error    wrong indentation: expected 4 but found 3  (indentation)
  34:6      error    wrong indentation: expected 7 but found 5  (indentation)
  43:5      warning  comment not indented like content  (comments-indentation)
  43:81     error    line too long (83 > 80 characters)  (line-length)
  44:81     error    line too long (82 > 80 characters)  (line-length)
  47:81     error    line too long (83 > 80 characters)  (line-length)
  51:3      warning  comment not indented like content  (comments-indentation)
  51:81     error    line too long (85 > 80 characters)  (line-length)

./molecule/default/converge.yml
  7:26      error    no new line character at the end of file  (new-line-at-end-of-file)

./molecule/default/verify.yml
  1:1       warning  missing document start "---"  (document-start)
  14:12     error    trailing spaces  (trailing-spaces)
  15:81     error    line too long (122 > 80 characters)  (line-length)
  16:18     error    too many spaces before colon  (colons)
  20:12     error    trailing spaces  (trailing-spaces)
  22:18     error    too many spaces before colon  (colons)

./molecule/tox/converge.yml
  7:26      error    no new line character at the end of file  (new-line-at-end-of-file)

./molecule/tox/molecule.yml
  20:19     error    no new line character at the end of file  (new-line-at-end-of-file)

./tasks/main.yml
  4:81      error    line too long (106 > 80 characters)  (line-length)
  13:6      error    wrong indentation: expected 6 but found 5  (indentation)
  14:22     warning  truthy value should be one of [false, true]  (truthy)
  21:81     error    line too long (105 > 80 characters)  (line-length)
  36:81     error    line too long (106 > 80 characters)  (line-length)
  50:28     error    trailing spaces  (trailing-spaces)
  51:24     error    trailing spaces  (trailing-spaces)
  56:1      error    too many blank lines (3 > 2)  (empty-lines)
  62:81     error    line too long (112 > 80 characters)  (line-length)
  79:81     error    line too long (111 > 80 characters)  (line-length)
  94:81     error    line too long (112 > 80 characters)  (line-length)
  107:30    error    trailing spaces  (trailing-spaces)
  108:26    error    trailing spaces  (trailing-spaces)

WARNING  Retrying execution failure 1 of: a n s i b l e - l i n t   . 
 y a m l l i n t   . 

CRITICAL Lint failed with error code 1
WARNING  An error occurred during the test sequence action: 'lint'. Cleaning up.
INFO     Running default > cleanup
WARNING  Skipping, cleanup playbook not configured.
INFO     Running default > destroy
INFO     Sanity checks: 'docker'

PLAY [Destroy] *****************************************************************

TASK [Destroy molecule instance(s)] ********************************************
changed: [localhost] => (item=centos7)

TASK [Wait for instance(s) deletion to complete] *******************************
ok: [localhost] => (item=centos7)

TASK [Delete docker networks(s)] ***********************************************

PLAY RECAP *********************************************************************
localhost                  : ok=2    changed=1    unreachable=0    failed=0    skipped=1    rescued=0    ignored=0

INFO     Pruning extra files from scenario ephemeral directory
Build step 'Execute shell' marked build as failure
Finished: FAILURE
```
### 2   
```Started by user Suntsov V.V.
[Pipeline] Start of Pipeline
[Pipeline] node
Running on agent1 in /opt/jenkins_agent/workspace/Declarative Pipeline
[Pipeline] {
[Pipeline] stage
[Pipeline] { (Download role from github)
[Pipeline] git
The recommended git tool is: NONE
No credentials specified
Cloning the remote Git repository
Avoid second fetch
Checking out Revision 45a5cfe8f72858365f7f3cb4d0d2acd8a8b801f2 (refs/remotes/origin/master)
Commit message: "Update molecule.yml"
First time build. Skipping changelog.
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (m_test)
[Pipeline] sh
Cloning repository https://github.com/suntsovvv/vector-role.git
 > git init /opt/jenkins_agent/workspace/Declarative Pipeline # timeout=10
Fetching upstream changes from https://github.com/suntsovvv/vector-role.git
 > git --version # timeout=10
 > git --version # 'git version 2.43.0'
 > git fetch --tags --force --progress -- https://github.com/suntsovvv/vector-role.git +refs/heads/*:refs/remotes/origin/* # timeout=10
 > git config remote.origin.url https://github.com/suntsovvv/vector-role.git # timeout=10
 > git config --add remote.origin.fetch +refs/heads/*:refs/remotes/origin/* # timeout=10
 > git rev-parse refs/remotes/origin/master^{commit} # timeout=10
 > git config core.sparsecheckout # timeout=10
 > git checkout -f 45a5cfe8f72858365f7f3cb4d0d2acd8a8b801f2 # timeout=10
 > git branch -a -v --no-abbrev # timeout=10
 > git checkout -b master 45a5cfe8f72858365f7f3cb4d0d2acd8a8b801f2 # timeout=10
+ molecule test
INFO     default scenario test matrix: dependency, lint, cleanup, destroy, syntax, create, prepare, converge, idempotence, side_effect, verify, cleanup, destroy
INFO     Performing prerun...
INFO     Set ANSIBLE_LIBRARY=/home/jenkins/.cache/ansible-compat/668096/modules:/home/jenkins/.ansible/plugins/modules:/usr/share/ansible/plugins/modules
INFO     Set ANSIBLE_COLLECTIONS_PATH=/home/jenkins/.cache/ansible-compat/668096/collections:/home/jenkins/.ansible/collections:/usr/share/ansible/collections
INFO     Set ANSIBLE_ROLES_PATH=/home/jenkins/.cache/ansible-compat/668096/roles:/home/jenkins/.ansible/roles:/usr/share/ansible/roles:/etc/ansible/roles
INFO     Using /home/jenkins/.ansible/roles/my_galaxy_namespace.my_name symlink to current repository in order to enable Ansible to find the role using its expected full name.
INFO     Running default > dependency
INFO     Running ansible-galaxy collection install -v --force community.docker:>=1.9.1
WARNING  Skipping, missing the requirements file.
WARNING  Skipping, missing the requirements file.
INFO     Running default > lint
WARNING: PATH altered to include /usr/bin
WARNING  Listing 12 violation(s) that are fatal
yaml: trailing spaces (trailing-spaces)
handlers/main.yml:6

meta-incorrect: Should change default metadata: license
meta/main.yml:1

yaml: wrong indentation: expected 4 but found 3 (indentation)
meta/main.yml:32

yaml: wrong indentation: expected 7 but found 5 (indentation)
meta/main.yml:34

yaml: wrong indentation: expected 6 but found 5 (indentation)
tasks/main.yml:13

yaml: truthy value should be one of [false, true] (truthy)
tasks/main.yml:14

risky-file-permissions: File permissions unset or incorrect
tasks/main.yml:49 Task/Handler: Generate vector config

yaml: trailing spaces (trailing-spaces)
tasks/main.yml:50

yaml: trailing spaces (trailing-spaces)
tasks/main.yml:51

yaml: too many blank lines (3 > 2) (empty-lines)
tasks/main.yml:56

yaml: trailing spaces (trailing-spaces)
tasks/main.yml:107

yaml: trailing spaces (trailing-spaces)
tasks/main.yml:108

You can skip specific rules or tags by adding them to your configuration file:
# .ansible-lint
warn_list:  # or 'skip_list' to silence them completely
  - experimental  # all rules tagged as experimental
  - meta-incorrect  # meta/main.yml default values should be changed
  - yaml  # Violations reported by yamllint

Finished with 11 failure(s), 1 warning(s) on 6 files.
./handlers/main.yml
  3:1       warning  comment not indented like content  (comments-indentation)
  6:1       error    trailing spaces  (trailing-spaces)

./meta/main.yml
  1:1       warning  missing document start "---"  (document-start)
  22:81     error    line too long (84 > 80 characters)  (line-length)
  26:81     error    line too long (84 > 80 characters)  (line-length)
  27:81     error    line too long (85 > 80 characters)  (line-length)
  32:4      error    wrong indentation: expected 4 but found 3  (indentation)
  34:6      error    wrong indentation: expected 7 but found 5  (indentation)
  43:5      warning  comment not indented like content  (comments-indentation)
  43:81     error    line too long (83 > 80 characters)  (line-length)
  44:81     error    line too long (82 > 80 characters)  (line-length)
  47:81     error    line too long (83 > 80 characters)  (line-length)
  51:3      warning  comment not indented like content  (comments-indentation)
  51:81     error    line too long (85 > 80 characters)  (line-length)

./molecule/default/converge.yml
  7:26      error    no new line character at the end of file  (new-line-at-end-of-file)

./molecule/default/verify.yml
  1:1       warning  missing document start "---"  (document-start)
  14:12     error    trailing spaces  (trailing-spaces)
  15:81     error    line too long (122 > 80 characters)  (line-length)
  16:18     error    too many spaces before colon  (colons)
  20:12     error    trailing spaces  (trailing-spaces)
  22:18     error    too many spaces before colon  (colons)

./molecule/tox/converge.yml
  7:26      error    no new line character at the end of file  (new-line-at-end-of-file)

./molecule/tox/molecule.yml
  20:19     error    no new line character at the end of file  (new-line-at-end-of-file)

./tasks/main.yml
  4:81      error    line too long (106 > 80 characters)  (line-length)
  13:6      error    wrong indentation: expected 6 but found 5  (indentation)
  14:22     warning  truthy value should be one of [false, true]  (truthy)
  21:81     error    line too long (105 > 80 characters)  (line-length)
  36:81     error    line too long (106 > 80 characters)  (line-length)
  50:28     error    trailing spaces  (trailing-spaces)
  51:24     error    trailing spaces  (trailing-spaces)
  56:1      error    too many blank lines (3 > 2)  (empty-lines)
  62:81     error    line too long (112 > 80 characters)  (line-length)
  79:81     error    line too long (111 > 80 characters)  (line-length)
  94:81     error    line too long (112 > 80 characters)  (line-length)
  107:30    error    trailing spaces  (trailing-spaces)
  108:26    error    trailing spaces  (trailing-spaces)

WARNING  Retrying execution failure 1 of: a n s i b l e - l i n t   . 
 y a m l l i n t   . 

CRITICAL Lint failed with error code 1
WARNING  An error occurred during the test sequence action: 'lint'. Cleaning up.
INFO     Running default > cleanup
WARNING  Skipping, cleanup playbook not configured.
INFO     Running default > destroy
INFO     Sanity checks: 'docker'

PLAY [Destroy] *****************************************************************

TASK [Destroy molecule instance(s)] ********************************************
changed: [localhost] => (item=centos7)

TASK [Wait for instance(s) deletion to complete] *******************************
FAILED - RETRYING: Wait for instance(s) deletion to complete (300 retries left).
ok: [localhost] => (item=centos7)

TASK [Delete docker networks(s)] ***********************************************

PLAY RECAP *********************************************************************
localhost                  : ok=2    changed=1    unreachable=0    failed=0    skipped=1    rescued=0    ignored=0

INFO     Pruning extra files from scenario ephemeral directory
[Pipeline] }
[Pipeline] // stage
[Pipeline] }
[Pipeline] // node
[Pipeline] End of Pipeline
ERROR: script returned exit code 1
Finished: FAILURE
```
### 3   
[Jenkinsfile](https://github.com/suntsovvv/vector-role/blob/master/Jenkinsfile)   
### 4   



