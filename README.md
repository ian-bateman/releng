DEPRECATED - we're not using catalyst, but we'll leave this here for now

These scripts make use of Gentoo's catalyst (https://wiki.gentoo.org/wiki/Catalyst)
to build Gentoo stage3 releases of amd64 and i686 musl userland.  This repositoriy
is forked from https://gitweb.gentoo.org/proj/releng.git/ but contains only the scripts
for building amd64-musl-hardened and i686-musl-vanilla stages.

### Usage

If this is the first time you're running these scripts, you need to prepare a seeds
stages at the appropriate locations.  Assuming you have `storedir="/var/tmp/catalyst"`
in `/etc/catalyst/catalyst.conf` then you can proceed as follows:

```
export storedir="/var/tmp/catalyst

mkdir -p ${storedir}/builds/musl/hardened/amd64/
touch ${storedir}/builds/musl/hardened/amd64/stage{1,2}-amd64-musl-hardened.tar.bz2
curl http://distfiles.gentoo.org/experimental/amd64/musl/stage3-amd64-musl-hardened-20171204.tar.bz2 \
 > ${storedir}/builds/musl/hardened/amd64/stage3-amd64-musl-hardened.tar.bz2

mkdir -p ${storedir}/builds/musl/vanilla/i686
touch ${storedir}/builds/musl/vanilla/i686/stage{1,2}-i686-musl-vanilla.tar.bz2 
curl http://distfiles.gentoo.org/experimental/x86/musl/stage3-i686-musl-vanilla-20171204.tar.bz2 \
 > ${storedir}/builds/musl/vanilla/i686/stage3-i686-musl-vanilla.tar.bz2

```

Note that as of the writing the lastest official stage3 is 20171204.

You can then execute `run.sh`.

### Maintainers
* Anthony G. Basile <blueness@gentoo.org>
* Robin H. Johnson <robbat2@gentoo.org>
