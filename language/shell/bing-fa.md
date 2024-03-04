# 并发

## 并发&

[Shell脚本中的多任务并发执行](https://blog.51cto.com/yttitan/2409618)

> 在并发执行时不能保证命令的执行顺序
>
> 所以在并发执行时，我们通常都需要保证在循环体中的所有命令都执行完后再向后执行接下来的命令，这时就可以使用 wait命令来实现。
>
> 在Shell中使用`wait`命令，相当于其它高级语言里的多线程同步。

* 参考ping脚本执行

[What does "&" at the end of a linux command mean?](https://stackoverflow.com/questions/13338870/what-does-at-the-end-of-a-linux-command-mean)

> If a command is terminated by the control operator `&`, the shell executes the command in the background in a `subshell`.
>
> The shell does not wait for the command to finish, and `the return status is 0`.

### Wait

[How to wait in bash for several subprocesses to finish, and return exit code !=0 when any subprocess ends with code !=0?](https://stackoverflow.com/questions/356100/how-to-wait-in-bash-for-several-subprocesses-to-finish-and-return-exit-code-0) [shell wait](https://www.gnu.org/software/bash/manual/html\_node/Job-Control-Builtins.html#index-wait)

* 参考ping脚本执行
