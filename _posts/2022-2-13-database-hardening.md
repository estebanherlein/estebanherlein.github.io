---
title: "Database Hardening"
categories:
  - Blog
tags:
  - Cibersecurity
---

Database hardening involves securing both the contents of a digital database and the database management system (DBMS), which is the database application users interact with to store and analyze information within a database.

<h3>Database hardening mainly involves three processes:</h3>
<ol>
<li>Controlling for and limiting user privileges and access</li>
<li>Disabling unnecessary database services and functions</li>
<li>Securing or encrypting database information and resources</li>
</ol>

<h3>Types of database hardening techniques include:</h3>
<ul>
<li>Restricting administrators and administrative privileges and functions</li>
<li>Encrypting in-transit and at-rest database information</li>
<li>Adhering to a role-based access control (RBAC) policy</li>
<li>Regularly updating and patching database software, or the DBMS</li>
<li>Turning off needless database services and functions</li>
<li>Locking database accounts if suspicious login activity is detected</li>
<li>Enforcing strong and more complex database passwords</li>
</ul>


<h3>Firewalls for Database Servers</h3>
<ul>
<li>The database server is located behind a firewall with default rules to deny all traffic.</li>
<li>The database server firewall is opened only to specific application or web servers, and firewall rules do not allow direct client access.   If the development environment cannot meet this requirement, then protected data is not stored in the development database server and mock data is made up for development.  Data obfuscation of production data is not sufficient.</li>
<li>Firewall rule change control procedures are in place and notification of rule changes are distributed to System Administrators (SAs) and Database Administrators (DBAs).</li>
<li>Firewall rules for database servers are maintained and reviewed on a regular basis by SAs and DBAs. If using the IST provided firewall service, the rules are also regularly reviewed by the Information Security Office (ISO).</li>
<li>Regularly test machine hardening and firewall rules via network scans, or by allowing ISO scans through the firewall.</li>
</ul>

<h3>Protected Data</h3>
<ul>
<li>Only the protected data required for the business function is kept within the database. When possible, historical information is purged when no longer required.</li>
<li>Redundancy of protected data is eliminated throughout the system, and shadowing of protected data outside the system of record is avoided wherever possible. Hashing functions are applied to protected data elements before storing if the data is only required for matching purposes. If possible, disassociate protected data from personally identifiable information and keep offline until needed. If data transfers are required for other applications, notify them of protected data and its security requirements.</li>
<li>Protected data in non-production environments is held to the same security standards as production systems. In cases where non-production environments are not held to the same security standard as required in production, data in these non-production environments must either be encrypted using industry-standard algorithms, or else test data must be made up for these systems. Data obfuscation is not sufficient.</li>
<li>The protected data elements within the database are documented.
    Protected data is never used as a key in a table.</li>
</ul>

<h3>Change Management</h3>
<ul>
<li>Change management procedures are documented and meet the data proprietor’s requirements.</li>
<li>Change management controls are in place to log all changes to the production database.</li>
<li>All programs scheduled to run against the database which read or modify production data are documented. </li>
</ul>

<h3>Database Encryption & Key Management</h3>
<ul>
<li>Protected data is encrypted during transmission over the network using encryption measures strong enough to minimize the risk of the data’s exposure if intercepted or misrouted from database to client workstation.</li>
<li>If database-level encryption for protected data is implemented, procedures for secure key management are documented. (Check National Institute of Standards and Technology (NIST) for current recommendations.) Note: It is recommended that all application layers (network, application, client workstation) are already encrypted before encrypting the database. Database encryption is not a substitute for any of the above requirements. Database encryption of protected data is not mandatory to meet this standards document.</li>
<li>For data subject to disclosure that is encrypted at storage, the means to decrypt must be available to more than one person and approved by the data proprietor.</li>
<li>Backup tapes store backups of the database in an encrypted format, and the tapes do not store the plain text encryption keys necessary to decrypt the backups.</li>
<li>Key management procedures for decrypting backups are documented, available to more than one person and approved by the data proprietor. </li>
</ul>
