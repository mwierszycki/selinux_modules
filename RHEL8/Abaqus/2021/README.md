# SELinux module for Abaqus
SELinux policy module for Abaqus dedicated to block a possible malicious code execution via subroutines and Python scripts e.g. in cloud services or in Abaqus/CAE jobs.

Abaqus version: 2021 GA

Distribution: Red Hat Enterprise Linux release 8.5 (Ootpa)

SELinux configuration:
 - Policy: targeted
 - Policy version: 31
 - Mode: enforcing

## Status
Not for production use. Still under development. Heavy testing required.

Feedback and contribution welcome!

### Supported command

| Abaqus command    | Status               | 
|-------------------|----------------------|
|`help`             |SUPPORTED             |
|`information`      |PARTIALLY SUPPORTED   |
|`cosimulation`     |NOT TESTED            |
|`analysis`[^1]     |SUPPORTED             |
|`input`            |SUPPORTED             |
|`datacheck`[^1]    |SUPPORTED             |
|`parametercheck`   |SUPPORTED             |
|`continue`[^1]     |SUPPORTED             |
|`convert`          |NOT TESTED            |
|`recover`          |NOT TESTED            |
|`syntaxcheck`[^1]  |SUPPORTED             |
|`fil`              |NOT TESTED            |
|`cpus`             |SUPPORTED             |
|`mp_mode`          |SUPPORTED             |
|`threads_per_mpi_process`|NOT TESTED             |
|`parallel`         |SUPPORTED             |
|`domains`          |NOT TESTED            |
|`dynamic_load_balancing`|NOT TESTED            |
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
|`timeout`          |NOT TESTED            |
|`unconnected_regions`|NOT TESTED            |
|`noFlexBody`       |NOT TESTED            |
|`user`[^2]         |SUPPORTED             |
|`globalmodel`      |SUPPORTED             |
|`oldjob`           |SUPPORTED             |
|`double`           |SUPPORTED             |
|`cae`[^1][^3]      |SUPPORTED (disabled by default) |
|`replay`[^5]       |PARTIALLY SUPPORTED   |
|`nogui`[^5]        |PARTIALLY SUPPORTED   |
|`viewer`[^1][^3]   |SUPPORTED (disabled by default) |
|`scratch`[^4]      |SUPPORTED             |
|`fmu`              |NOT TESTED            |
|`fmuinstance`      |NOT TESTED            |
|`queue`            |NOT SUPPORTED         |
|`optimization`     |NOT SUPPORTED         |
|`python`[^5]       |PARTIALLY SUPPORTED   |
|`script`[^5]       |PARTIALLY SUPPORTED   |
|`make library`[^1][^2][^6] |SUPPORTED             |
|`make job`         |NOT TESTED            |
|`uniquelibs`[^1][^2][^6]   |SUPPORTED             |
|`sim_version`      |SUPPORTED             |
|`odb2sim`[^1]          |SUPPORTED             |
|`odbreport`[^1]        |SUPPORTED             |
|`restartjoin`[^1]      |SUPPORTED             |

[^1]: Working dir must be labeled as `abaqus_job_dir_t` type
[^2]: Intel OneAPI compilers labeled as `bin_t` type
[^3]: Remote only (with `-mesa`); use `set allow_abaqus_cae true` to enable 
[^4]: Scratch dir must be labeled as `tmp_t` type
[^5]: Python interpreter is confined strictly for Abaqus solvers execution (and GUI if enabled) - many other calls are intentionally blocked
[^6]: `usub_lib_dir` must be labeled as `abaqus_user_lib_dir_t` type
