
# Processos

O comando `ps` serve para exibir os processos que estão sendo executados no momento. Lembrando que no diretório `proc` contém arquivos referentes aos processos do linux. Exemplo, para o processo de PID `1`:

````bash
[root@65ccdc0d5356 proc]# cd 1/
[root@65ccdc0d5356 1]# ls
arch_status  comm             fd         maps        ns             projid_map  smaps_rollup  task
attr         coredump_filter  fdinfo     mem         oom_adj        root        stack         timers
auxv         cpuset           gid_map    mountinfo   oom_score      sched       stat          timerslack_ns
cgroup       cwd              io         mounts      oom_score_adj  schedstat   statm         uid_map
clear_refs   environ          limits     mountstats  pagemap        setgroups   status        wchan
cmdline      exe              map_files  net         personality    smaps       syscall
````

O comando ``top`` equivale ao gerenciador de tarefas do windows
