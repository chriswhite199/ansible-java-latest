# Ansible Role - 'java-latest'

Ansible role to keep the latest version of Oracle's JDK installed on the managed hosts.

The role uses a variety of tricks to ascertain that the most current version is:

* Query the Java SE download page
* Scrap the HTML response to find hrefs which contain links to the most recent download page
* Query the most recent download page to identify the link of the *first* linux x64 artifact

Information about the latest download URL is saved off to a file (`/var/lib/java-latest-download`)
and the presence of this file / its timestamp is used to prevent redunant multiple discovery calls.
 
The role (written for RHEL / CentOS) can be configured to install the RPM or tarball version.
 
Check the defaults/main.yml for configurable options for the role
