The System Security Services Daemon (SSSD) is a system service to access remote directories and authentication mechanisms. The following chapters outline how SSSD works, what are the benefits of using it, how the configuration files are processed, as well as what identity and authentication providers you can configure.

How SSSD works?
The System Security Services Daemon (SSSD) is a system service that allows you to access remote directories and authentication mechanisms. You can connect a local system, an SSSD client, to an external back-end system, a provider.

For example:
An LDAP directory
An Identity Management (IdM) domain
An Active Directory (AD) domain
A Kerberos realm
SSSD works in two stages:

It connects the client to a remote provider to retrieve identity and authentication information.
It uses the obtained authentication information to create a local cache of users and credentials on the client.
Users on the local system are then able to authenticate using the user accounts stored in the remote provider.

SSSD does not create user accounts on the local system. However, SSSD can be configured to create home directories for IdM users. Once created, an IdM user home directory and its contents on the client are not deleted when the user logs out.

Fail to start SSSD process or how to troubleshoot sssd>

SSSD service can fail to start due to multiple reasons. i.e:
1] Check for any typos in sssd configuration files especially under /etc/sssd/conf.d/ directory and in /etc/sssd/sssd.conf
2] Correct the typos and restart sssd service. If it fails, try removing any customized sssd configuration under /etc/sssd/conf.d/ directory.
3]  Detailed information can be obtained by running SSSD in daemon mode with debug using `sssd -i d9` command
