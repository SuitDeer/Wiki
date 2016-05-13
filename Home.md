# OCS Inventory NG 2.x Documentation

To make it easier to read, the OCS Inventory NG documentation has been divided into 10 sections.

## Newbie documentation

* [OCS Inventory NG in 2 pages - Basics](1.Newbie-documentation/OCS-Inventory-NG-Basics.md)

## Basic documentation

* [Setting up a management server](2.Basic-documentation/Setting-up-a-management-server.md)
* [Setting up the UNIX agent on client computers](2.Basic-documentation/Setting-up-the-UNIX-agent-on-client-computers.md)
* [Setting up the Windows Agent 2.X on client computers](2.Basic-documentation/Setting-up-the-Windows-Agent-2.x-on-client-computers.md)
* [Setting up the MacOSX agent on client computers](2.Basic-documentation/Setting-up-the-MacOSX-agent-on-client-computers.md)
* [Setting up the Android Agent](2.Basic-documentation/Setting-up-the-Android-Agent.md)
* [Administration of OCS Inventory NG](2.Basic-documentation/Administration-of-OCS-Inventory-NG.md)

## Management console and its advanced features

* [Querying inventory results](3.Management-console-and-its-advanced-features/Querying-inventory-results.md)
* [Using computers groups](3.Management-console-and-its-advanced-features/Using-computers-groups.md)
* [Using the Plugins feature](3.Management-console-and-its-advanced-features/Using-the-Plugins-feature.md)
* [Managing users profiles of the web interface](3.Management-console-and-its-advanced-features/Managing-users-profiles-of-the-web-interface.md)
* [Managing administrative data](3.Management-console-and-its-advanced-features/Managing-administrative-data.md)
* [Synchronization between OCS and LDAP](3.Management-console-and-its-advanced-features/Synchronization-between-OCS-and-LDAP.md)
* [Export a computer](3.Management-console-and-its-advanced-features/Export-a-computer.md)

## Deployment

* [Deploying packages or executing commands on client hosts](4.Deployment/Deploying-packages-or-executing-commands-on-client-hosts.md)

## Network Discovery with OCS Inventory NG

* [Using IP discovery feature](5.Network-Discovery-with-OCS-Inventory-NG/Using-IP-discovery-feature.md)
* [Using SNMP scan feature](5.Network-Discovery-with-OCS-Inventory-NG/Using-SNMP-scan-feature.md)

## OCS Tools

* [OCS Inventory NG Agent Deployement Tool](6.OCS-Tools/OCS-Inventory-NG-Agent-Deployement-Tool.md)
* [OCS Packager](6.OCS-Tools/OCS-Packager.md)
* [OCS Packager for MacOSX](6.OCS-Tools/OCS-Packager-for-MacOSX.md)
* [Uninstall Windows Agent](6.OCS-Tools/Uninstall-Windows-Agent.md)

## Multi-site network architecture

* [Using redistribution servers](7.Multi-site-network-architecture/Using-redistribution-servers.md)
* [Using local proxy cache to deploy](7.Multi-site-network-architecture/Using-local-proxy-cache-to-deploy.md)
* [Synchronisation between OCS server master/slaves](7.Multi-site-network-architecture/Synchronisation-between-OCS-server-master-slaves.md)

## Extras

* [Secure your OCS Inventory NG Server](8.Extras/Secure-your-OCS-Inventory-NG-Server.md)
* [Management server tuning](8.Extras/Management-server-tuning.md)
* [Backup/restore of OCS Inventory NG database ](8.Extras/Backup-restore-of-OCS-Inventory-NG-database.md)
* [Common errors](8.Extras/Common-errors.md)

## Howtos



## Developers

* [Unified backend 2.0](10.Developers/Unified-backend-2.0.md)
* [Unified standalone](10.Developers/Unified-standalone.md)
* [Unified OSX](10.Developers/Unified-OSX.md)
* [Web services](10.Developers/Web-services.md)
* [SNMP tables in ocsweb database](10.Developers/SNMP-tables-in-ocsweb-database.md)
* [Linux Storage](10.Developers/Linux-Storage.md)
* [Linux Storage 3ware](10.Developers/Linux-Storage-3ware.md)
* [XML-Format](10.Developers/XML-Format.md)
* [Data Filter](10.Developers/Data-Filter.md)
* [Enhance database using type tables](10.Developers/Enhance-database-using-type-tables.md)
* [HOWTO package OCS Unix server releases](10.Developers/HOWTO-package-OCS-Unix-server-releases.md)
* [HOWTO package OCS Unix agent releases](10.Developers/HOWTO-package-OCS-Unix-agent-releases.md)
* [HOWTO package OCS MacOSX agent releases](10.Developers/HOWTO-package-OCS-MacOSX-agent-releases.md)
* [HOWTO package OCS Windows server releases](10.Developers/)
* [HOWTO update language file](10.Developers/HOWTO-update-language-file.md)
* [HOWTO export accountinfo data](10.Developers/HOWTO-export-accountinfo-data.md)
* [Unified Agent 2.x](10.Developers/Unified-Agent-2.x.md)
* [UTF-8 migration plan](10.Developers/UTF-8-migration-plan.md)
* [Meetings:About SNMP](10.Developers/Meetings:AboutSNMP.md)

# FAQ

* Ipdiscover works fine but I have no SNMP data up in my OCS Inventory NG server ?

    **Solution**: SNMP is not currently implemented in Windows agent. It will work in future version. You can use the unix agent instead to retrieve SNMP data.

* Can I upgrade my server from version X to the last stable version ?

    **Solution**: Yes of course! All old versions can be upgrade to the latest version without problem.

* After installing the server, I go to the graphical admin console (GUI) and it asks me to install the database ?

    **Solution**: The database is installed on the first access to the graphical admin console (GUI).

* What URL must I put in the agent to contact the server ?

    **Solution**: The URL must be in this form http://dns_or_ip/ocsinventory. It is recommended that you use DNS instead of IP.

* ocsinventory directory does not exist on my server

    **Solution**: ocsinventory is a virtual directory call by mod_perl in apache. ocsinventory directory must not exist.

* Fatal error: main() [<a href='function.main'>function.main</a>]: The script tried to execute a method or access a property of an incomplete object. Please ensure that the class definition "language" of the object you are trying to operate on was loaded _before_ unserialize() gets called or provide a __autoload() function to load the class definition in /usr/share/ocsinventory-reports/ocsreports/install.php on line 29

    **Solution**: Edit the php.ini file and change the value of session_auto_start from 1 to 0. Save and restart apache.

* Error 500 :

    **Solution**: OCS engine can't comunicate with mysql server. Probably due to a wrong mysql account. You have to check z-ocsinventory-server.conf (ocsinventory-server.conf on Windows Server), exactly theses few lines

        # Master Database settings
          # Replace localhost by hostname or ip of MySQL server for WRITE
          PerlSetEnv OCS_DB_HOST localhost
          # Replace 3306 by port where running MySQL server, generally 3306
          PerlSetEnv OCS_DB_PORT 3306
          # Name of database
          PerlSetEnv OCS_DB_NAME ocsweb
          PerlSetEnv OCS_DB_LOCAL ocsweb
          # User allowed to connect to database
          PerlSetEnv OCS_DB_USER ocs
          # Password for user
          PerlSetVar OCS_DB_PWD ocs

    Modify **OCS_DB_USER** and **OCS_DB_PWD** with your own account, restart apache, and finaly launch an inventory.

* Error 417 :

    **Solution** : insert ignore_expect_100 on into your squid.conf file and then run squid -k reconfigure.