描述 `git stash` 工作原理。

# git stash 工作原理

本质上 stash 会创建一个 commit 对象，被 `refs/stash` 引用。所有历史的 stash 通过 `logs/refs/stash` 追踪。

默认情况下，stash 只会提交跟踪文件的修改/已经在暂存区中的文件。对于未跟踪的文件不会进行提交，可以通过参数 `--include-untracked` 更改默认行为。

# git stash 操作

- 添加注释

    为了更加清晰的区分不同的 stash， 我们可以给不同的 stash 添加注释： git stash save "message"


- 查看 stash 修改内容

    git stash show [-p] stash-name # -p 查看完整的差异


- 查看所有的 stash

    git stash list


- 应用某个 stash

    git stash apply stash-name

    **apply 会保留对应的 stash，这是跟 pop 不同的地方。**

    不管是 apply 还是 pop，本质上都是执行 **merge** 操作。


- 丢弃某个 stash

    git stash drop stash-name


- 清空所有的 stash

    git stash clear