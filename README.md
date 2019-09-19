Script for auto sync/merge the code from branch [A] to [B] with just one click

## How to start  
```
vim config.txt
```
And update the configs to what you want
```
DEVELOP_BRANCH="develop"
REMOTE_REPO="https://github.com/pjq/auto_sync_branch.git"
LOCAL_REPO="local"
WORKSPACE="./auto_sync_branch_workspace"
RULE="develop>pjq/develop|pjq/develop>user/develop"
```

Then run it
```
chmod +x auto_sync_branch.sh
./auto_sync_branch.sh
```
Output
```
./auto_sync_branch.sh
read config...
Prepare the workspace...
Cloning into 'local'...
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (4/4), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (4/4), done.
start sync...
Sync rule develop>pjq/develop
Start Sync code from develop to pjq/develop
From https://github.com/pjq/auto_sync_branch
 * branch            develop    -> FETCH_HEAD
From https://github.com/pjq/auto_sync_branch
 * branch            pjq/develop -> FETCH_HEAD
Branch 'pjq/develop' set up to track remote branch 'pjq/develop' from 'origin'.
Switched to a new branch 'pjq/develop'
git checkout pjq/develop success!
Already up to date.
Merge develop > pjq/develop success!
Push to remote success!
Sync develop>pjq/develop success!
Sync rule pjq/develop>user/develop
Start Sync code from pjq/develop to user/develop
From https://github.com/pjq/auto_sync_branch
 * branch            pjq/develop -> FETCH_HEAD
From https://github.com/pjq/auto_sync_branch
 * branch            user/develop -> FETCH_HEAD
Branch 'user/develop' set up to track remote branch 'user/develop' from 'origin'.
Switched to a new branch 'user/develop'
git checkout user/develop success!
Already up to date.
Merge pjq/develop > user/develop success!
Push to remote success!
Sync pjq/develop>user/develop success!
```
## Update Rules
The rule is simple, define the branch `from>to`, and use "|" to split different rules

```
RULE="develop>pjq/develop|pjq/develop>user/develop"
```

