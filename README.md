Sample Pipeline Worker
======================

This repository illustrates the structure expected for a git repository to be
used in OpenFIDO to execute a Pipeline.

Any git repository that would be executed within OpenFIDO should:

 * Be a publicly visible github project. Private repositories are not supported
   at this time.
 * Have a shell script called `openfido.sh` in the root of the project. This
   script should launch your project's particular workload.

openfido.sh
-----------

The `openfido.sh` is executed within the OpenFIDO pipelines system within a
docker container specified by the user.
 * Any input files supplied through the OpenFIDO system are stored in
   `$OPENFIDO_INPUT` for the `openfido.sh` script to access.
 * Any artifacts generated by a project should be stored in the
     `$OPENFIDO_OUTPUT` directory.
 * If the `openfido.sh` returns a non-zero system code it is considered to have 
   failed.
