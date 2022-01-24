# Gerrit

## Useful links

[Gerrit Documentation](https://gerrit-review.googlesource.com/Documentation/)

### Replication Plugin

[Documentation](https://gerrit.wikimedia.org/r/plugins/replication/Documentation/cmd-start.md)

```bash
# Replicate all
ssh -p 29418 localhost replication start --now --wait --all

# Add "time" to see how long it takes
# Add "| tee mylogfile.txt" to log the output   
time ssh -p 29418 localhost replication start --now --wait --all | tee mylogfile.txt

# Replicate specific repository
ssh -p 29418 localhost replication start --now --wait myproject/myteam/aosp/platform/frameworks/native
```

### Check Gerrit queue

```bash
# Check Gerrit Queue
ssh -p 29418 my-gerrit.srv.awesome.com gerrit show-queue -w
```

If there is no queue, you can check logs at _$GERRIT_HOME/logs/_

## Trouble shooting

### Replication

After a replication is done compare the repos on each server to see if you have erros

```bash

# On EBN Gerrit list references in a remote repository
git ls-remote --heads ssh://localhost:29418/myproject/myteam/aosp/platform/frameworks/native

# Result
0756f727203e5c530c035d6f3819d78e2d234a22        refs/heads/android-q-B3-vis-vol-ivi-ce_my22
26fe9a2cb2a4317e9d5907f5ed31ee1ee23c2d7b        refs/heads/android-q-C-CS63-vis-vol-ivi-ce_my22
41e9d621e8c13733c29e80ff9f8e2d835ba51a65        refs/heads/android-q-C-CS73-vis-vol-ivi-ce_my22
e2cd9196dbca9688c08ae7503a05f2076d5c449c        refs/heads/android-q-vis-vol-ivi-ce_my22
2a59a002ff3d95d4201bb0cf12c6be70d94d0a51        refs/heads/master


# On VCE Gerrit list references in a remote repository
git ls-remote --heads ssh://localhost:29418/myproject/myteam/aosp/platform/frameworks/native

# Result
0756f727203e5c530c035d6f3819d78e2d234a22        refs/heads/android-q-B3-vis-vol-ivi-ce_my22
e2cd9196dbca9688c08ae7503a05f2076d5c449c        refs/heads/android-q-vis-vol-ivi-ce_my22
2a59a002ff3d95d4201bb0cf12c6be70d94d0a51        refs/heads/master
 ```

As you see they differ
