## run-dljc

This project contains scripts used to control do-like-javac to run large-scale experiments using Checker Framework whole-program inference.

The most important script is `run-dljc.sh`. It runs whole-program inference on every buildable gradle or maven project in a list of
repository URL, git hash pairs. (It is restricted to using GitHub URLs.) The output is stored in a results directory, which can be summarized
with `summary.sh`. To create an input file, you can use `run-queries.sh` to search GitHub for candidate repositories, or you can write
an input file from scratch.

Three example files are included:
* `no-literal-securerandom-exact-dljc-cmd.sh` is a no-arguments script that serves as an example of how to use `run-dljc.sh` with a
custom checker.
* `securerandom.list` is a list of repositories and hashes in the format expected by `run-dljc.sh`. It was created by invoking `run-queries.sh`
and is used by `no-literal-securerandom-exact-dljc-cmd.sh`.
* `securerandom.query` is the GitHub search query used to create `securerandom.list`. The exact command to create `securerandom.list` is
`./run-queries.sh securerandom.query 100`.

See the documentation of the individual scripts for more information.
