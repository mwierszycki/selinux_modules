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
|`syntaxcheck`      |SUPPORTED             |
|`user`[^1]         |SUPPORTED             |
|`globalmodel`      |SUPPORTED             |
|`oldjob`           |SUPPORTED             |
|`double`           |SUPPORTED             |
|`cae`[^2]          |SUPPORTED (disabled by default) |
|`replay`[^4]       |PARTIALLY SUPPORTED   |
|`nogui`[^4]        |PARTIALLY SUPPORTED   |
|`viewer`[^2]       |SUPPORTED (disabled by default) |
|`scratch`[^3]      |SUPPORTED             |
|`fmu`              |NOT TESTED            |
|`fmuinstance`      |NOT TESTED            |
|`queue`            |NOT SUPPORTED         |
|`optimization`     |NOT SUPPORTED         |
|`python`[^4]       |PARTIALLY SUPPORTED   |
|`script`[^4]       |PARTIALLY SUPPORTED   |



[^1]: Intel OneAPI compilers with `bin_t` type
[^2]: Remote only (with `-mesa`); use `set allow_abaqus_cae true` to enable 
[^3]: Scratch dir must be labeled as `tmp_t` type
[^4]: Python interpreter is confined strictly for Abaqus solvers execution (and GUI if enabled) - many other calls are intentionally blocked
