# Repo health command

I want a small local command that reports repository health. It should probably
be Python, unless Rust is better. It needs to be fast, future-facing, and usable
by people and agents. It should show branch, dirty files, upstream divergence,
and worktrees. Maybe it should also merge worktrees automatically, although I
do not want destructive behavior or surprise merges.

The agent should inspect the repository before deciding. The command needs
`--help`, text and JSON output, tests, and useful failures outside a Git
repository. Do not implement it during preparation. Produce a plan another
agent can execute in bounded steps and independently audit.
