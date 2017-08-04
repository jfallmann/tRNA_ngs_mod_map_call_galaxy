# tRNA\_ngs\_mod\_map\_call\_galaxy
##Tool collection for identification of tRNA modifications from NGS data galaxy workflow

This git repo contains a collection of tools and
[galaxy](https://galaxyproject.org/) wrappers for the
[tRNA read mapping workflow](https://github.com/AnneHoffmann/tRNA-read-mapping)
which can either be run from commandline or in galaxy.

*Requires a local installation of gatk in version 3.6-0.*
Just install gatk and link the GenomeAnalysisTK.jar to this directory.

Due to this dependency and the corresponding issues with licensing,
this tool collection is not part of the galaxy toolshed.  This may
change in the future, due to the open source license for GATK4.

Meanwhile, just clone this repository, link the GenomeAnalysisTK.jar
executable into the tools directory and add the tools to your galaxy
instance.

To run this workflow you must also install the tRNA\_prediction tool
from the
[galaxy toolshed](https://toolshed.g2.bx.psu.edu/view/bgruening/trna_prediction/358f58401cd6)
and resolve all tool depencies.

In case you are using a docker image of galaxy, make sure that this
directory is exported to galaxy and create a mytools.xml file, a file
mytools.xml.example is part of this repo.

##A docker run example could look like this:
```docker run -d -p 8080:80 -p 8021:21 -p 8800:8800 --privileged=true -v ${PATHtoStorage}/galaxy_storage/:/export/ -v ${PATHtoGits}/tRNA_ngs_mod_map_call_galaxy/:/tRNA_mods -e GALAXY_CONFIG_TOOL_CONFIG_FILE=config/tool_conf.xml,config/shed_tool_conf.xml,/tRNA_mods/mytools.xml ${dockerimageID}```

More information on how to include custom tools in galaxy can be found
at the official galaxy documents,
e.g. [here](https://galaxyproject.org/admin/tools/add-tool-tutorial/).
