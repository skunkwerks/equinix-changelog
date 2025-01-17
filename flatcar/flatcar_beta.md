# Changelog for flatcar_3745.1.0_beta
_Changes since **Beta 3732.1.0**_
 
 #### Security fixes:
 
 - curl ([CVE-2023-38039](https://nvd.nist.gov/vuln/detail/CVE-2023-38039), [CVE-2023-38545](https://nvd.nist.gov/vuln/detail/CVE-2023-38545), [CVE-2023-38546](https://nvd.nist.gov/vuln/detail/CVE-2023-38546))
 - glibc ([CVE-2023-4527](https://nvd.nist.gov/vuln/detail/CVE-2023-4527), [CVE-2023-4806](https://nvd.nist.gov/vuln/detail/CVE-2023-4806))
 - lua ([CVE-2022-33099](https://nvd.nist.gov/vuln/detail/CVE-2022-33099))
 - mit-krb5 ([CVE-2023-36054](https://nvd.nist.gov/vuln/detail/CVE-2023-36054))
 - procps ([CVE-2023-4016](https://nvd.nist.gov/vuln/detail/CVE-2023-4016))
 - samba ([CVE-2021-44142](https://nvd.nist.gov/vuln/detail/CVE-2021-44142), [CVE-2022-1615](https://nvd.nist.gov/vuln/detail/CVE-2022-1615))
 
 #### Bug fixes:
 
 - Disabled systemd-networkd's RoutesToDNS setting by default to fix provisioning failures observed in VMs with multiple network interfaces on Azure ([scripts#1206](https://github.com/flatcar/scripts/pull/1206))
 - Fixed the postinstall hook failure when updating from Azure instances without OEM systemd-sysext images to Flatcar Alpha 3745.x.y ([update_engine#29](https://github.com/flatcar/update_engine/pull/29))
 
 #### Changes:
 
 - AWS OEM images now use a systemd-sysext image for layering additional platform-specific software on top of `/usr`
 - Reworked the VMware OEM software to be shipped as A/B updated systemd-sysext image
 - SDK: Experimental support for [prefix builds](https://github.com/flatcar/scripts/blob/main/PREFIX.md) to create distro independent, portable, self-contained applications w/ all dependencies included. With contributions from [chewi](https://github.com/chewi) and [HappyTobi](https://github.com/HappyTobi).
 - Started shipping default ssh client and ssh daemon configs in `/etc/ssh/ssh_config` and `/etc/ssh/sshd_config` which include config snippets in `/etc/ssh/ssh_config.d` and `/etc/ssh/sshd_config.d`, respectively.
 - The open-vm-tools package in VMware OEM now comes with vmhgfs-fuse, udev rules, pam and vgauth
 - To make Kubernetes work by default, `/usr/libexec/kubernetes/kubelet-plugins/volume/exec` is now a symlink to the writable folder `/var/kubernetes/kubelet-plugins/volume/exec` ([Flatcar#1193](https://github.com/flatcar/Flatcar/issues/1193))
 
 #### Updates:
 
 - Linux ([6.1.58](https://lwn.net/Articles/947820) (includes [6.1.57](https://lwn.net/Articles/947298), [6.1.56](https://lwn.net/Articles/946854)))
 - Linux Firmware ([20230919](https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/tag/?h=20230919))
 - bind-tools ([9.16.42](https://bind9.readthedocs.io/en/v9.16.42/notes.html#notes-for-bind-9-16-42))
 - ca-certificates ([3.94](https://firefox-source-docs.mozilla.org/security/nss/releases/nss_3_94.html))
 - checkpolicy ([3.5](https://github.com/SELinuxProject/selinux/releases/tag/3.5))
 - curl ([8.3.0](https://curl.se/changes.html#8_3_0))
 - gcc ([13.2](https://gcc.gnu.org/gcc-13/changes.html))
 - gzip ([1.13](https://savannah.gnu.org/news/?id=10501))
 - libgcrypt ([1.10.2](https://git.gnupg.org/cgi-bin/gitweb.cgi?p=libgcrypt.git;a=blob;f=NEWS;h=c9a239615f8070427a96688b1be40a81e59e9b8a;hb=1c5cbacf3d88dded5063e959ee68678ff7d0fa56))
 - libselinux ([3.5](https://github.com/SELinuxProject/selinux/releases/tag/3.5))
 - libsemanage ([3.5](https://github.com/SELinuxProject/selinux/releases/tag/3.5))
 - libsepol ([3.5](https://github.com/SELinuxProject/selinux/releases/tag/3.5))
 - lua ([5.4.6](https://www.lua.org/manual/5.4/readme.html#changes))
 - mit-krb5 ([1.21.2](http://web.mit.edu/kerberos/krb5-1.21/))
 - openssh ([9.4p1](https://www.openssh.com/releasenotes.html#9.4p1))
 - policycoreutils ([3.5](https://github.com/SELinuxProject/selinux/releases/tag/3.5))
 - procps ([4.0.4](https://gitlab.com/procps-ng/procps/-/releases/v4.0.4) (includes [4.0.3](https://gitlab.com/procps-ng/procps/-/releases/v4.0.3) and [4.0.0](https://gitlab.com/procps-ng/procps/-/releases/v4.0.0)))
 - rpcsvc-proto ([1.4.4](https://github.com/thkukuk/rpcsvc-proto/releases/tag/v1.4.4))
 - samba ([4.18.4](https://wiki.samba.org/index.php/Samba_4.18_Features_added/changed#Samba_4.18.4))
 - selinux-base ([2.20221101](https://github.com/SELinuxProject/refpolicy/releases/tag/RELEASE_2_20221101))
 - selinux-base-policy ([2.20221101](https://github.com/SELinuxProject/refpolicy/releases/tag/RELEASE_2_20221101))
 - selinux-container ([2.20221101](https://github.com/SELinuxProject/refpolicy/releases/tag/RELEASE_2_20221101))
 - selinux-sssd ([2.20221101](https://github.com/SELinuxProject/refpolicy/releases/tag/RELEASE_2_20221101))
 - selinux-unconfined ([2.20221101](https://github.com/SELinuxProject/refpolicy/releases/tag/RELEASE_2_20221101))
 - semodule-utils ([3.5](https://github.com/SELinuxProject/selinux/releases/tag/3.5))
 - SDK: Rust ([1.72.1](https://github.com/rust-lang/rust/releases/tag/1.72.1))
 - VMWARE: libdnet ([1.16.2](https://github.com/ofalk/libdnet/releases/tag/libdnet-1.16.2) (includes [1.16](https://github.com/ofalk/libdnet/releases/tag/libdnet-1.16)))

 _Changes since **Alpha 3745.0.0**_
 
 #### Security fixes:
 
 - curl ([CVE-2023-38545](https://nvd.nist.gov/vuln/detail/CVE-2023-38545), [CVE-2023-38546](https://nvd.nist.gov/vuln/detail/CVE-2023-38546))
 
 #### Bug fixes:
 
 - Disabled systemd-networkd's RoutesToDNS setting by default to fix provisioning failures observed in VMs with multiple network interfaces on Azure ([scripts#1206](https://github.com/flatcar/scripts/pull/1206))
 - Fixed the postinstall hook failure when updating from Azure instances without OEM systemd-sysext images to Flatcar Alpha 3745.x.y ([update_engine#29](https://github.com/flatcar/update_engine/pull/29))
 
 #### Changes:
 
 - To make Kubernetes work by default, `/usr/libexec/kubernetes/kubelet-plugins/volume/exec` is now a symlink to the writable folder `/var/kubernetes/kubelet-plugins/volume/exec` ([Flatcar#1193](https://github.com/flatcar/Flatcar/issues/1193))
 
 #### Updates:
 
 - Linux ([6.1.58](https://lwn.net/Articles/947820) (includes [6.1.57](https://lwn.net/Articles/947298), [6.1.56](https://lwn.net/Articles/946854)))
 - ca-certificates ([3.94](https://firefox-source-docs.mozilla.org/security/nss/releases/nss_3_94.html))# Changelog for flatcar_3602.1.6_beta
 _Changes since **Beta 3602.1.5**_
 
 #### Changes:
 
 - Azure: Add support for Microsoft Azure Network Adapter (MANA) NICs on Azure ([scripts#1131](https://github.com/flatcar/scripts/pull/1131))
 
 #### Updates:
 
 - Linux ([5.15.132](https://lwn.net/Articles/944877) (includes [5.15.131](https://lwn.net/Articles/943755), [5.15.130](https://lwn.net/Articles/943404)))
 - ca-certificates ([3.93](https://firefox-source-docs.mozilla.org/security/nss/releases/nss_3_93.html))# Changelog for flatcar_3602.1.5_beta
 _Changes since **Beta 3602.1.4**_
 
 #### Security fixes:
 
 - Linux ([CVE-2022-40982](https://nvd.nist.gov/vuln/detail/CVE-2022-40982), [CVE-2022-41804](https://nvd.nist.gov/vuln/detail/CVE-2022-41804), [CVE-2023-20569](https://nvd.nist.gov/vuln/detail/CVE-2023-20569), [CVE-2023-20588](https://nvd.nist.gov/vuln/detail/CVE-2023-20588), [CVE-2023-40283](https://nvd.nist.gov/vuln/detail/CVE-2023-40283), [CVE-2023-4128](https://nvd.nist.gov/vuln/detail/CVE-2023-4128), [CVE-2023-23908](https://nvd.nist.gov/vuln/detail/CVE-2023-23908))
 
 #### Bug fixes:
 
 - Fixed the restart of Systemd services when the main process is being killed by a SIGHUP signal ([flatcar#1157](https://github.com/flatcar/Flatcar/issues/1157))
 
 #### Updates:
 
 - Linux ([5.15.129](https://lwn.net/Articles/943113) (includes [5.15.128](https://lwn.net/Articles/942866), [5.15.127](https://lwn.net/Articles/941775), [5.15.126](https://lwn.net/Articles/941296), [5.15.125](https://lwn.net/Articles/940801)))# Changelog for flatcar_3602.1.4_beta
 _Changes since **Beta 3602.1.3**_
 
 #### Security fixes:
 
 - Linux ([CVE-2022-48502](https://nvd.nist.gov/vuln/detail/CVE-2022-48502), [CVE-2023-20593](https://nvd.nist.gov/vuln/detail/CVE-2023-20593), [CVE-2023-2898](https://nvd.nist.gov/vuln/detail/CVE-2023-2898), [CVE-2023-31248](https://nvd.nist.gov/vuln/detail/CVE-2023-31248), [CVE-2023-35001](https://nvd.nist.gov/vuln/detail/CVE-2023-35001), [CVE-2023-3611](https://nvd.nist.gov/vuln/detail/CVE-2023-3611), [CVE-2023-3776](https://nvd.nist.gov/vuln/detail/CVE-2023-3776), [CVE-2023-38432](https://nvd.nist.gov/vuln/detail/CVE-2023-38432), [CVE-2023-3863](https://nvd.nist.gov/vuln/detail/CVE-2023-3863))
 - OpenSSH ([CVE-2023-38408](https://nvd.nist.gov/vuln/detail/CVE-2023-38408))
 - linux-firmware ([CVE-2023-20593](https://nvd.nist.gov/vuln/detail/CVE-2023-20593))

 #### Updates:
 
 - Linux ([5.15.124](https://lwn.net/Articles/940339) (includes [5.15.123](https://lwn.net/Articles/939424), [5.15.122](https://lwn.net/Articles/939104), [5.15.121](https://lwn.net/Articles/939016)))
 - ca-certificates ([3.92](https://firefox-source-docs.mozilla.org/security/nss/releases/nss_3_92.html))
 - linux-firmware ([20230625](https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/tag/?h=20230625))
# Changelog for flatcar_3602.1.3_beta
 _Changes since **Beta 3602.1.2**_

 #### Updates:
 
 - Linux ([5.15.120](https://lwn.net/Articles/937404))# Changelog for flatcar_3602.1.2_beta
 _Changes since **Beta 3602.1.1**_
 
 #### Security fixes:
 
 - Linux ([CVE-2023-3338](https://nvd.nist.gov/vuln/detail/CVE-2023-3338), [CVE-2023-3390](https://nvd.nist.gov/vuln/detail/CVE-2023-3390))
 
 #### Bug fixes:
 
 - Ensured that the folder `/var/log/sssd` is created if it doesn't exist, required for `sssd.service` ([Flatcar#1096](https://github.com/flatcar/Flatcar/issues/1096))
 - Worked around a bash regression in `flatcar-install` and added error reporting for disk write failures ([Flatcar#1059](https://github.com/flatcar/Flatcar/issues/1059))
 
 #### Changes:
 
 - Changed ext4 inode size of root partition to 256 bytes. This improves compatibility with applications and is necessary for 2038 readiness ([Flatcar#1082](https://github.com/flatcar/Flatcar/issues/1082))
 
 #### Updates:
 
 - Linux ([5.15.119](https://lwn.net/Articles/936675) (includes [5.15.118](https://lwn.net/Articles/935584)))
 - ca-certificates ([3.91](https://firefox-source-docs.mozilla.org/security/nss/releases/nss_3_91.html))