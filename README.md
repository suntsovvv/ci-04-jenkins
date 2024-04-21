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
```

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
```
### 3   
[Jenkinsfile](https://github.com/suntsovvv/vector-role/blob/master/Jenkinsfile)   
### 4   
```
Started by user Suntsov V.V.
Obtained Jenkinsfile from git git@github.com:suntsovvv/vector-role.git
[Pipeline] Start of Pipeline
[Pipeline] node
Running on agent in /home/jenkins/workspace/Multibranch Pipeline
[Pipeline] {
[Pipeline] stage
[Pipeline] { (Declarative: Checkout SCM)
[Pipeline] checkout
Selected Git installation does not exist. Using Default
The recommended git tool is: NONE
using credential c9e4ee73-67a6-4b7d-a935-52578d88e2c1
Fetching changes from the remote Git repository
 > git rev-parse --resolve-git-dir /home/jenkins/workspace/Multibranch Pipeline/.git # timeout=10
 > git config remote.origin.url git@github.com:suntsovvv/vector-role.git # timeout=10
Fetching upstream changes from git@github.com:suntsovvv/vector-role.git
 > git --version # timeout=10
 > git --version # 'git version 2.34.1'
using GIT_SSH to set credentials 
Verifying host key using known hosts file
 > git fetch --tags --force --progress -- git@github.com:suntsovvv/vector-role.git +refs/heads/*:refs/remotes/origin/* # timeout=10
Checking out Revision b1045f2c24ed7625600fc4e13d6f8da41d75d26d (refs/remotes/origin/master)
Commit message: "Update main.yml"
First time build. Skipping changelog.
[Pipeline] }
 > git rev-parse refs/remotes/origin/master^{commit} # timeout=10
 > git config core.sparsecheckout # timeout=10
 > git checkout -f b1045f2c24ed7625600fc4e13d6f8da41d75d26d # timeout=10
[Pipeline] // stage
[Pipeline] withEnv
[Pipeline] {
[Pipeline] stage
[Pipeline] { (Download role from github)
[Pipeline] git
Selected Git installation does not exist. Using Default
The recommended git tool is: NONE
No credentials specified
Fetching changes from the remote Git repository
Checking out Revision b1045f2c24ed7625600fc4e13d6f8da41d75d26d (refs/remotes/origin/master)
Commit message: "Update main.yml"
First time build. Skipping changelog.
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (m_test)
[Pipeline] sh
+ molecule test
 > git rev-parse --resolve-git-dir /home/jenkins/workspace/Multibranch Pipeline/.git # timeout=10
 > git config remote.origin.url https://github.com/suntsovvv/vector-role.git # timeout=10
Fetching upstream changes from https://github.com/suntsovvv/vector-role.git
 > git --version # timeout=10
 > git --version # 'git version 2.34.1'
 > git fetch --tags --force --progress -- https://github.com/suntsovvv/vector-role.git +refs/heads/*:refs/remotes/origin/* # timeout=10
 > git rev-parse refs/remotes/origin/master^{commit} # timeout=10
 > git config core.sparsecheckout # timeout=10
 > git checkout -f b1045f2c24ed7625600fc4e13d6f8da41d75d26d # timeout=10
 > git branch -a -v --no-abbrev # timeout=10
 > git checkout -b master b1045f2c24ed7625600fc4e13d6f8da41d75d26d # timeout=10
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
ok: [localhost] => (item=centos7)

TASK [Delete docker networks(s)] ***********************************************
skipping: [localhost]

PLAY RECAP *********************************************************************
localhost                  : ok=3    changed=1    unreachable=0    failed=0    skipped=1    rescued=0    ignored=0

INFO     Pruning extra files from scenario ephemeral directory
[Pipeline] }
[Pipeline] // stage
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // node
[Pipeline] End of Pipeline
ERROR: script returned exit code 1
Finished: FAILURE
```
### 5   
```
Started by user Suntsov V.V.
[Pipeline] Start of Pipeline
[Pipeline] node
Running on agent in /home/jenkins/workspace/Scripted Pipeline
[Pipeline] {
[Pipeline] stage
[Pipeline] { (Git checkout)
[Pipeline] git
The recommended git tool is: NONE
using credential c9e4ee73-67a6-4b7d-a935-52578d88e2c1
Fetching changes from the remote Git repository
 > git rev-parse --resolve-git-dir /home/jenkins/workspace/Scripted Pipeline/.git # timeout=10
 > git config remote.origin.url git@github.com:aragastmatb/example-playbook.git # timeout=10
Fetching upstream changes from git@github.com:aragastmatb/example-playbook.git
 > git --version # timeout=10
 > git --version # 'git version 2.34.1'
using GIT_SSH to set credentials 
Verifying host key using known hosts file
 > git fetch --tags --force --progress -- git@github.com:aragastmatb/example-playbook.git +refs/heads/*:refs/remotes/origin/* # timeout=10
Checking out Revision 20bd8d945340bb742acdd9e8c1a8fb5b73cc1700 (refs/remotes/origin/master)
Commit message: "Merge branch 'master' of https://github.com/aragastmatb/example-playbook"
 > git rev-parse refs/remotes/origin/master^{commit} # timeout=10
 > git config core.sparsecheckout # timeout=10
 > git checkout -f 20bd8d945340bb742acdd9e8c1a8fb5b73cc1700 # timeout=10
 > git branch -a -v --no-abbrev # timeout=10
 > git branch -D master # timeout=10
 > git checkout -b master 20bd8d945340bb742acdd9e8c1a8fb5b73cc1700 # timeout=10
 > git rev-list --no-walk 20bd8d945340bb742acdd9e8c1a8fb5b73cc1700 # timeout=10
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Sample define secret_check)
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Run playbook)
[Pipeline] sh
+ ansible-playbook site.yml -i inventory/prod.yml

PLAY [Install Java] ************************************************************

TASK [Gathering Facts] *********************************************************
ok: [localhost]

TASK [java : Upload .tar.gz file containing binaries from local storage] *******
skipping: [localhost]

TASK [java : Upload .tar.gz file conaining binaries from remote storage] *******
ok: [localhost]

TASK [java : Ensure installation dir exists] ***********************************
ok: [localhost]

TASK [java : Extract java in the installation directory] ***********************
skipping: [localhost]

TASK [java : Export environment variables] *************************************
ok: [localhost]

PLAY RECAP *********************************************************************
localhost                  : ok=4    changed=0    unreachable=0    failed=0    skipped=2    rescued=0    ignored=0   

[Pipeline] }
[Pipeline] // stage
[Pipeline] }
[Pipeline] // node
[Pipeline] End of Pipeline
Finished: SUCCESS
```
### 6   
Started by user Suntsov V.V.
[Pipeline] Start of Pipeline
[Pipeline] node
Running on agent in /home/jenkins/workspace/Scripted Pipeline
[Pipeline] {
[Pipeline] stage
[Pipeline] { (Git checkout)
[Pipeline] git
The recommended git tool is: NONE
using credential c9e4ee73-67a6-4b7d-a935-52578d88e2c1
Fetching changes from the remote Git repository
 > git rev-parse --resolve-git-dir /home/jenkins/workspace/Scripted Pipeline/.git # timeout=10
 > git config remote.origin.url git@github.com:aragastmatb/example-playbook.git # timeout=10
Fetching upstream changes from git@github.com:aragastmatb/example-playbook.git
 > git --version # timeout=10
 > git --version # 'git version 2.34.1'
using GIT_SSH to set credentials 
Verifying host key using known hosts file
 > git fetch --tags --force --progress -- git@github.com:aragastmatb/example-playbook.git +refs/heads/*:refs/remotes/origin/* # timeout=10
Checking out Revision 20bd8d945340bb742acdd9e8c1a8fb5b73cc1700 (refs/remotes/origin/master)
Commit message: "Merge branch 'master' of https://github.com/aragastmatb/example-playbook"
 > git rev-parse refs/remotes/origin/master^{commit} # timeout=10
 > git config core.sparsecheckout # timeout=10
 > git checkout -f 20bd8d945340bb742acdd9e8c1a8fb5b73cc1700 # timeout=10
 > git branch -a -v --no-abbrev # timeout=10
 > git branch -D master # timeout=10
 > git checkout -b master 20bd8d945340bb742acdd9e8c1a8fb5b73cc1700 # timeout=10
 > git rev-list --no-walk 20bd8d945340bb742acdd9e8c1a8fb5b73cc1700 # timeout=10
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Sample define secret_check)
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Defind prod_run)
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Run playbook)
[Pipeline] sh
+ ansible-playbook site.yml -i inventory/prod.yml --check --diff

PLAY [Install Java] ************************************************************

TASK [Gathering Facts] *********************************************************
ok: [localhost]

TASK [java : Upload .tar.gz file containing binaries from local storage] *******
skipping: [localhost]

TASK [java : Upload .tar.gz file conaining binaries from remote storage] *******
ok: [localhost]

TASK [java : Ensure installation dir exists] ***********************************
ok: [localhost]

TASK [java : Extract java in the installation directory] ***********************
skipping: [localhost]

TASK [java : Export environment variables] *************************************
ok: [localhost]

PLAY RECAP *********************************************************************
localhost                  : ok=4    changed=0    unreachable=0    failed=0    skipped=2    rescued=0    ignored=0   

[Pipeline] }
[Pipeline] // stage
[Pipeline] }
[Pipeline] // node
[Pipeline] End of Pipeline
Finished: SUCCESS   
```





