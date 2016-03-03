# Change Log

## [Unreleased]
### Added
- onstart handler, that allows to add code that shall be only executed before the actual workflow execution (not on dryrun).
### Changed
- Allow to use rule/job parameters with braces notation in cluster config.
- Show a proper error message in case of recursion errors.
- Remove non-empty temp dirs.
- Don't set the process group of Snakemake in order to allow kill signals from parent processes to be propagated.

## [3.5.5] - 2016-01-23
### Added
- New experimental wrapper directive, which allows to refer to re-usable [wrapper scripts](https://bitbucket.org/snakemake/snakemake/wiki/Documentation#markdown-header-wrappers). Wrappers are provided in the [Snakemake Wrapper Repository](https://bitbucket.org/snakemake/snakemake-wrappers).
- David Koppstein implemented two new command line options to constrain the execution of the DAG of job to sub-DAGs (--until and --omit-from).
### Changed
- Fixed various bugs, e.g. with shadow jobs and --latency-wait.

## [3.5.4] - 2015-12-04
### Changed
- The params directive now fully supports non-string parameters. Several bugs in the remote support were fixed.

## [3.5.3] - 2015-11-24
### Changed
- The missing remote module was added to the package.

## [3.5.2] - 2015-11-24
### Added
- Support for easy integration of external R and Python scripts via the new [script directive](https://bitbucket.org/snakemake/snakemake/wiki/Documentation#markdown-header-external-scripts).
- Chris Tomkins-Tinch has implemented support for remote files: Snakemake can now handle input and output files from Amazon S3, Google Storage, FTP, SFTP, HTTP and Dropbox.
- Simon Ye has implemented support for sandboxing jobs with [shadow rules](https://bitbucket.org/snakemake/snakemake/wiki/Documentation#markdown-header-shadow-rules).
### Changed
- Manuel Holtgrewe has fixed dynamic output files in combination with mutliple wildcards.
- It is now possible to add suffixes to all shell commands with shell.suffix("mysuffix").
- Job execution has been refactored to spawn processes only when necessary, resolving several problems in combination with huge workflows consisting of thousands of jobs and reducing the memory footprint.
- In order to reflect the new collaborative development model, Snakemake has moved from my personal bitbucket account to http://snakemake.bitbucket.org.

## [3.4.2] - 2015-09-12
### Changed
- Willem Ligtenberg has reduced the memory usage of Snakemake.
- Per Unneberg has improved config file handling to provide a more intuitive overwrite behavior.
- Simon Ye has improved the test suite of Snakemake and helped with setting up continuous integration via Codeship.
- The cluster implementation has been rewritten to use only a single thread to wait for jobs. This avoids failures with large numbers of jobs.
- Benchmarks are now writing tab-delimited text files instead of JSON.
- Snakemake now always requires to set the number of jobs with -j when in cluster mode. Set this to a high value if your cluster does not have restrictions.
- The Snakemake Conda package has been moved to the bioconda channel.
- The handling of Symlinks was improved, which made a switch to Python 3.3 as the minimum required Python version necessary.

## [3.4.1] - 2015-08-05
### Changed
- This release fixes a bug that caused named input or output files to always be returned as lists instead of single files.

## [3.4] - 2015-07-18
### Added
- This release adds support for executing jobs on clusters in synchronous mode (e.g. qsub -sync). Thanks to David Alexander for implementing this.
- There is now vim syntax highlighting support (thanks to Jay Hesselberth).
- Snakemake is now available as Conda package.
### Changed
- Lots of bugs have been fixed. Thanks go to e.g. David Koppstein, Marcel Martin, John Huddleston and Tao Wen for helping with useful reports and debugging.

See [here](https://bitbucket.org/snakemake/snakemake/wiki/News-Archive) for older changes.