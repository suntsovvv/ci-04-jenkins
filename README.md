# Домашнее задание к занятию 10 «Jenkins»
## Подготовка к выполнению
![image](https://github.com/suntsovvv/ci-04-jenkins/assets/154943765/a65dd365-f129-42ec-86e9-a23c6ab76e34)   
![image](https://github.com/suntsovvv/ci-04-jenkins/assets/154943765/4976d299-131e-4c64-a6da-54ff6b96885f)  
## Основная часть
### 1
```
Started by user Suntsov V.V.
Running as SYSTEM
Building remotely on agent (linux ansible) in workspace /home/jenkins/workspace/Freestyle Job
The recommended git tool is: NONE
No credentials specified
 > git rev-parse --resolve-git-dir /home/jenkins/workspace/Freestyle Job/.git # timeout=10
Fetching changes from the remote Git repository
 > git config remote.origin.url https://github.com/suntsovvv/vector-role.git # timeout=10
Fetching upstream changes from https://github.com/suntsovvv/vector-role.git
 > git --version # timeout=10
 > git --version # 'git version 2.34.1'
 > git fetch --tags --force --progress -- https://github.com/suntsovvv/vector-role.git +refs/heads/*:refs/remotes/origin/* # timeout=10
 > git rev-parse refs/remotes/origin/master^{commit} # timeout=10
Checking out Revision b1045f2c24ed7625600fc4e13d6f8da41d75d26d (refs/remotes/origin/master)
 > git config core.sparsecheckout # timeout=10
 > git checkout -f b1045f2c24ed7625600fc4e13d6f8da41d75d26d # timeout=10
Commit message: "Update main.yml"
 > git rev-list --no-walk 9a9489df0788e1950ec76b4f61cc206868b64863 # timeout=10
[Freestyle Job] $ /bin/sh -xe /tmp/jenkins14633605139723501223.sh
+ docker run -dit --name centos7 pycontribs/centos:7 sleep 6000000
d2e64c51994e6b49499fd241d67af910ce1f4949776ff4e9fea3d9287fc8cc39
+ molecule test
INFO     default scenario test matrix: dependency, lint, cleanup, destroy, syntax, create, prepare, converge, idempotence, side_effect, verify, cleanup, destroy
INFO     Performing prerun...
INFO     Running default > dependency
WARNING  Skipping, missing the requirements file.
WARNING  Skipping, missing the requirements file.
INFO     Running default > lint
COMMAND: ansible-lint .
yamllint .

WARNING  Listing 13 violation(s) that are fatal
name[casing]: All names should start with an uppercase letter.
handlers/main.yml:2 Task/Handler: restart vector service

no-changed-when: Commands should not change things if nothing needs doing.
handlers/main.yml:2 Task/Handler: restart vector service

yaml[trailing-spaces]: Trailing spaces
handlers/main.yml:6

meta-incorrect: Should change default metadata: license
meta/main.yml:1

schema[meta]: $.galaxy_info.min_ansible_version 2.1 is not of type 'string'. See https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_reuse_roles.html#using-role-dependencies
meta/main.yml:1  Returned errors will not include exact line numbers, but they will mention
the schema name being used as a tag, like ``schema[playbook]``,
``schema[tasks]``.

This rule is not skippable and stops further processing of the file.

If incorrect schema was picked, you might want to either:

* move the file to standard location, so its file is detected correctly.
* use ``kinds:`` option in linter config to help it pick correct file type.


yaml[indentation]: Wrong indentation: expected 4 but found 3
meta/main.yml:32

yaml[indentation]: Wrong indentation: expected 7 but found 5
meta/main.yml:34

schema[tasks]: $[2].become 1 is not of type 'boolean'
tasks/main.yml:1  Returned errors will not include exact line numbers, but they will mention
the schema name being used as a tag, like ``schema[playbook]``,
``schema[tasks]``.

This rule is not skippable and stops further processing of the file.

If incorrect schema was picked, you might want to either:

* move the file to standard location, so its file is detected correctly.
* use ``kinds:`` option in linter config to help it pick correct file type.


yaml[indentation]: Wrong indentation: expected 6 but found 5
tasks/main.yml:13

yaml[truthy]: Truthy value should be one of [false, true]
tasks/main.yml:14

risky-file-permissions: File permissions unset or incorrect.
tasks/main.yml:49 Task/Handler: Generate vector config

yaml[trailing-spaces]: Trailing spaces
tasks/main.yml:50

yaml[trailing-spaces]: Trailing spaces
tasks/main.yml:51

Read documentation for instructions on how to ignore specific rule violations.

                      Rule Violation Summary
 count tag                    profile  rule associated tags
     1 schema[meta]           basic    core
     1 schema[tasks]          basic    core
     3 yaml[indentation]      basic    formatting, yaml
     3 yaml[trailing-spaces]  basic    formatting, yaml
     1 yaml[truthy]           basic    formatting, yaml
     1 name[casing]           moderate idiom
     1 risky-file-permissions safety   unpredictability
     1 meta-incorrect         shared   metadata
     1 no-changed-when        shared   command-shell, idempotency

Failed: 13 failure(s), 0 warning(s) on 6 files. Last profile that met the validation criteria was 'min'.
./molecule/default/molecule.yml
  15:1      error    too many blank lines (1 > 0)  (empty-lines)

./molecule/default/verify.yml
  1:1       warning  missing document start "---"  (document-start)
  5:3       error    wrong indentation: expected at least 3  (indentation)
  14:12     error    trailing spaces  (trailing-spaces)
  15:81     error    line too long (122 > 80 characters)  (line-length)
  16:18     error    too many spaces before colon  (colons)
  20:12     error    trailing spaces  (trailing-spaces)
  22:18     error    too many spaces before colon  (colons)

./molecule/tox/converge.yml
  7:26      error    no new line character at the end of file  (new-line-at-end-of-file)

./molecule/tox/molecule.yml
  20:19     error    no new line character at the end of file  (new-line-at-end-of-file)

./handlers/main.yml
  3:1       warning  comment not indented like content  (comments-indentation)
  6:1       error    trailing spaces  (trailing-spaces)

./tasks/main.yml
  4:81      error    line too long (106 > 80 characters)  (line-length)
  13:6      error    wrong indentation: expected 6 but found 5  (indentation)
  14:22     warning  truthy value should be one of [false, true]  (truthy)
  21:81     error    line too long (105 > 80 characters)  (line-length)
  36:81     error    line too long (106 > 80 characters)  (line-length)
  50:28     error    trailing spaces  (trailing-spaces)
  51:24     error    trailing spaces  (trailing-spaces)

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

CRITICAL Lint failed with error code 1
WARNING  An error occurred during the test sequence action: 'lint'. Cleaning up.
INFO     Running default > cleanup
WARNING  Skipping, cleanup playbook not configured.
INFO     Running default > destroy
INFO     Sanity checks: 'docker'

PLAY [Destroy] *****************************************************************

TASK [Set async_dir for HOME env] **********************************************
ok: [localhost]

TASK [Destroy molecule instance(s)] ********************************************
changed: [localhost] => (item=centos7)

TASK [Wait for instance(s) deletion to complete] *******************************
FAILED - RETRYING: [localhost]: Wait for instance(s) deletion to complete (300 retries left).
changed: [localhost] => (item=centos7)

TASK [Delete docker networks(s)] ***********************************************
skipping: [localhost]

PLAY RECAP *********************************************************************
localhost                  : ok=3    changed=2    unreachable=0    failed=0    skipped=1    rescued=0    ignored=0

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




