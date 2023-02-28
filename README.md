# THIS PROJECT HAS BEEN ARCHIVED
## This is due to 
### - the transition to the pot container management project - https://github.com/bsdpot/pot
### - lack of development on focker althogether

# fockerfiles

fockerfiles for all your favorite projects

# !IMPORTANT NOTICE!
All fockerfile in this repository use **HardenedBSD** as the base image distro. 
This also means that all fockerfiles are deisgned and tested on HardenedBSD.
It is **reccomended** to use HardenedBSD for maximum compatibility and support for other OS's is **limited**.

## To change the base image distro Manually (Reccomended)
1. Clone the Focker Repository
```
git clone https://github.com/sadaszewski/focker
```
2. Edit the `scripts/focker-mirrorselect` file
```
cd focker
ee scripts/focker-mirrorselect
```
3. Find the line `BSDINSTALL_DISTSITE` and comment it out
```
# It should look like this
# BSDINSTALL_DISTSITE="$MIRROR/pub/FreeBSD/${RELDIR}/`uname -m`/`uname -p`/${_UNAME_R}"```
```
4. Add the HardenedBSD download repo above `export BSDINSTALL_DISTSITE`
```
# It should look like this
# BSDINSTALL_DISTSITE="$MIRROR/pub/FreeBSD/${RELDIR}/`uname -m`/`uname -p`/${_UNAME_R}"
BSDINSTALL_DISTSITE="https://ci-01.nyi.hardenedbsd.org/pub/hardenedbsd/13-stable/amd64/amd64/BUILD-LATEST/"
export BSDINSTALL_DISTSITE
```
5. Follow the focker install as normal

## To change the base image distro automatically
Instead of installing focker using sadaszewski's repo use `https://github.com/t2v/focker`.
```
pip install git+https://github.com/t2v/focker.git
```
This is not reccomended as my repository is not always updated.