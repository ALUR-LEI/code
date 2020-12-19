Allodial Land Use Registry (ALUR) is an open source
software system being a customisation of the FAO SOLA Community Server software 
(https://github.com/OpenTenure). The customisation was undertaken by
Land Equity Internation working with the United Treaty Council.
For more information refer to www.alur.world 

ALUR uses 7 Git repositories for managing its code base. These
repositories are:

1) code      - This repository. Contains the Main POM file and
               additional supporting files. This Git repository acts
               as the super/parent repositories for all the other ALUR
               Git repositories. 
2) common    - Contains only the Common Utilities project. Attached as
               the common/common subdirectory of the code repository. 
3) messaging - Contains only the Common Messaging project. Attached as
               the common/messaging subdirectory of the code
               repository. 
4) boundary  - Contains the Web Service Boundary projects. Attached as
               the services/boundary subdirectory of the code
               repository. 
5) services  - Conatins the EJB and common service projects. Attached
               as the services subdirectory of the code repository.
6) database - Contains the ALUR sola database creation scripts. Attached relative
               to the code repository in the ../database directory.
7) docker   - Contains the dockerfiles and docker-compose and other files
              associated with installing ALUR usind Docker

Each repository can be managed independently, although when a change
spans more than one repository, ensuring the changes remain
synchronized across the repositories can be difficult. Also tasks such
as pushing and pulling from GitHub can be extremely repetitive as they
may need to be done up to 10 times (once for each repository). Git does
not provide any really good tools for managing multiple repositories as
one. To effectively manage git command across multiple ALUR Git
repositories, the gits (Git Slave) script can be used. This script can
issue a git command to all nested/slave repositories and is particularly
useful for committing changes and pushing and pulling from the GitHub
repositories. 

The gits script has been included in the root folder of the code
repository. To use gits, open the Git Bash Shell and cd to the root of
the code repository. At the prompt type gits <any git command> to issue
a git command that will apply to the super repository and all slave
repositories.
