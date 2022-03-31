# SELinux module for Abaqus
SELinux policy module for Abaqus dedicated to block a possible malicious code execution via subroutines and Python scripts e.g. in cloud services or in Abaqus/CAE jobs.

Abaqus version: 2021 GA
Distribution: Red Hat Enterprise Linux release 8.5 (Ootpa)

Still under development. Heavlly testing required. 

## Supported command

| Abaqus command    | Status               | 
|-------------------|----------------------|
|`help`             |SUPPORTED             |
|`information`      |PARTIALLY SUPPORTED   |
|`cosimulation`     |NOT TESTED            |
|`analysis`         |SUPPORTED             |
|`input`            |SUPPORTED             |
|`datacheck`        |SUPPORTED             |
|`parametercheck`   |SUPPORTED             |
|`continue`         |SUPPORTED             |
|`convert`          |NOT TESTED            |
|`recover`          |NOT TESTED            |
|`syntaxcheck`      |SUPPORTED             |
|`fil`              |NOT TESTED            |
|`cpus`             |SUPPORTED             |
|`mp_mode`          |SUPPORTED             |
|`threads_per_mpi_process`|NOT TESTED             |
|`standard_parallel`|SUPPORTED             |
|`gpus`             |NOT TESTED            |
|`memory`           |SUPPORTED             |
|`interactive`      |SUPPORTED             |
|`background`       |SUPPORTED             |
|`output_precision` |SUPPORTED             |
|`resultsformat`    |SUPPORTED             |
|`port`             |NOT TESTED            |
|`host`             |NOT TESTED            |
|`csedirector`      |NOT TESTED            |
|`csedirector`      |NOT TESTED            |
|` timeout`         |NOT TESTED            |
|`unconnected_regions`|NOT TESTED            |
|`noFlexBody`       |NOT TESTED            |
|`user`[^1]         |SUPPORTED             |
|`uniquelibs`       |NOT TESTED            |
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
