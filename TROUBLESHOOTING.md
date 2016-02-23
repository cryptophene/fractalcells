# Common failures:


## library/iocage not present
```
fatal: [redacted]: FAILED! => {"failed": true, "reason": "ERROR! no action detected in task\n\nThe error appears to have been in '/usr/local/jenkins/workspace/Set_up_testing_server/roles/comb/tasks/iocage.yml': line 75, column 3, but may\nbe elsewhere in the file depending on the exact syntax problem.\n\nThe offending line appears to be:\n\n\n- name: Check if basejail already exists\n  ^ here\n"}
```

### Solution:
```
mkdir library
cd library
git clone https://github.com/fractalcells/ansible-iocage.git .
```
