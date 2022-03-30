# SELinux module for Abaqus
SELinux policy module for Abauqs solvers

| Abaqus command    | Status               | 
|-------------------|----------------------|
|`help`             |SUPPORTED             |
|`information`      |PARTIALLY SUPPORTED   |
|`cosimulation`     |NOT TESTED            |
|`analysis`         |SUPPORTED             |
|`datacheck`        |SUPPORTED             |
|`parametercheck`   |SUPPORTED             |
|`continue`         |SUPPORTED             |
|`convert`          |NOT TESTED            |
|`recover`          |NOT TESTED            |
|`syntaxcheck`      |NOT TESTED            |
|`user`[^1]         |SUPPORTED             |
|`cae`[^2]          |SUPPORTED             |
|`viewer`[^2]       |SUPPORTED             |

[^1]: Intel OneAPI compilers with bin_t type
[^2]: Remote only (with -mesa)
