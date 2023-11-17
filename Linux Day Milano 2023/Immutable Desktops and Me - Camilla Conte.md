# Immutable Desktops and Me

## Links

https://fedoraproject.org/silverblue/
https://ubuntu.com/blog/ubuntu-core-an-immutable-linux-desktop
https://docs.fedoraproject.org/en-US/fedora-silverblue/faq/#_about_using_fedora_silverblue
https://docs.fedoraproject.org/en-US/fedora-silverblue/toolbox/
https://github.com/owtaylor/toolbox-vscode
https://docs.flatpak.org/en/latest/first-build.html
https://github.com/castrojo/awesome-immutable

## Output del terminale

```bash
[tofu@pinkpad ~]$ ls
Android                code     Documents  maint  Pictures  rpmbuild          Sync       Videos
AndroidStudioProjects  Desktop  Downloads  Music  Public    rpt-personal.cfg  Templates
[tofu@pinkpad ~]$ dnf
bash: dnf: command not found
[tofu@pinkpad ~]$ toolbox 
Error: missing command

create    Create a new toolbox container
enter     Enter an existing toolbox container
list      List all existing toolbox containers and images

Run 'toolbox --help' for usage.
[tofu@pinkpad ~]$ toolbox list 
IMAGE ID      IMAGE NAME                                              CREATED
63bae3bc7ad4  localhost/virt-maint-toolbox:latest                     2 months ago
1f47fa078bc3  quay.io/rhel-devel-tools/rhel-developer-toolbox:latest  2 months ago
997b52ccbf85  registry.fedoraproject.org/fedora-toolbox:38            6 months ago
997b52ccbf85  registry.fedoraproject.org/fedora-toolbox:latest        6 months ago

CONTAINER ID  CONTAINER NAME          CREATED       STATUS   IMAGE NAME
8ffba88d4f86  fedora-toolbox-38       2 months ago  created  registry.fedoraproject.org/fedora-toolbox:38
2caa62338afd  rhel-developer-toolbox  2 months ago  created  quay.io/rhel-devel-tools/rhel-developer-toolbox:latest
100a6cb2be3b  virt-maint-toolbox      7 weeks ago   exited   localhost/virt-maint-toolbox:latest
[tofu@pinkpad ~]$ toolbox enter fedora-toolbox-38 
⬢[tofu@toolbox ~]$ 
⬢[tofu@toolbox ~]$ dnf
usage: dnf [options] COMMAND

List of Main Commands:

alias                     List or create command aliases
autoremove                remove all unneeded packages that were originally installed as dependencies
check                     check for problems in the packagedb
check-update              check for available package upgrades
clean                     remove cached data
deplist                   [deprecated, use repoquery --deplist] List package's dependencies and what packages provide them
distro-sync               synchronize installed packages to the latest available versions
downgrade                 Downgrade a package
group                     display, or use, the groups information
help                      display a helpful usage message
history                   display, or use, the transaction history
info                      display details about a package or group of packages
install                   install a package or packages on your system
list                      list a package or groups of packages
makecache                 generate the metadata cache
mark                      mark or unmark installed packages as installed by user.
module                    Interact with Modules.
provides                  find what package provides the given value
reinstall                 reinstall a package
remove                    remove a package or packages from your system
repolist                  display the configured software repositories
repoquery                 search for packages matching keyword
repository-packages       run commands on top of all packages in given repository
search                    search package details for the given string
shell                     run an interactive DNF shell
swap                      run an interactive DNF mod for remove and install one spec
updateinfo                display advisories about packages
upgrade                   upgrade a package or packages on your system
upgrade-minimal           upgrade, but only 'newest' package match which fixes a problem that affects your system

List of Plugin Commands:

builddep                  Install build dependencies for package or spec file
changelog                 Show changelog data of packages
config-manager            manage dnf configuration options and repositories
copr                      Interact with Copr repositories.
debug-dump                dump information about installed rpm packages to file
debug-restore             restore packages recorded in debug-dump file
debuginfo-install         install debuginfo packages
download                  Download package to current directory
groups-manager            create and edit groups metadata file
needs-restarting          determine updated binaries that need restarting
offline-distrosync        Prepare offline distrosync of the system
offline-upgrade           Prepare offline upgrade of the system
playground                Interact with Playground repository.
repoclosure               Display a list of unresolved dependencies for repositories
repodiff                  List differences between two sets of repositories
repograph                 Output a full package dependency graph in dot format
repomanage                Manage a directory of rpm packages
reposync                  download all packages from remote repo
system-upgrade            Prepare system for upgrade to a new release

General DNF options:
  -c [config file], --config [config file]
                        config file location
  -q, --quiet           quiet operation
  -v, --verbose         verbose operation
  --version             show DNF version and exit
  --installroot [path]  set install root
  --nodocs              do not install documentations
  --noplugins           disable all plugins
  --enableplugin [plugin]
                        enable plugins by name
  --disableplugin [plugin]
                        disable plugins by name
  --releasever RELEASEVER
                        override the value of $releasever in config and repo files
  --setopt SETOPTS      set arbitrary config and repo options
  --skip-broken         resolve depsolve problems by skipping packages
  -h, --help, --help-cmd
                        show command help
  --allowerasing        allow erasing of installed packages to resolve dependencies
  -b, --best            try the best available package versions in transactions.
  --nobest              do not limit the transaction to the best candidate
  -C, --cacheonly       run entirely from system cache, don't update cache
  -R [minutes], --randomwait [minutes]
                        maximum command wait time
  -d [debug level], --debuglevel [debug level]
                        debugging output level
  --debugsolver         dumps detailed solving results into files
  --showduplicates      show duplicates, in repos, in list/search commands
  -e ERRORLEVEL, --errorlevel ERRORLEVEL
                        error output level
  --obsoletes           enables dnf's obsoletes processing logic for upgrade or display
                        capabilities that the package obsoletes for info, list and repoquery
  --rpmverbosity [debug level name]
                        debugging output level for rpm
  -y, --assumeyes       automatically answer yes for all questions
  --assumeno            automatically answer no for all questions
  --enablerepo [repo]   Temporarily enable repositories for the purpose of the current dnf
                        command. Accepts an id, a comma-separated list of ids, or a glob of ids.
                        This option can be specified multiple times.
  --disablerepo [repo]  Temporarily disable active repositories for the purpose of the current dnf
                        command. Accepts an id, a comma-separated list of ids, or a glob of ids.
                        This option can be specified multiple times, but is mutually exclusive
                        with `--repo`.
  --repo [repo], --repoid [repo]
                        enable just specific repositories by an id or a glob, can be specified
                        multiple times
  --enable              enable repos with config-manager command (automatically saves)
  --disable             disable repos with config-manager command (automatically saves)
  -x [package], --exclude [package], --excludepkgs [package]
                        exclude packages by name or glob
  --disableexcludes [repo], --disableexcludepkgs [repo]
                        disable excludepkgs
  --repofrompath [repo,path]
                        label and path to an additional repository to use (same path as in a
                        baseurl), can be specified multiple times.
  --noautoremove        disable removal of dependencies that are no longer used
  --nogpgcheck          disable gpg signature checking (if RPM policy allows)
  --color COLOR         control whether color is used
  --refresh             set metadata as expired before running the command
  -4                    resolve to IPv4 addresses only
  -6                    resolve to IPv6 addresses only
  --destdir DESTDIR, --downloaddir DESTDIR
                        set directory to copy packages to
  --downloadonly        only download packages
  --comment COMMENT     add a comment to transaction
  --bugfix              Include bugfix relevant packages, in updates
  --enhancement         Include enhancement relevant packages, in updates
  --newpackage          Include newpackage relevant packages, in updates
  --security            Include security relevant packages, in updates
  --advisory ADVISORY, --advisories ADVISORY
                        Include packages needed to fix the given advisory, in updates
  --bz BUGZILLA, --bzs BUGZILLA
                        Include packages needed to fix the given BZ, in updates
  --cve CVES, --cves CVES
                        Include packages needed to fix the given CVE, in updates
  --sec-severity {Critical,Important,Moderate,Low}, --secseverity {Critical,Important,Moderate,Low}
                        Include security relevant packages matching the severity, in updates
  --forcearch ARCH      Force the use of an architecture
⬢[tofu@toolbox ~]$ ls code/
adviser           gitlab-private-namespace   rpt            virt-maint-container
backport-bot      gitlab-projects            sig-guide      virt-maint-toolbox
build-automation  gitlab-terraform-qemu-kvm  subtree-bot    virt-maint-tools
cami-suite        gitlab-triage-policies     tektoncd       virt-sig-docs
distro-scripts    glab                       tekton-runner
fastbook          rabbitmq-to-http           toolbox-demo
⬢[tofu@toolbox ~]$ cd code/fastbook/
⬢[tofu@toolbox fastbook]$ code 
⬢[tofu@toolbox fastbook]$ code .
⬢[tofu@toolbox fastbook]$ cd
⬢[tofu@toolbox ~]$ cd code/
⬢[tofu@toolbox code]$ mkdir flatpak-linux-day
⬢[tofu@toolbox code]$ cd flatpak-linux-day/
⬢[tofu@toolbox flatpak-linux-day]$ 
⬢[tofu@toolbox flatpak-linux-day]$ sudo dnf install flatpak
Fedora 38 - x86_64                                                   19 kB/s |  21 kB     00:01    
Fedora Modular 38 - x86_64                                           48 kB/s |  21 kB     00:00    
Fedora 38 - x86_64 - Updates                                         19 kB/s |  18 kB     00:00    
Fedora 38 - x86_64 - Updates                                        1.5 MB/s | 5.3 MB     00:03    
Fedora Modular 38 - x86_64 - Updates                                 27 kB/s |  19 kB     00:00    
Dependencies resolved.
====================================================================================================
 Package                          Architecture     Version                  Repository         Size
====================================================================================================
Installing:
 flatpak                          x86_64           1.15.4-1.fc38            fedora            1.6 M
Installing dependencies:
 appstream                        x86_64           0.16.1-1.fc38            fedora            723 k
 appstream-data                   noarch           38-6.fc38                updates            13 M
 bubblewrap                       x86_64           0.7.0-1.fc38             fedora             60 k
 flatpak-selinux                  noarch           1.15.4-1.fc38            fedora             22 k
 flatpak-session-helper           x86_64           1.15.4-1.fc38            fedora             44 k
 librsvg2                         x86_64           2.56.3-1.fc38            updates           1.6 M
 libxmlb                          x86_64           0.3.14-1.fc38            updates           117 k
 malcontent-libs                  x86_64           0.11.1-1.fc38            fedora             46 k
 ostree-libs                      x86_64           2023.6-1.fc38            updates           460 k
 xdg-dbus-proxy                   x86_64           0.1.4-2.fc38             updates            42 k
Installing weak dependencies:
 p11-kit-server                   x86_64           0.24.1-6.fc38            fedora            192 k

Transaction Summary
====================================================================================================
Install  12 Packages

Total download size: 18 M
Installed size: 30 M
Is this ok [y/N]: y
Downloading Packages:
(1/12): bubblewrap-0.7.0-1.fc38.x86_64.rpm                          124 kB/s |  60 kB     00:00    
(2/12): flatpak-selinux-1.15.4-1.fc38.noarch.rpm                    161 kB/s |  22 kB     00:00    
(3/12): flatpak-session-helper-1.15.4-1.fc38.x86_64.rpm             241 kB/s |  44 kB     00:00    
(4/12): malcontent-libs-0.11.1-1.fc38.x86_64.rpm                    247 kB/s |  46 kB     00:00    
(5/12): flatpak-1.15.4-1.fc38.x86_64.rpm                            1.5 MB/s | 1.6 MB     00:01    
(6/12): appstream-0.16.1-1.fc38.x86_64.rpm                          662 kB/s | 723 kB     00:01    
(7/12): p11-kit-server-0.24.1-6.fc38.x86_64.rpm                     1.0 MB/s | 192 kB     00:00    
(8/12): librsvg2-2.56.3-1.fc38.x86_64.rpm                           1.4 MB/s | 1.6 MB     00:01    
(9/12): libxmlb-0.3.14-1.fc38.x86_64.rpm                            111 kB/s | 117 kB     00:01    
(10/12): xdg-dbus-proxy-0.1.4-2.fc38.x86_64.rpm                     389 kB/s |  42 kB     00:00    
(11/12): ostree-libs-2023.6-1.fc38.x86_64.rpm                       1.2 MB/s | 460 kB     00:00    
(12/12): appstream-data-38-6.fc38.noarch.rpm                        1.4 MB/s |  13 MB     00:09    
----------------------------------------------------------------------------------------------------
Total                                                               1.5 MB/s |  18 MB     00:11     
Running transaction check
Transaction check succeeded.
Running transaction test
Transaction test succeeded.
Running transaction
  Preparing        :                                                                            1/1 
  Installing       : xdg-dbus-proxy-0.1.4-2.fc38.x86_64                                        1/12 
  Installing       : ostree-libs-2023.6-1.fc38.x86_64                                          2/12 
  Installing       : libxmlb-0.3.14-1.fc38.x86_64                                              3/12 
  Installing       : librsvg2-2.56.3-1.fc38.x86_64                                             4/12 
  Installing       : appstream-data-38-6.fc38.noarch                                           5/12 
  Installing       : appstream-0.16.1-1.fc38.x86_64                                            6/12 
  Installing       : p11-kit-server-0.24.1-6.fc38.x86_64                                       7/12 
  Installing       : malcontent-libs-0.11.1-1.fc38.x86_64                                      8/12 
  Installing       : flatpak-session-helper-1.15.4-1.fc38.x86_64                               9/12 
  Installing       : flatpak-selinux-1.15.4-1.fc38.noarch                                     10/12 
  Running scriptlet: flatpak-selinux-1.15.4-1.fc38.noarch                                     10/12 
  Installing       : bubblewrap-0.7.0-1.fc38.x86_64                                           11/12 
  Running scriptlet: flatpak-1.15.4-1.fc38.x86_64                                             12/12 
  Installing       : flatpak-1.15.4-1.fc38.x86_64                                             12/12 
  Running scriptlet: flatpak-1.15.4-1.fc38.x86_64                                             12/12 
Failed to preset unit: Access denied

  Running scriptlet: appstream-0.16.1-1.fc38.x86_64                                           12/12 
  Running scriptlet: flatpak-1.15.4-1.fc38.x86_64                                             12/12 
Failed to reload daemon: Access denied

Failed to start transient service unit: Connection reset by peer
Failed to reload daemon: Transport endpoint is not connected
Failed to start transient service unit: Connection reset by peer
Failed to start jobs: Transport endpoint is not connected

  Verifying        : appstream-0.16.1-1.fc38.x86_64                                            1/12 
  Verifying        : bubblewrap-0.7.0-1.fc38.x86_64                                            2/12 
  Verifying        : flatpak-1.15.4-1.fc38.x86_64                                              3/12 
  Verifying        : flatpak-selinux-1.15.4-1.fc38.noarch                                      4/12 
  Verifying        : flatpak-session-helper-1.15.4-1.fc38.x86_64                               5/12 
  Verifying        : malcontent-libs-0.11.1-1.fc38.x86_64                                      6/12 
  Verifying        : p11-kit-server-0.24.1-6.fc38.x86_64                                       7/12 
  Verifying        : appstream-data-38-6.fc38.noarch                                           8/12 
  Verifying        : librsvg2-2.56.3-1.fc38.x86_64                                             9/12 
  Verifying        : libxmlb-0.3.14-1.fc38.x86_64                                             10/12 
  Verifying        : ostree-libs-2023.6-1.fc38.x86_64                                         11/12 
  Verifying        : xdg-dbus-proxy-0.1.4-2.fc38.x86_64                                       12/12 

Installed:
  appstream-0.16.1-1.fc38.x86_64                appstream-data-38-6.fc38.noarch                     
  bubblewrap-0.7.0-1.fc38.x86_64                flatpak-1.15.4-1.fc38.x86_64                        
  flatpak-selinux-1.15.4-1.fc38.noarch          flatpak-session-helper-1.15.4-1.fc38.x86_64         
  librsvg2-2.56.3-1.fc38.x86_64                 libxmlb-0.3.14-1.fc38.x86_64                        
  malcontent-libs-0.11.1-1.fc38.x86_64          ostree-libs-2023.6-1.fc38.x86_64                    
  p11-kit-server-0.24.1-6.fc38.x86_64           xdg-dbus-proxy-0.1.4-2.fc38.x86_64                  

Complete!
⬢[tofu@toolbox flatpak-linux-day]$ flatpak install flathub org.freedesktop.Platform//23.08 org.freedesktop.Sdk//23.08
Looking for matches…
Skipping: org.freedesktop.Platform/x86_64/23.08 is already installed


        ID                                Branch       Op       Remote        Download
 1. [✓] org.freedesktop.Sdk.Locale        23.08        i        flathub        18.2 kB / 361.7 MB
 2. [✓] org.freedesktop.Sdk               23.08        i        flathub       378.2 MB / 554.8 MB

Installation complete.
⬢[tofu@toolbox flatpak-linux-day]$ ls
⬢[tofu@toolbox flatpak-linux-day]$ vi hello.sh
⬢[tofu@toolbox flatpak-linux-day]$ . hello.sh 
Ciao ciao pinguini!
⬢[tofu@toolbox flatpak-linux-day]$ code .
⬢[tofu@toolbox flatpak-linux-day]$ 
⬢[tofu@toolbox flatpak-linux-day]$ vi org.flatpak.Hello.yml
⬢[tofu@toolbox flatpak-linux-day]$ flatpak-builder build-dir org.flatpak.Hello.yml
bash: flatpak-builder: command not found
⬢[tofu@toolbox flatpak-linux-day]$ dnf install flatpak-builder
Error: This command has to be run with superuser privileges (under the root user on most systems).
⬢[tofu@toolbox flatpak-linux-day]$ sudo dnf install flatpak-builder
Last metadata expiration check: 0:07:15 ago on Sat 28 Oct 2023 09:00:55 AM +01.
Dependencies resolved.
=========================================================================================================
 Package                      Architecture        Version                     Repository            Size
=========================================================================================================
Installing:
 flatpak-builder              x86_64              1.3.3-1.fc38                fedora               217 k
Installing dependencies:
 debugedit                    x86_64              5.0-9.fc38                  updates               78 k
 dwz                          x86_64              0.15-2.fc38                 fedora               135 k
 ed                           x86_64              1.19-2.fc38                 fedora                78 k
 elfutils                     x86_64              0.189-1.fc38                fedora               536 k
 gdb-minimal                  x86_64              13.2-6.fc38                 updates              4.2 M
 hiredis                      x86_64              1.0.2-4.fc38                fedora                42 k
 ostree                       x86_64              2023.6-1.fc38               updates              263 k
Installing weak dependencies:
 ccache                       x86_64              4.7.4-1.fc38                fedora               627 k
 patch                        x86_64              2.7.6-19.fc38               fedora               126 k

Transaction Summary
=========================================================================================================
Install  10 Packages

Total download size: 6.2 M
Installed size: 19 M
Is this ok [y/N]: y
Downloading Packages:
(1/10): ed-1.19-2.fc38.x86_64.rpm                                        127 kB/s |  78 kB     00:00    
(2/10): ccache-4.7.4-1.fc38.x86_64.rpm                                   722 kB/s | 627 kB     00:00    
(3/10): dwz-0.15-2.fc38.x86_64.rpm                                       143 kB/s | 135 kB     00:00    
(4/10): elfutils-0.189-1.fc38.x86_64.rpm                                 1.5 MB/s | 536 kB     00:00    
(5/10): flatpak-builder-1.3.3-1.fc38.x86_64.rpm                          1.0 MB/s | 217 kB     00:00    
(6/10): hiredis-1.0.2-4.fc38.x86_64.rpm                                  278 kB/s |  42 kB     00:00    
(7/10): patch-2.7.6-19.fc38.x86_64.rpm                                   611 kB/s | 126 kB     00:00    
(8/10): debugedit-5.0-9.fc38.x86_64.rpm                                  225 kB/s |  78 kB     00:00    
(9/10): ostree-2023.6-1.fc38.x86_64.rpm                                  504 kB/s | 263 kB     00:00    
(10/10): gdb-minimal-13.2-6.fc38.x86_64.rpm                              2.7 MB/s | 4.2 MB     00:01    
---------------------------------------------------------------------------------------------------------
Total                                                                    1.0 MB/s | 6.2 MB     00:06     
Running transaction check
Transaction check succeeded.
Running transaction test
Transaction test succeeded.
Running transaction
  Preparing        :                                                                                 1/1 
  Installing       : elfutils-0.189-1.fc38.x86_64                                                   1/10 
  Installing       : ostree-2023.6-1.fc38.x86_64                                                    2/10 
  Running scriptlet: ostree-2023.6-1.fc38.x86_64                                                    2/10 
Failed to preset unit: Access denied

  Installing       : gdb-minimal-13.2-6.fc38.x86_64                                                 3/10 
  Installing       : hiredis-1.0.2-4.fc38.x86_64                                                    4/10 
  Running scriptlet: ccache-4.7.4-1.fc38.x86_64                                                     5/10 
  Installing       : ccache-4.7.4-1.fc38.x86_64                                                     5/10 
  Installing       : ed-1.19-2.fc38.x86_64                                                          6/10 
  Installing       : patch-2.7.6-19.fc38.x86_64                                                     7/10 
  Installing       : dwz-0.15-2.fc38.x86_64                                                         8/10 
  Installing       : debugedit-5.0-9.fc38.x86_64                                                    9/10 
  Installing       : flatpak-builder-1.3.3-1.fc38.x86_64                                           10/10 
  Running scriptlet: flatpak-builder-1.3.3-1.fc38.x86_64                                           10/10 
"/home" already exists and is not a directory.
fchownat() of /run/systemd/sessions failed: Operation not permitted
fchownat() of /run/systemd/users failed: Operation not permitted
fchownat() of /var/lib/systemd/coredump failed: Read-only file system
fchownat() of /tmp failed: Operation not permitted
Setting access ACL "u::rwx,g::r-x,g:adm:r-x,g:wheel:r-x,g:4294967295:r-x,g:4294967295:r-x,m::r-x,o::r-x" on /var/log/journal failed: Read-only file system
Failed to re-open '/var/log/journal': Operation not permitted
fchownat() of /var/log/journal failed: Read-only file system
Setting access ACL "u::rwx,g::r-x,g:adm:r-x,g:wheel:r-x,g:4294967295:r-x,g:4294967295:r-x,m::r-x,o::r-x" on /var/log/journal/4c5e7083f47a469cae00afe65c75396f failed: Read-only file system
Failed to re-open '/var/log/journal/4c5e7083f47a469cae00afe65c75396f': Operation not permitted
fchownat() of /var/log/journal/4c5e7083f47a469cae00afe65c75396f failed: Read-only file system
fchownat() of /dev/snd/seq failed: Operation not permitted
fchownat() of /dev/snd/timer failed: Operation not permitted
fchownat() of /dev/loop-control failed: Operation not permitted
fchownat() of /dev/kvm failed: Operation not permitted
fchownat() of /dev/vhost-net failed: Operation not permitted
fchownat() of /dev/vhost-vsock failed: Operation not permitted
Setting access ACL "u::rw-,g::r-x,g:adm:r--,g:wheel:r--,g:4294967295:r-x,g:4294967295:r-x,m::r--,o::---" on /var/log/journal/4c5e7083f47a469cae00afe65c75396f/system.journal failed: Read-only file system
fchownat() of /var/log/journal/4c5e7083f47a469cae00afe65c75396f/system.journal failed: Read-only file system
fchownat() of /sys/kernel/security/tpm0/binary_bios_measurements failed: Operation not permitted
fchownat() of /sys/kernel/security/ima/binary_runtime_measurements failed: Operation not permitted

Failed to reload daemon: Access denied

  Verifying        : ccache-4.7.4-1.fc38.x86_64                                                     1/10 
  Verifying        : dwz-0.15-2.fc38.x86_64                                                         2/10 
  Verifying        : ed-1.19-2.fc38.x86_64                                                          3/10 
  Verifying        : elfutils-0.189-1.fc38.x86_64                                                   4/10 
  Verifying        : flatpak-builder-1.3.3-1.fc38.x86_64                                            5/10 
  Verifying        : hiredis-1.0.2-4.fc38.x86_64                                                    6/10 
  Verifying        : patch-2.7.6-19.fc38.x86_64                                                     7/10 
  Verifying        : debugedit-5.0-9.fc38.x86_64                                                    8/10 
  Verifying        : gdb-minimal-13.2-6.fc38.x86_64                                                 9/10 
  Verifying        : ostree-2023.6-1.fc38.x86_64                                                   10/10 

Installed:
  ccache-4.7.4-1.fc38.x86_64       debugedit-5.0-9.fc38.x86_64    dwz-0.15-2.fc38.x86_64               
  ed-1.19-2.fc38.x86_64            elfutils-0.189-1.fc38.x86_64   flatpak-builder-1.3.3-1.fc38.x86_64  
  gdb-minimal-13.2-6.fc38.x86_64   hiredis-1.0.2-4.fc38.x86_64    ostree-2023.6-1.fc38.x86_64          
  patch-2.7.6-19.fc38.x86_64      

Complete!
⬢[tofu@toolbox flatpak-linux-day]$ flatpak-builder build-dir org.flatpak.Hello.yml
Downloading sources
Initializing build dir
Committing stage init to cache
Starting build of org.flatpak.Hello
========================================================================
Building module hello in /var/home/tofu/code/flatpak-linux-day/.flatpak-builder/build/hello-1
========================================================================
Running: install -D hello.sh /app/bin/hello.sh
Committing stage build-hello to cache
Cleaning up
Committing stage cleanup to cache
Finishing app
Please review the exported files and the metadata
Committing stage finish to cache
Pruning cache
⬢[tofu@toolbox flatpak-linux-day]$ flatpak-builder --user --install --force-clean build-dir org.flatpak.Hello.yml
Emptying app dir 'build-dir'
Downloading sources
Starting build of org.flatpak.Hello
Cache hit for hello, skipping build
Cache hit for cleanup, skipping
Cache hit for finish, skipping
Everything cached, checking out from cache
Exporting org.flatpak.Hello to repo
Commit: c2de1aa1d19e85d65a6d325d01aaa532f722d0b505d1c4131d2cba14569670fe
Metadata Total: 9
Metadata Written: 2
Content Total: 3
Content Written: 0
Content Bytes Written: 0 (0 bytes)
Installing app/org.flatpak.Hello/x86_64/master
Pruning cache
⬢[tofu@toolbox flatpak-linux-day]$ flatpak run org.flatpak.Hello
Ciao ciao pinguini!
⬢[tofu@toolbox flatpak-linux-day]$ ls
build-dir  hello.sh  org.flatpak.Hello.yml
⬢[tofu@toolbox flatpak-linux-day]$ ls build-dir/
export  files  metadata  var
⬢[tofu@toolbox flatpak-linux-day]$ ls build-dir/export/
⬢[tofu@toolbox flatpak-linux-day]$ ls build-dir/files/
bin  manifest.json
⬢[tofu@toolbox flatpak-linux-day]$ flatpak-builder --repo=repo --force-clean build-dir org.flatpak.Hello.yml
Emptying app dir 'build-dir'
Downloading sources
Starting build of org.flatpak.Hello
Cache hit for hello, skipping build
Cache hit for cleanup, skipping
Cache hit for finish, skipping
Everything cached, checking out from cache
Exporting org.flatpak.Hello to repo
Commit: e4831647c5f88b36e060db3ff535aed4a0368ef26596cccce36e936d21842777
Metadata Total: 9
Metadata Written: 6
Content Total: 3
Content Written: 3
Content Bytes Written: 827 (827 bytes)
Pruning cache
⬢[tofu@toolbox flatpak-linux-day]$ ls
build-dir  hello.sh  org.flatpak.Hello.yml  repo
⬢[tofu@toolbox flatpak-linux-day]$ ls repo/
config  extensions  objects  refs  state  summaries  summary  summary.idx  tmp
⬢[tofu@toolbox flatpak-linux-day]$ 
logout
[tofu@pinkpad ~]$ cd code/flatpak-linux-day/
[tofu@pinkpad flatpak-linux-day]$ flatpak --user remote-add --no-gpg-verify tutorial-repo repo
[tofu@pinkpad flatpak-linux-day]$ flatpak --user install tutorial-repo org.flatpak.Hello
Looking for matches…
error: org.flatpak.Hello/x86_64/master is already installed from remote hello-origin
[tofu@pinkpad flatpak-linux-day]$ flatpak --user install tutorial-repo org.flatpak.Hello^C
[tofu@pinkpad flatpak-linux-day]$ flatpak run org.flatpak.Hello
Ciao ciao pinguini!
[tofu@pinkpad flatpak-linux-day]$ cd ..
[tofu@pinkpad code]$ ls
adviser           flatpak-linux-day          rabbitmq-to-http  toolbox-demo
backport-bot      gitlab-private-namespace   rpt               virt-maint-container
build-automation  gitlab-projects            sig-guide         virt-maint-toolbox
cami-suite        gitlab-terraform-qemu-kvm  subtree-bot       virt-maint-tools
distro-scripts    gitlab-triage-policies     tektoncd          virt-sig-docs
fastbook          glab                       tekton-runner
[tofu@pinkpad code]$ mkdir toolbox-container
[tofu@pinkpad code]$ cd toolbox-container/
[tofu@pinkpad toolbox-container]$ vi Containerfile
[tofu@pinkpad toolbox-container]$ podman image ls
REPOSITORY                                       TAG         IMAGE ID      CREATED       SIZE
<none>                                           <none>      1146e6f7a745  24 hours ago  1.22 GB
docker.io/squidfunk/mkdocs-material              latest      468561bea4f3  4 weeks ago   200 MB
localhost/virt-maint-toolbox                     latest      63bae3bc7ad4  2 months ago  3.76 GB
quay.io/rhel-devel-tools/rhel-developer-toolbox  latest      1f47fa078bc3  2 months ago  6.23 GB
registry.gitlab.com/gitlab-org/cli               latest      6c652b4acf5a  2 months ago  388 MB
registry.fedoraproject.org/fedora                latest      919a420d29c6  3 months ago  196 MB
docker.io/library/docker                         cli         50a608703af7  5 months ago  152 MB
mcr.microsoft.com/azure-cli                      latest      5f396be15915  6 months ago  1 GB
registry.fedoraproject.org/fedora-toolbox        latest      997b52ccbf85  6 months ago  1.72 GB
registry.fedoraproject.org/fedora-toolbox        38          997b52ccbf85  6 months ago  1.72 GB
[tofu@pinkpad toolbox-container]$ vi Containerfile
[tofu@pinkpad toolbox-container]$ podman 
attach       (Attach to a running container)
auto-update  (Auto update containers according to their auto-update policy)
build        (Build an image using instructions from Containerfiles)
commit       (Create new image based on the changed container)
compose      (Run compose workloads via an external provider such as docker-compose or podman-compose)
container    (Manage containers)
cp           (Copy files/folders between a container and the local filesystem)
create       (Create but do not start a container)
diff         (Display the changes to the object's file system)
events       (Show podman system events)
exec         (Run a process in a running container)
export       (Export container's filesystem contents as a tar archive)
generate     (Generate structured data based on containers, pods or volumes)
healthcheck  (Manage health checks on containers)
help         (Help about any command)
history      (Show history of a specified image)
image        (Manage images)
images       (List images in local storage)
import       (Import a tarball to create a filesystem image)
info         (Display podman system information)
init         (Initialize one or more containers)
inspect      (Display the configuration of object denoted by ID)
kill         (Kill one or more running containers with a specific signal)
kube         (Play containers, pods or volumes from a structured file)
[tofu@pinkpad toolbox-container]$ podman build .
STEP 1/2: FROM registry.fedoraproject.org/fedora-toolbox
STEP 2/2: RUN dnf install -y flatpak
Fedora 38 - x86_64                              4.9 MB/s |  83 MB     00:16    
Fedora 38 openh264 (From Cisco) - x86_64        863  B/s | 2.5 kB     00:02    
Fedora Modular 38 - x86_64                      211 kB/s | 2.8 MB     00:13    
Fedora 38 - x86_64 - Updates                    3.2 MB/s |  34 MB     00:10    
Fedora Modular 38 - x86_64 - Updates            1.1 MB/s | 2.1 MB     00:02    
Dependencies resolved.
==========================================================================================
 Package                                   Arch    Version                  Repo      Size
==========================================================================================
Installing:
 flatpak                                   x86_64  1.15.4-1.fc38            fedora   1.6 M
Installing dependencies:
 ModemManager-glib                         x86_64  1.20.6-1.fc38            updates  323 k
 alsa-lib                                  x86_64  1.2.10-2.fc38            updates  521 k
 appstream                                 x86_64  0.16.1-1.fc38            fedora   723 k
 appstream-data                            noarch  38-6.fc38                updates   13 M
 avahi-glib                                x86_64  0.8-20.fc38              fedora    15 k
 bluez-libs                                x86_64  5.70-1.fc38              updates   83 k
 bubblewrap                                x86_64  0.7.0-1.fc38             fedora    60 k
 cairo                                     x86_64  1.17.8-4.fc38            updates  704 k
 cairo-gobject                             x86_64  1.17.8-4.fc38            updates   18 k
 dconf                                     x86_64  0.40.0-8.fc38            fedora   107 k
 device-mapper                             x86_64  1.02.189-2.fc38          fedora   139 k
 device-mapper-libs                        x86_64  1.02.189-2.fc38          fedora   176 k
 duktape                                   x86_64  2.7.0-2.fc38             fedora   170 k
 fdk-aac-free                              x86_64  2.0.0-10.fc38            fedora   336 k
 flac-libs                                 x86_64  1.4.3-1.fc38             updates  263 k
 flatpak-session-helper                    x86_64  1.15.4-1.fc38            fedora    44 k
 fontconfig                                x86_64  2.14.2-1.fc38            fedora   295 k
 freetype                                  x86_64  2.13.0-2.fc38            fedora   414 k
 fribidi                                   x86_64  1.0.12-3.fc38            fedora    89 k
 fuse                                      x86_64  2.9.9-16.fc38            fedora    79 k
 fuse-common                               x86_64  3.14.1-1.fc38            updates  6.9 k
 fuse3                                     x86_64  3.14.1-1.fc38            updates   55 k
 fuse3-libs                                x86_64  3.14.1-1.fc38            updates   93 k
 gdk-pixbuf2                               x86_64  2.42.10-2.fc38           fedora   485 k
 geoclue2                                  x86_64  2.7.0-1.fc38             updates  156 k
 google-noto-fonts-common                  noarch  20230201-1.fc38          fedora    16 k
 google-noto-sans-vf-fonts                 noarch  20230201-1.fc38          fedora   580 k
 graphite2                                 x86_64  1.3.14-11.fc38           fedora    95 k
 gsettings-desktop-schemas                 x86_64  44.0-1.fc38              fedora   733 k
 gsm                                       x86_64  1.0.22-2.fc38            fedora    35 k
 harfbuzz                                  x86_64  7.1.0-1.fc38             fedora   889 k
 json-glib                                 x86_64  1.6.6-4.fc38             fedora   162 k
 kmod-libs                                 x86_64  30-4.fc38                fedora    68 k
 lame-libs                                 x86_64  3.100-14.fc38            fedora   337 k
 langpacks-core-font-en                    noarch  3.0-32.fc38              updates  9.6 k
 libXft                                    x86_64  2.3.8-2.fc38             updates   72 k
 libXrender                                x86_64  0.9.11-2.fc38            fedora    27 k
 libargon2                                 x86_64  20190702-2.fc38          fedora    28 k
 libasyncns                                x86_64  0.8-24.fc38              fedora    30 k
 libdatrie                                 x86_64  0.2.13-5.fc38            fedora    32 k
 libjpeg-turbo                             x86_64  2.1.4-2.fc38             fedora   183 k
 libldac                                   x86_64  2.0.2.3-12.fc38          fedora    41 k
 libnotify                                 x86_64  0.8.2-1.fc38             fedora    51 k
 libogg                                    x86_64  2:1.3.5-5.fc38           fedora    33 k
 libpng                                    x86_64  2:1.6.37-14.fc38         fedora   120 k
 libproxy                                  x86_64  0.4.18-6.fc38            fedora    71 k
 librsvg2                                  x86_64  2.56.3-1.fc38            updates  1.6 M
 libsbc                                    x86_64  2.0-2.fc38               fedora    47 k
 libseccomp                                x86_64  2.5.3-4.fc38             fedora    71 k
 libsndfile                                x86_64  1.1.0-6.fc38             fedora   214 k
 libsoup3                                  x86_64  3.4.4-1.fc38             updates  389 k
 libstemmer                                x86_64  2.2.0-5.fc38             fedora   168 k
 libthai                                   x86_64  0.1.29-4.fc38            fedora   213 k
 libusb1                                   x86_64  1.0.26-2.fc38            fedora    74 k
 libvorbis                                 x86_64  1:1.3.7-7.fc38           fedora   195 k
 libxmlb                                   x86_64  0.3.14-1.fc38            updates  117 k
 low-memory-monitor                        x86_64  2.1-7.fc38               fedora    34 k
 malcontent-libs                           x86_64  0.11.1-1.fc38            fedora    46 k
 mpg123-libs                               x86_64  1.31.3-1.fc38            fedora   340 k
 opus                                      x86_64  1.3.1-12.fc38            fedora   206 k
 ostree-libs                               x86_64  2023.6-1.fc38            updates  460 k
 pango                                     x86_64  1.50.14-1.fc38           fedora   342 k
 pipewire-jack-audio-connection-kit-libs   x86_64  0.3.83-2.fc38            updates  140 k
 pipewire-libs                             x86_64  0.3.83-2.fc38            updates  1.8 M
 pixman                                    x86_64  0.42.2-1.fc38            fedora   285 k
 polkit                                    x86_64  122-3.fc38.1             updates  150 k
 polkit-libs                               x86_64  122-3.fc38.1             updates   63 k
 polkit-pkla-compat                        x86_64  0.1-23.fc38              fedora    44 k
 pulseaudio-libs                           x86_64  16.1-4.fc38              fedora   694 k
 rtkit                                     x86_64  0.11-58.fc38             fedora    55 k
 shared-mime-info                          x86_64  2.2-3.fc38               fedora   381 k
 systemd                                   x86_64  253.2-1.fc38             fedora   4.4 M
 systemd-pam                               x86_64  253.2-1.fc38             fedora   345 k
 webrtc-audio-processing                   x86_64  0.3.1-10.fc38            fedora   307 k
 wireplumber                               x86_64  0.4.15-1.fc38            updates   98 k
 wireplumber-libs                          x86_64  0.4.15-1.fc38            updates  347 k
 xdg-dbus-proxy                            x86_64  0.1.4-2.fc38             updates   42 k
 xkeyboard-config                          noarch  2.38-1.fc38              fedora   963 k
 xml-common                                noarch  0.6.3-60.fc38            fedora    31 k
Installing weak dependencies:
 abattis-cantarell-fonts                   noarch  0.301-9.fc38             fedora   270 k
 adobe-source-code-pro-fonts               noarch  2.042.1.062.1.026-2.fc38 updates  806 k
 cryptsetup-libs                           x86_64  2.6.1-1.fc38             fedora   492 k
 glib-networking                           x86_64  2.76.1-1.fc38            updates  195 k
 libproxy-duktape                          x86_64  0.4.18-6.fc38            fedora    17 k
 libxkbcommon                              x86_64  1.5.0-2.fc38             fedora   140 k
 p11-kit-server                            x86_64  0.24.1-6.fc38            fedora   192 k
 pipewire                                  x86_64  0.3.83-2.fc38            updates  112 k
 pipewire-alsa                             x86_64  0.3.83-2.fc38            updates   64 k
 pipewire-jack-audio-connection-kit        x86_64  0.3.83-2.fc38            updates   16 k
 pipewire-pulseaudio                       x86_64  0.3.83-2.fc38            updates  174 k
 qrencode-libs                             x86_64  4.1.1-4.fc38             fedora    61 k
 systemd-networkd                          x86_64  253.2-1.fc38             fedora   636 k
 systemd-resolved                          x86_64  253.2-1.fc38             fedora   291 k
 xdg-desktop-portal                        x86_64  1.16.0-3.fc38            fedora   435 k

Transaction Summary
==========================================================================================
Install  95 Packages

Total download size: 42 M
Installed size: 114 M
Downloading Packages:
(1/95): avahi-glib-0.8-20.fc38.x86_64.rpm        34 kB/s |  15 kB     00:00    
(2/95): abattis-cantarell-fonts-0.301-9.fc38.no 495 kB/s | 270 kB     00:00    
(3/95): bubblewrap-0.7.0-1.fc38.x86_64.rpm      261 kB/s |  60 kB     00:00    
(4/95): dconf-0.40.0-8.fc38.x86_64.rpm          284 kB/s | 107 kB     00:00    
(5/95): cryptsetup-libs-2.6.1-1.fc38.x86_64.rpm 701 kB/s | 492 kB     00:00    
(6/95): device-mapper-1.02.189-2.fc38.x86_64.rp 391 kB/s | 139 kB     00:00    
(7/95): appstream-0.16.1-1.fc38.x86_64.rpm      470 kB/s | 723 kB     00:01    
(8/95): duktape-2.7.0-2.fc38.x86_64.rpm         315 kB/s | 170 kB     00:00    
(9/95): device-mapper-libs-1.02.189-2.fc38.x86_ 107 kB/s | 176 kB     00:01    
(10/95): flatpak-session-helper-1.15.4-1.fc38.x  82 kB/s |  44 kB     00:00    
(11/95): fdk-aac-free-2.0.0-10.fc38.x86_64.rpm  164 kB/s | 336 kB     00:02    
(12/95): fontconfig-2.14.2-1.fc38.x86_64.rpm    884 kB/s | 295 kB     00:00    
(13/95): fribidi-1.0.12-3.fc38.x86_64.rpm       673 kB/s |  89 kB     00:00    
(14/95): fuse-2.9.9-16.fc38.x86_64.rpm          825 kB/s |  79 kB     00:00    
(15/95): freetype-2.13.0-2.fc38.x86_64.rpm      940 kB/s | 414 kB     00:00    
(16/95): google-noto-fonts-common-20230201-1.fc 336 kB/s |  16 kB     00:00    
(17/95): gdk-pixbuf2-2.42.10-2.fc38.x86_64.rpm  1.1 MB/s | 485 kB     00:00    
(18/95): graphite2-1.3.14-11.fc38.x86_64.rpm    723 kB/s |  95 kB     00:00    
(19/95): google-noto-sans-vf-fonts-20230201-1.f 996 kB/s | 580 kB     00:00    
(20/95): gsm-1.0.22-2.fc38.x86_64.rpm           507 kB/s |  35 kB     00:00    
(21/95): gsettings-desktop-schemas-44.0-1.fc38. 1.2 MB/s | 733 kB     00:00    
(22/95): flatpak-1.15.4-1.fc38.x86_64.rpm       503 kB/s | 1.6 MB     00:03    
(23/95): json-glib-1.6.6-4.fc38.x86_64.rpm      1.1 MB/s | 162 kB     00:00    
(24/95): kmod-libs-30-4.fc38.x86_64.rpm         1.0 MB/s |  68 kB     00:00    
(25/95): libXrender-0.9.11-2.fc38.x86_64.rpm    375 kB/s |  27 kB     00:00    
(26/95): harfbuzz-7.1.0-1.fc38.x86_64.rpm       1.2 MB/s | 889 kB     00:00    
(27/95): libargon2-20190702-2.fc38.x86_64.rpm   197 kB/s |  28 kB     00:00    
(28/95): libasyncns-0.8-24.fc38.x86_64.rpm      339 kB/s |  30 kB     00:00    
(29/95): libdatrie-0.2.13-5.fc38.x86_64.rpm     626 kB/s |  32 kB     00:00    
(30/95): lame-libs-3.100-14.fc38.x86_64.rpm     1.0 MB/s | 337 kB     00:00    
(31/95): libldac-2.0.2.3-12.fc38.x86_64.rpm     699 kB/s |  41 kB     00:00    
(32/95): libnotify-0.8.2-1.fc38.x86_64.rpm      854 kB/s |  51 kB     00:00    
(33/95): libogg-1.3.5-5.fc38.x86_64.rpm         534 kB/s |  33 kB     00:00    
(34/95): libjpeg-turbo-2.1.4-2.fc38.x86_64.rpm  1.0 MB/s | 183 kB     00:00    
(35/95): libpng-1.6.37-14.fc38.x86_64.rpm       1.0 MB/s | 120 kB     00:00    
(36/95): libproxy-0.4.18-6.fc38.x86_64.rpm      834 kB/s |  71 kB     00:00    
(37/95): libproxy-duktape-0.4.18-6.fc38.x86_64. 242 kB/s |  17 kB     00:00    
(38/95): libsbc-2.0-2.fc38.x86_64.rpm           834 kB/s |  47 kB     00:00    
(39/95): libseccomp-2.5.3-4.fc38.x86_64.rpm     1.1 MB/s |  71 kB     00:00    
(40/95): libstemmer-2.2.0-5.fc38.x86_64.rpm     996 kB/s | 168 kB     00:00    
(41/95): libsndfile-1.1.0-6.fc38.x86_64.rpm     990 kB/s | 214 kB     00:00    
(42/95): libthai-0.1.29-4.fc38.x86_64.rpm       925 kB/s | 213 kB     00:00    
(43/95): libusb1-1.0.26-2.fc38.x86_64.rpm       390 kB/s |  74 kB     00:00    
(44/95): libvorbis-1.3.7-7.fc38.x86_64.rpm      946 kB/s | 195 kB     00:00    
(45/95): libxkbcommon-1.5.0-2.fc38.x86_64.rpm   1.1 MB/s | 140 kB     00:00    
(46/95): low-memory-monitor-2.1-7.fc38.x86_64.r 534 kB/s |  34 kB     00:00    
(47/95): malcontent-libs-0.11.1-1.fc38.x86_64.r 764 kB/s |  46 kB     00:00    
(48/95): opus-1.3.1-12.fc38.x86_64.rpm          801 kB/s | 206 kB     00:00    
(49/95): mpg123-libs-1.31.3-1.fc38.x86_64.rpm   873 kB/s | 340 kB     00:00    
(50/95): p11-kit-server-0.24.1-6.fc38.x86_64.rp 575 kB/s | 192 kB     00:00    
(51/95): polkit-pkla-compat-0.1-23.fc38.x86_64. 573 kB/s |  44 kB     00:00    
(52/95): pango-1.50.14-1.fc38.x86_64.rpm        929 kB/s | 342 kB     00:00    
(53/95): pixman-0.42.2-1.fc38.x86_64.rpm        1.0 MB/s | 285 kB     00:00    
(54/95): rtkit-0.11-58.fc38.x86_64.rpm          646 kB/s |  55 kB     00:00    
(55/95): qrencode-libs-4.1.1-4.fc38.x86_64.rpm  646 kB/s |  61 kB     00:00    
(56/95): shared-mime-info-2.2-3.fc38.x86_64.rpm 1.1 MB/s | 381 kB     00:00    
(57/95): pulseaudio-libs-16.1-4.fc38.x86_64.rpm 999 kB/s | 694 kB     00:00    
(58/95): systemd-networkd-253.2-1.fc38.x86_64.r 945 kB/s | 636 kB     00:00    
(59/95): systemd-pam-253.2-1.fc38.x86_64.rpm    487 kB/s | 345 kB     00:00    
(60/95): systemd-resolved-253.2-1.fc38.x86_64.r 767 kB/s | 291 kB     00:00    
(61/95): webrtc-audio-processing-0.3.1-10.fc38. 700 kB/s | 307 kB     00:00    
(62/95): xdg-desktop-portal-1.16.0-3.fc38.x86_6 944 kB/s | 435 kB     00:00    
(63/95): xml-common-0.6.3-60.fc38.noarch.rpm     89 kB/s |  31 kB     00:00    
(64/95): xkeyboard-config-2.38-1.fc38.noarch.rp 994 kB/s | 963 kB     00:00    
(65/95): systemd-253.2-1.fc38.x86_64.rpm        1.5 MB/s | 4.4 MB     00:02    
(66/95): adobe-source-code-pro-fonts-2.042.1.06 668 kB/s | 806 kB     00:01    
(67/95): ModemManager-glib-1.20.6-1.fc38.x86_64 119 kB/s | 323 kB     00:02    
(68/95): bluez-libs-5.70-1.fc38.x86_64.rpm      215 kB/s |  83 kB     00:00    
(69/95): alsa-lib-1.2.10-2.fc38.x86_64.rpm      214 kB/s | 521 kB     00:02    
(70/95): cairo-gobject-1.17.8-4.fc38.x86_64.rpm  80 kB/s |  18 kB     00:00    
(71/95): flac-libs-1.4.3-1.fc38.x86_64.rpm      490 kB/s | 263 kB     00:00    
(72/95): cairo-1.17.8-4.fc38.x86_64.rpm         787 kB/s | 704 kB     00:00    
(73/95): fuse-common-3.14.1-1.fc38.x86_64.rpm    26 kB/s | 6.9 kB     00:00    
(74/95): fuse3-3.14.1-1.fc38.x86_64.rpm         184 kB/s |  55 kB     00:00    
(75/95): fuse3-libs-3.14.1-1.fc38.x86_64.rpm    294 kB/s |  93 kB     00:00    
(76/95): geoclue2-2.7.0-1.fc38.x86_64.rpm       570 kB/s | 156 kB     00:00    
(77/95): langpacks-core-font-en-3.0-32.fc38.noa  38 kB/s | 9.6 kB     00:00    
(78/95): glib-networking-2.76.1-1.fc38.x86_64.r 387 kB/s | 195 kB     00:00    
(79/95): libXft-2.3.8-2.fc38.x86_64.rpm         267 kB/s |  72 kB     00:00    
(80/95): libsoup3-3.4.4-1.fc38.x86_64.rpm       522 kB/s | 389 kB     00:00    
(81/95): libxmlb-0.3.14-1.fc38.x86_64.rpm       408 kB/s | 117 kB     00:00    
(82/95): appstream-data-38-6.fc38.noarch.rpm    2.5 MB/s |  13 MB     00:05    
(83/95): ostree-libs-2023.6-1.fc38.x86_64.rpm   558 kB/s | 460 kB     00:00    
(84/95): librsvg2-2.56.3-1.fc38.x86_64.rpm      829 kB/s | 1.6 MB     00:01    
(85/95): pipewire-0.3.83-2.fc38.x86_64.rpm      1.2 MB/s | 112 kB     00:00    
(86/95): pipewire-alsa-0.3.83-2.fc38.x86_64.rpm 660 kB/s |  64 kB     00:00    
(87/95): pipewire-jack-audio-connection-kit-0.3 199 kB/s |  16 kB     00:00    
(88/95): pipewire-jack-audio-connection-kit-lib 1.6 MB/s | 140 kB     00:00    
(89/95): pipewire-libs-0.3.83-2.fc38.x86_64.rpm 6.3 MB/s | 1.8 MB     00:00    
(90/95): pipewire-pulseaudio-0.3.83-2.fc38.x86_ 583 kB/s | 174 kB     00:00    
(91/95): polkit-122-3.fc38.1.x86_64.rpm         678 kB/s | 150 kB     00:00    
(92/95): polkit-libs-122-3.fc38.1.x86_64.rpm    743 kB/s |  63 kB     00:00    
(93/95): wireplumber-0.4.15-1.fc38.x86_64.rpm   1.0 MB/s |  98 kB     00:00    
(94/95): wireplumber-libs-0.4.15-1.fc38.x86_64. 1.7 MB/s | 347 kB     00:00    
(95/95): xdg-dbus-proxy-0.1.4-2.fc38.x86_64.rpm 364 kB/s |  42 kB     00:00    
--------------------------------------------------------------------------------
Total                                           2.4 MB/s |  42 MB     00:17     
Running transaction check
Transaction check succeeded.
Running transaction test
Transaction test succeeded.
Running transaction
  Preparing        :                                                        1/1 
  Installing       : libpng-2:1.6.37-14.fc38.x86_64                        1/95 
  Installing       : polkit-libs-122-3.fc38.1.x86_64                       2/95 
  Installing       : fuse3-libs-3.14.1-1.fc38.x86_64                       3/95 
  Installing       : libogg-2:1.3.5-5.fc38.x86_64                          4/95 
  Installing       : libXrender-0.9.11-2.fc38.x86_64                       5/95 
  Installing       : json-glib-1.6.6-4.fc38.x86_64                         6/95 
  Installing       : fuse-common-3.14.1-1.fc38.x86_64                      7/95 
  Installing       : alsa-lib-1.2.10-2.fc38.x86_64                         8/95 
  Installing       : shared-mime-info-2.2-3.fc38.x86_64                    9/95 
  Running scriptlet: shared-mime-info-2.2-3.fc38.x86_64                    9/95 
  Installing       : opus-1.3.1-12.fc38.x86_64                            10/95 
  Installing       : libseccomp-2.5.3-4.fc38.x86_64                       11/95 
  Installing       : libproxy-0.4.18-6.fc38.x86_64                        12/95 
  Installing       : duktape-2.7.0-2.fc38.x86_64                          13/95 
  Installing       : libproxy-duktape-0.4.18-6.fc38.x86_64                14/95 
  Installing       : libxmlb-0.3.14-1.fc38.x86_64                         15/95 
  Installing       : fuse-2.9.9-16.fc38.x86_64                            16/95 
  Installing       : fuse3-3.14.1-1.fc38.x86_64                           17/95 
  Installing       : libvorbis-1:1.3.7-7.fc38.x86_64                      18/95 
  Installing       : flac-libs-1.4.3-1.fc38.x86_64                        19/95 
  Installing       : xdg-dbus-proxy-0.1.4-2.fc38.x86_64                   20/95 
  Installing       : ostree-libs-2023.6-1.fc38.x86_64                     21/95 
  Installing       : bluez-libs-5.70-1.fc38.x86_64                        22/95 
  Installing       : appstream-data-38-6.fc38.noarch                      23/95 
  Installing       : adobe-source-code-pro-fonts-2.042.1.062.1.026-2.fc   24/95 
  Installing       : ModemManager-glib-1.20.6-1.fc38.x86_64               25/95 
  Running scriptlet: xml-common-0.6.3-60.fc38.noarch                      26/95 
  Installing       : xml-common-0.6.3-60.fc38.noarch                      26/95 
  Installing       : xkeyboard-config-2.38-1.fc38.noarch                  27/95 
  Installing       : libxkbcommon-1.5.0-2.fc38.x86_64                     28/95 
  Installing       : webrtc-audio-processing-0.3.1-10.fc38.x86_64         29/95 
  Installing       : qrencode-libs-4.1.1-4.fc38.x86_64                    30/95 
  Installing       : pixman-0.42.2-1.fc38.x86_64                          31/95 
  Installing       : p11-kit-server-0.24.1-6.fc38.x86_64                  32/95 
  Installing       : mpg123-libs-1.31.3-1.fc38.x86_64                     33/95 
  Installing       : malcontent-libs-0.11.1-1.fc38.x86_64                 34/95 
  Installing       : low-memory-monitor-2.1-7.fc38.x86_64                 35/95 
  Running scriptlet: low-memory-monitor-2.1-7.fc38.x86_64                 35/95 
  Installing       : libusb1-1.0.26-2.fc38.x86_64                         36/95 
  Installing       : libstemmer-2.2.0-5.fc38.x86_64                       37/95 
  Installing       : appstream-0.16.1-1.fc38.x86_64                       38/95 
  Installing       : libsbc-2.0-2.fc38.x86_64                             39/95 
  Installing       : libldac-2.0.2.3-12.fc38.x86_64                       40/95 
  Installing       : libjpeg-turbo-2.1.4-2.fc38.x86_64                    41/95 
  Installing       : gdk-pixbuf2-2.42.10-2.fc38.x86_64                    42/95 
  Installing       : libnotify-0.8.2-1.fc38.x86_64                        43/95 
  Installing       : libdatrie-0.2.13-5.fc38.x86_64                       44/95 
  Installing       : libthai-0.1.29-4.fc38.x86_64                         45/95 
  Installing       : libasyncns-0.8-24.fc38.x86_64                        46/95 
  Installing       : libargon2-20190702-2.fc38.x86_64                     47/95 
  Installing       : lame-libs-3.100-14.fc38.x86_64                       48/95 
  Installing       : kmod-libs-30-4.fc38.x86_64                           49/95 
  Installing       : device-mapper-libs-1.02.189-2.fc38.x86_64            50/95 
  Installing       : cryptsetup-libs-2.6.1-1.fc38.x86_64                  51/95 
  Installing       : device-mapper-1.02.189-2.fc38.x86_64                 52/95 
  Installing       : systemd-networkd-253.2-1.fc38.x86_64                 53/95 
  Running scriptlet: systemd-networkd-253.2-1.fc38.x86_64                 53/95 
  Installing       : systemd-pam-253.2-1.fc38.x86_64                      54/95 
  Installing       : systemd-resolved-253.2-1.fc38.x86_64                 55/95 
  Running scriptlet: systemd-resolved-253.2-1.fc38.x86_64                 55/95 
  Installing       : systemd-253.2-1.fc38.x86_64                          56/95 
  Running scriptlet: systemd-253.2-1.fc38.x86_64                          56/95 
Creating group 'input' with GID 104.
Creating group 'kvm' with GID 36.
Creating group 'render' with GID 105.
Creating group 'sgx' with GID 106.
Creating group 'systemd-journal' with GID 190.
Creating group 'systemd-network' with GID 192.
Creating user 'systemd-network' (systemd Network Management) with UID 192 and GID 192.
Creating group 'systemd-oom' with GID 999.
Creating user 'systemd-oom' (systemd Userspace OOM Killer) with UID 999 and GID 999.
Creating group 'systemd-resolve' with GID 193.
Creating user 'systemd-resolve' (systemd Resolver) with UID 193 and GID 193.

  Running scriptlet: polkit-122-3.fc38.1.x86_64                           57/95 
  Installing       : polkit-122-3.fc38.1.x86_64                           57/95 
  Running scriptlet: polkit-122-3.fc38.1.x86_64                           57/95 
  Installing       : polkit-pkla-compat-0.1-23.fc38.x86_64                58/95 
  Running scriptlet: rtkit-0.11-58.fc38.x86_64                            59/95 
  Installing       : rtkit-0.11-58.fc38.x86_64                            59/95 
  Running scriptlet: rtkit-0.11-58.fc38.x86_64                            59/95 
Created symlink /etc/systemd/system/graphical.target.wants/rtkit-daemon.service → /usr/lib/systemd/system/rtkit-daemon.service.

  Installing       : flatpak-session-helper-1.15.4-1.fc38.x86_64          60/95 
  Installing       : gsm-1.0.22-2.fc38.x86_64                             61/95 
  Installing       : libsndfile-1.1.0-6.fc38.x86_64                       62/95 
  Installing       : pulseaudio-libs-16.1-4.fc38.x86_64                   63/95 
  Installing       : graphite2-1.3.14-11.fc38.x86_64                      64/95 
  Installing       : google-noto-fonts-common-20230201-1.fc38.noarch      65/95 
  Installing       : google-noto-sans-vf-fonts-20230201-1.fc38.noarch     66/95 
  Installing       : langpacks-core-font-en-3.0-32.fc38.noarch            67/95 
  Installing       : cairo-1.17.8-4.fc38.x86_64                           68/95 
  Installing       : harfbuzz-7.1.0-1.fc38.x86_64                         69/95 
  Installing       : freetype-2.13.0-2.fc38.x86_64                        70/95 
  Installing       : fontconfig-2.14.2-1.fc38.x86_64                      71/95 
  Running scriptlet: fontconfig-2.14.2-1.fc38.x86_64                      71/95 
  Installing       : libXft-2.3.8-2.fc38.x86_64                           72/95 
  Installing       : cairo-gobject-1.17.8-4.fc38.x86_64                   73/95 
  Installing       : fribidi-1.0.12-3.fc38.x86_64                         74/95 
  Installing       : pango-1.50.14-1.fc38.x86_64                          75/95 
  Installing       : librsvg2-2.56.3-1.fc38.x86_64                        76/95 
  Installing       : fdk-aac-free-2.0.0-10.fc38.x86_64                    77/95 
  Installing       : pipewire-libs-0.3.83-2.fc38.x86_64                   78/95 
  Running scriptlet: pipewire-0.3.83-2.fc38.x86_64                        79/95 
  Installing       : pipewire-0.3.83-2.fc38.x86_64                        79/95 
  Running scriptlet: pipewire-0.3.83-2.fc38.x86_64                        79/95 
Created symlink /etc/systemd/user/sockets.target.wants/pipewire.socket → /usr/lib/systemd/user/pipewire.socket.

  Installing       : wireplumber-libs-0.4.15-1.fc38.x86_64                80/95 
  Installing       : wireplumber-0.4.15-1.fc38.x86_64                     81/95 
  Installing       : pipewire-jack-audio-connection-kit-libs-0.3.83-2.f   82/95 
  Installing       : dconf-0.40.0-8.fc38.x86_64                           83/95 
  Running scriptlet: dconf-0.40.0-8.fc38.x86_64                           83/95 
  Installing       : bubblewrap-0.7.0-1.fc38.x86_64                       84/95 
  Installing       : avahi-glib-0.8-20.fc38.x86_64                        85/95 
  Installing       : abattis-cantarell-fonts-0.301-9.fc38.noarch          86/95 
  Installing       : gsettings-desktop-schemas-44.0-1.fc38.x86_64         87/95 
  Installing       : glib-networking-2.76.1-1.fc38.x86_64                 88/95 
  Installing       : libsoup3-3.4.4-1.fc38.x86_64                         89/95 
  Running scriptlet: geoclue2-2.7.0-1.fc38.x86_64                         90/95 
  Installing       : geoclue2-2.7.0-1.fc38.x86_64                         90/95 
  Running scriptlet: geoclue2-2.7.0-1.fc38.x86_64                         90/95 
  Installing       : xdg-desktop-portal-1.16.0-3.fc38.x86_64              91/95 
  Running scriptlet: xdg-desktop-portal-1.16.0-3.fc38.x86_64              91/95 
  Running scriptlet: flatpak-1.15.4-1.fc38.x86_64                         92/95 
  Installing       : flatpak-1.15.4-1.fc38.x86_64                         92/95 
  Running scriptlet: flatpak-1.15.4-1.fc38.x86_64                         92/95 
Created symlink /etc/systemd/system/multi-user.target.wants/flatpak-add-fedora-repos.service → /usr/lib/systemd/system/flatpak-add-fedora-repos.service.

  Installing       : pipewire-jack-audio-connection-kit-0.3.83-2.fc38.x   93/95 
  Installing       : pipewire-alsa-0.3.83-2.fc38.x86_64                   94/95 
  Installing       : pipewire-pulseaudio-0.3.83-2.fc38.x86_64             95/95 
  Running scriptlet: pipewire-pulseaudio-0.3.83-2.fc38.x86_64             95/95 
Created symlink /etc/systemd/user/sockets.target.wants/pipewire-pulse.socket → /usr/lib/systemd/user/pipewire-pulse.socket.

  Running scriptlet: appstream-0.16.1-1.fc38.x86_64                       95/95 
  Running scriptlet: systemd-resolved-253.2-1.fc38.x86_64                 95/95 
  Running scriptlet: fontconfig-2.14.2-1.fc38.x86_64                      95/95 
  Running scriptlet: wireplumber-0.4.15-1.fc38.x86_64                     95/95 
Created symlink /etc/systemd/user/pipewire-session-manager.service → /usr/lib/systemd/user/wireplumber.service.
Created symlink /etc/systemd/user/pipewire.service.wants/wireplumber.service → /usr/lib/systemd/user/wireplumber.service.

  Running scriptlet: dconf-0.40.0-8.fc38.x86_64                           95/95 
  Running scriptlet: pipewire-pulseaudio-0.3.83-2.fc38.x86_64             95/95 
  Verifying        : abattis-cantarell-fonts-0.301-9.fc38.noarch           1/95 
  Verifying        : appstream-0.16.1-1.fc38.x86_64                        2/95 
  Verifying        : avahi-glib-0.8-20.fc38.x86_64                         3/95 
  Verifying        : bubblewrap-0.7.0-1.fc38.x86_64                        4/95 
  Verifying        : cryptsetup-libs-2.6.1-1.fc38.x86_64                   5/95 
  Verifying        : dconf-0.40.0-8.fc38.x86_64                            6/95 
  Verifying        : device-mapper-1.02.189-2.fc38.x86_64                  7/95 
  Verifying        : device-mapper-libs-1.02.189-2.fc38.x86_64             8/95 
  Verifying        : duktape-2.7.0-2.fc38.x86_64                           9/95 
  Verifying        : fdk-aac-free-2.0.0-10.fc38.x86_64                    10/95 
  Verifying        : flatpak-1.15.4-1.fc38.x86_64                         11/95 
  Verifying        : flatpak-session-helper-1.15.4-1.fc38.x86_64          12/95 
  Verifying        : fontconfig-2.14.2-1.fc38.x86_64                      13/95 
  Verifying        : freetype-2.13.0-2.fc38.x86_64                        14/95 
  Verifying        : fribidi-1.0.12-3.fc38.x86_64                         15/95 
  Verifying        : fuse-2.9.9-16.fc38.x86_64                            16/95 
  Verifying        : gdk-pixbuf2-2.42.10-2.fc38.x86_64                    17/95 
  Verifying        : google-noto-fonts-common-20230201-1.fc38.noarch      18/95 
  Verifying        : google-noto-sans-vf-fonts-20230201-1.fc38.noarch     19/95 
  Verifying        : graphite2-1.3.14-11.fc38.x86_64                      20/95 
  Verifying        : gsettings-desktop-schemas-44.0-1.fc38.x86_64         21/95 
  Verifying        : gsm-1.0.22-2.fc38.x86_64                             22/95 
  Verifying        : harfbuzz-7.1.0-1.fc38.x86_64                         23/95 
  Verifying        : json-glib-1.6.6-4.fc38.x86_64                        24/95 
  Verifying        : kmod-libs-30-4.fc38.x86_64                           25/95 
  Verifying        : lame-libs-3.100-14.fc38.x86_64                       26/95 
  Verifying        : libXrender-0.9.11-2.fc38.x86_64                      27/95 
  Verifying        : libargon2-20190702-2.fc38.x86_64                     28/95 
  Verifying        : libasyncns-0.8-24.fc38.x86_64                        29/95 
  Verifying        : libdatrie-0.2.13-5.fc38.x86_64                       30/95 
  Verifying        : libjpeg-turbo-2.1.4-2.fc38.x86_64                    31/95 
  Verifying        : libldac-2.0.2.3-12.fc38.x86_64                       32/95 
  Verifying        : libnotify-0.8.2-1.fc38.x86_64                        33/95 
  Verifying        : libogg-2:1.3.5-5.fc38.x86_64                         34/95 
  Verifying        : libpng-2:1.6.37-14.fc38.x86_64                       35/95 
  Verifying        : libproxy-0.4.18-6.fc38.x86_64                        36/95 
  Verifying        : libproxy-duktape-0.4.18-6.fc38.x86_64                37/95 
  Verifying        : libsbc-2.0-2.fc38.x86_64                             38/95 
  Verifying        : libseccomp-2.5.3-4.fc38.x86_64                       39/95 
  Verifying        : libsndfile-1.1.0-6.fc38.x86_64                       40/95 
  Verifying        : libstemmer-2.2.0-5.fc38.x86_64                       41/95 
  Verifying        : libthai-0.1.29-4.fc38.x86_64                         42/95 
  Verifying        : libusb1-1.0.26-2.fc38.x86_64                         43/95 
  Verifying        : libvorbis-1:1.3.7-7.fc38.x86_64                      44/95 
  Verifying        : libxkbcommon-1.5.0-2.fc38.x86_64                     45/95 
  Verifying        : low-memory-monitor-2.1-7.fc38.x86_64                 46/95 
  Verifying        : malcontent-libs-0.11.1-1.fc38.x86_64                 47/95 
  Verifying        : mpg123-libs-1.31.3-1.fc38.x86_64                     48/95 
  Verifying        : opus-1.3.1-12.fc38.x86_64                            49/95 
  Verifying        : p11-kit-server-0.24.1-6.fc38.x86_64                  50/95 
  Verifying        : pango-1.50.14-1.fc38.x86_64                          51/95 
  Verifying        : pixman-0.42.2-1.fc38.x86_64                          52/95 
  Verifying        : polkit-pkla-compat-0.1-23.fc38.x86_64                53/95 
  Verifying        : pulseaudio-libs-16.1-4.fc38.x86_64                   54/95 
  Verifying        : qrencode-libs-4.1.1-4.fc38.x86_64                    55/95 
  Verifying        : rtkit-0.11-58.fc38.x86_64                            56/95 
  Verifying        : shared-mime-info-2.2-3.fc38.x86_64                   57/95 
  Verifying        : systemd-253.2-1.fc38.x86_64                          58/95 
  Verifying        : systemd-networkd-253.2-1.fc38.x86_64                 59/95 
  Verifying        : systemd-pam-253.2-1.fc38.x86_64                      60/95 
  Verifying        : systemd-resolved-253.2-1.fc38.x86_64                 61/95 
  Verifying        : webrtc-audio-processing-0.3.1-10.fc38.x86_64         62/95 
  Verifying        : xdg-desktop-portal-1.16.0-3.fc38.x86_64              63/95 
  Verifying        : xkeyboard-config-2.38-1.fc38.noarch                  64/95 
  Verifying        : xml-common-0.6.3-60.fc38.noarch                      65/95 
  Verifying        : ModemManager-glib-1.20.6-1.fc38.x86_64               66/95 
  Verifying        : adobe-source-code-pro-fonts-2.042.1.062.1.026-2.fc   67/95 
  Verifying        : alsa-lib-1.2.10-2.fc38.x86_64                        68/95 
  Verifying        : appstream-data-38-6.fc38.noarch                      69/95 
  Verifying        : bluez-libs-5.70-1.fc38.x86_64                        70/95 
  Verifying        : cairo-1.17.8-4.fc38.x86_64                           71/95 
  Verifying        : cairo-gobject-1.17.8-4.fc38.x86_64                   72/95 
  Verifying        : flac-libs-1.4.3-1.fc38.x86_64                        73/95 
  Verifying        : fuse-common-3.14.1-1.fc38.x86_64                     74/95 
  Verifying        : fuse3-3.14.1-1.fc38.x86_64                           75/95 
  Verifying        : fuse3-libs-3.14.1-1.fc38.x86_64                      76/95 
  Verifying        : geoclue2-2.7.0-1.fc38.x86_64                         77/95 
  Verifying        : glib-networking-2.76.1-1.fc38.x86_64                 78/95 
  Verifying        : langpacks-core-font-en-3.0-32.fc38.noarch            79/95 
  Verifying        : libXft-2.3.8-2.fc38.x86_64                           80/95 
  Verifying        : librsvg2-2.56.3-1.fc38.x86_64                        81/95 
  Verifying        : libsoup3-3.4.4-1.fc38.x86_64                         82/95 
  Verifying        : libxmlb-0.3.14-1.fc38.x86_64                         83/95 
  Verifying        : ostree-libs-2023.6-1.fc38.x86_64                     84/95 
  Verifying        : pipewire-0.3.83-2.fc38.x86_64                        85/95 
  Verifying        : pipewire-alsa-0.3.83-2.fc38.x86_64                   86/95 
  Verifying        : pipewire-jack-audio-connection-kit-0.3.83-2.fc38.x   87/95 
  Verifying        : pipewire-jack-audio-connection-kit-libs-0.3.83-2.f   88/95 
  Verifying        : pipewire-libs-0.3.83-2.fc38.x86_64                   89/95 
  Verifying        : pipewire-pulseaudio-0.3.83-2.fc38.x86_64             90/95 
  Verifying        : polkit-122-3.fc38.1.x86_64                           91/95 
  Verifying        : polkit-libs-122-3.fc38.1.x86_64                      92/95 
  Verifying        : wireplumber-0.4.15-1.fc38.x86_64                     93/95 
  Verifying        : wireplumber-libs-0.4.15-1.fc38.x86_64                94/95 
  Verifying        : xdg-dbus-proxy-0.1.4-2.fc38.x86_64                   95/95 

Installed:
  ModemManager-glib-1.20.6-1.fc38.x86_64                                        
  abattis-cantarell-fonts-0.301-9.fc38.noarch                                   
  adobe-source-code-pro-fonts-2.042.1.062.1.026-2.fc38.noarch                   
  alsa-lib-1.2.10-2.fc38.x86_64                                                 
  appstream-0.16.1-1.fc38.x86_64                                                
  appstream-data-38-6.fc38.noarch                                               
  avahi-glib-0.8-20.fc38.x86_64                                                 
  bluez-libs-5.70-1.fc38.x86_64                                                 
  bubblewrap-0.7.0-1.fc38.x86_64                                                
  cairo-1.17.8-4.fc38.x86_64                                                    
  cairo-gobject-1.17.8-4.fc38.x86_64                                            
  cryptsetup-libs-2.6.1-1.fc38.x86_64                                           
  dconf-0.40.0-8.fc38.x86_64                                                    
  device-mapper-1.02.189-2.fc38.x86_64                                          
  device-mapper-libs-1.02.189-2.fc38.x86_64                                     
  duktape-2.7.0-2.fc38.x86_64                                                   
  fdk-aac-free-2.0.0-10.fc38.x86_64                                             
  flac-libs-1.4.3-1.fc38.x86_64                                                 
  flatpak-1.15.4-1.fc38.x86_64                                                  
  flatpak-session-helper-1.15.4-1.fc38.x86_64                                   
  fontconfig-2.14.2-1.fc38.x86_64                                               
  freetype-2.13.0-2.fc38.x86_64                                                 
  fribidi-1.0.12-3.fc38.x86_64                                                  
  fuse-2.9.9-16.fc38.x86_64                                                     
  fuse-common-3.14.1-1.fc38.x86_64                                              
  fuse3-3.14.1-1.fc38.x86_64                                                    
  fuse3-libs-3.14.1-1.fc38.x86_64                                               
  gdk-pixbuf2-2.42.10-2.fc38.x86_64                                             
  geoclue2-2.7.0-1.fc38.x86_64                                                  
  glib-networking-2.76.1-1.fc38.x86_64                                          
  google-noto-fonts-common-20230201-1.fc38.noarch                               
  google-noto-sans-vf-fonts-20230201-1.fc38.noarch                              
  graphite2-1.3.14-11.fc38.x86_64                                               
  gsettings-desktop-schemas-44.0-1.fc38.x86_64                                  
  gsm-1.0.22-2.fc38.x86_64                                                      
  harfbuzz-7.1.0-1.fc38.x86_64                                                  
  json-glib-1.6.6-4.fc38.x86_64                                                 
  kmod-libs-30-4.fc38.x86_64                                                    
  lame-libs-3.100-14.fc38.x86_64                                                
  langpacks-core-font-en-3.0-32.fc38.noarch                                     
  libXft-2.3.8-2.fc38.x86_64                                                    
  libXrender-0.9.11-2.fc38.x86_64                                               
  libargon2-20190702-2.fc38.x86_64                                              
  libasyncns-0.8-24.fc38.x86_64                                                 
  libdatrie-0.2.13-5.fc38.x86_64                                                
  libjpeg-turbo-2.1.4-2.fc38.x86_64                                             
  libldac-2.0.2.3-12.fc38.x86_64                                                
  libnotify-0.8.2-1.fc38.x86_64                                                 
  libogg-2:1.3.5-5.fc38.x86_64                                                  
  libpng-2:1.6.37-14.fc38.x86_64                                                
  libproxy-0.4.18-6.fc38.x86_64                                                 
  libproxy-duktape-0.4.18-6.fc38.x86_64                                         
  librsvg2-2.56.3-1.fc38.x86_64                                                 
  libsbc-2.0-2.fc38.x86_64                                                      
  libseccomp-2.5.3-4.fc38.x86_64                                                
  libsndfile-1.1.0-6.fc38.x86_64                                                
  libsoup3-3.4.4-1.fc38.x86_64                                                  
  libstemmer-2.2.0-5.fc38.x86_64                                                
  libthai-0.1.29-4.fc38.x86_64                                                  
  libusb1-1.0.26-2.fc38.x86_64                                                  
  libvorbis-1:1.3.7-7.fc38.x86_64                                               
  libxkbcommon-1.5.0-2.fc38.x86_64                                              
  libxmlb-0.3.14-1.fc38.x86_64                                                  
  low-memory-monitor-2.1-7.fc38.x86_64                                          
  malcontent-libs-0.11.1-1.fc38.x86_64                                          
  mpg123-libs-1.31.3-1.fc38.x86_64                                              
  opus-1.3.1-12.fc38.x86_64                                                     
  ostree-libs-2023.6-1.fc38.x86_64                                              
  p11-kit-server-0.24.1-6.fc38.x86_64                                           
  pango-1.50.14-1.fc38.x86_64                                                   
  pipewire-0.3.83-2.fc38.x86_64                                                 
  pipewire-alsa-0.3.83-2.fc38.x86_64                                            
  pipewire-jack-audio-connection-kit-0.3.83-2.fc38.x86_64                       
  pipewire-jack-audio-connection-kit-libs-0.3.83-2.fc38.x86_64                  
  pipewire-libs-0.3.83-2.fc38.x86_64                                            
  pipewire-pulseaudio-0.3.83-2.fc38.x86_64                                      
  pixman-0.42.2-1.fc38.x86_64                                                   
  polkit-122-3.fc38.1.x86_64                                                    
  polkit-libs-122-3.fc38.1.x86_64                                               
  polkit-pkla-compat-0.1-23.fc38.x86_64                                         
  pulseaudio-libs-16.1-4.fc38.x86_64                                            
  qrencode-libs-4.1.1-4.fc38.x86_64                                             
  rtkit-0.11-58.fc38.x86_64                                                     
  shared-mime-info-2.2-3.fc38.x86_64                                            
  systemd-253.2-1.fc38.x86_64                                                   
  systemd-networkd-253.2-1.fc38.x86_64                                          
  systemd-pam-253.2-1.fc38.x86_64                                               
  systemd-resolved-253.2-1.fc38.x86_64                                          
  webrtc-audio-processing-0.3.1-10.fc38.x86_64                                  
  wireplumber-0.4.15-1.fc38.x86_64                                              
  wireplumber-libs-0.4.15-1.fc38.x86_64                                         
  xdg-dbus-proxy-0.1.4-2.fc38.x86_64                                            
  xdg-desktop-portal-1.16.0-3.fc38.x86_64                                       
  xkeyboard-config-2.38-1.fc38.noarch                                           
  xml-common-0.6.3-60.fc38.noarch                                               

Complete!
COMMIT
--> 0c2136df116a
0c2136df116a16a2ddf642b20206f0e32e62c43afc7c0c2d0ab55c7584ab5322
[tofu@pinkpad toolbox-container]$ toolbox create --image 0c2136df116a16a2ddf642b20206f0e32e62c43afc7c0c2d0ab55c7584ab5322 flatpak
Error: empty RepoTag for image 0c2136df116a16a2ddf642b20206f0e32e62c43afc7c0c2d0ab55c7584ab5322
[tofu@pinkpad toolbox-container]$ toolbox create --image 0c2136df116a16a2ddf642b20206f0e32e62c43afc7c0c2d0ab55c7584ab5322 flatpak^C
[tofu@pinkpad toolbox-container]$ podman
podman       podman-host  
[tofu@pinkpad toolbox-container]$ podman
podman       podman-host  
[tofu@pinkpad toolbox-container]$ podman 
attach       (Attach to a running container)
auto-update  (Auto update containers according to their auto-update policy)
build        (Build an image using instructions from Containerfiles)
commit       (Create new image based on the changed container)
compose      (Run compose workloads via an external provider such as docker-compose or podman-compose)
container    (Manage containers)
cp           (Copy files/folders between a container and the local filesystem)
create       (Create but do not start a container)
diff         (Display the changes to the object's file system)
events       (Show podman system events)
exec         (Run a process in a running container)
export       (Export container's filesystem contents as a tar archive)
generate     (Generate structured data based on containers, pods or volumes)
healthcheck  (Manage health checks on containers)
help         (Help about any command)
history      (Show history of a specified image)
image        (Manage images)
images       (List images in local storage)
import       (Import a tarball to create a filesystem image)
info         (Display podman system information)
init         (Initialize one or more containers)
inspect      (Display the configuration of object denoted by ID)
kill         (Kill one or more running containers with a specific signal)
kube         (Play containers, pods or volumes from a structured file)
[tofu@pinkpad toolbox-container]$ podman tag 0c2136df116a16a2ddf642b20206f0e32e62c43afc7c0c2d0ab55c7584ab5322 flatpak-toolbox
[tofu@pinkpad toolbox-container]$ toolbox create --image flatpak-toolbox flatpak-toolbox
Created container: flatpak-toolbox
Enter with: toolbox enter flatpak-toolbox
[tofu@pinkpad toolbox-container]$ toolbox enter flatpak-toolbox 
⬢[tofu@toolbox toolbox-container]$ flatpak
error: No command specified

See 'flatpak --help'
⬢[tofu@toolbox toolbox-container]$ flatpak --help 
Usage:
  flatpak [OPTION…] COMMAND

Builtin Commands:
 Manage installed applications and runtimes
  install                Install an application or runtime
  update                 Update an installed application or runtime
  uninstall              Uninstall an installed application or runtime
  mask                   Mask out updates and automatic installation
  pin                    Pin a runtime to prevent automatic removal
  list                   List installed apps and/or runtimes
  info                   Show info for installed app or runtime
  history                Show history
  config                 Configure flatpak
  repair                 Repair flatpak installation
  create-usb             Put applications or runtimes onto removable media

 Find applications and runtimes
  search                 Search for remote apps/runtimes

 Manage running applications
  run                    Run an application
  override               Override permissions for an application
  make-current           Specify default version to run
  enter                  Enter the namespace of a running application
  ps                     Enumerate running applications
  kill                   Stop a running application

 Manage file access
  documents              List exported files
  document-export        Grant an application access to a specific file
  document-unexport      Revoke access to a specific file
  document-info          Show information about a specific file

 Manage dynamic permissions
  permissions            List permissions
  permission-remove      Remove item from permission store
  permission-set         Set permissions
  permission-show        Show app permissions
  permission-reset       Reset app permissions

 Manage remote repositories
  remotes                List all configured remotes
  remote-add             Add a new remote repository (by URL)
  remote-modify          Modify properties of a configured remote
  remote-delete          Delete a configured remote
  remote-ls              List contents of a configured remote
  remote-info            Show information about a remote app or runtime

 Build applications
  build-init             Initialize a directory for building
  build                  Run a build command inside the build dir
  build-finish           Finish a build dir for export
  build-export           Export a build dir to a repository
  build-bundle           Create a bundle file from a ref in a local repository
  build-import-bundle    Import a bundle file
  build-sign             Sign an application or runtime
  build-update-repo      Update the summary file in a repository
  build-commit-from      Create new commit based on existing ref
  repo                   Show information about a repo

Help Options:
  -h, --help              Show help options

Application Options:
  --version               Print version information and exit
  --default-arch          Print default arch and exit
  --supported-arches      Print supported arches and exit
  --gl-drivers            Print active gl drivers and exit
  --installations         Print paths for system installations and exit
  --print-updated-env     Print the updated environment needed to run flatpaks
  --print-system-only     Only include the system installation with --print-updated-env
  -v, --verbose           Show debug information, -vv for more detail
  --ostree-verbose        Show OSTree debug information

⬢[tofu@toolbox toolbox-container]$ 
```