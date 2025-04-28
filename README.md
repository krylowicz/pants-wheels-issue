Running:

```shell
pants run src:pex
```
with Pants version 2.23.0 works as intended.

Running the same command after upgrading to pants 2.24.0 or 2.25.0, gives the following error:

```shell
08:20:55.94 [INFO] Initializing scheduler...
08:20:57.54 [INFO] Scheduler initialized.
08:21:00.00 [INFO] Completed: Building 1 requirement for src/pex.pex from the python-default.lock resolve: MarkupSafe==3.0.2
08:21:00.01 [ERROR] 1 Exception encountered:

Engine traceback:
  in `run` goal

ProcessExecutionFailure: Process 'Building 1 requirement for src/pex.pex from the python-default.lock resolve: MarkupSafe==3.0.2' failed with exit code 1.
stdout:

stderr:
No pre-built wheel was available for MarkupSafe 3.0.2.
Successfully built the wheel markupsafe-3.0.2-cp311-cp311-linux_x86_64.whl from the sdist markupsafe-3.0.2.tar.gz but it is not compatible with the requested foreign target complete platform cp311-cp311abi3-manylinux_2_35_aarch64.
You'll need to build a wheel from markupsafe-3.0.2.tar.gz on the foreign target platform and make it available to Pex via a `--find-links` repo or a custom `--index`.



Use `--keep-sandboxes=on_failure` to preserve the process chroot for inspection.
```
