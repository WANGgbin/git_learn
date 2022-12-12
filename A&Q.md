描述 git 中常见的问题.
# git clone
- git clone 太慢怎么办?

默认情况下, git clone 会把所有的分支 clone 下来并基于 remote head checkout 一个新的分支. 而往往我们只需要某一个分支的最新提交,可以使用以下参数来进行限定.
  - `--branch`

    checkout 特定的分支.
  - `--single-branch`

    只 clone --branch 指定的分支.默认是 master.
  - `--depth=n`

    只 clone 特定分支的最近 n 次commit

所以当我们使用下面命令的时候:
`git clone --branch dev --single-branch --depth=1 repo` 的时候,只会 clone 远程仓库 dev 分支的最近一次提交,会大大提升 clone 时间.
