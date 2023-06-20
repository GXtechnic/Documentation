# Backup & Restore User Data SOP

<br>

## Purpose

* To outline the process for backing up and restoring data on a Linux server. It covers the scope of backing up critical server data and restoring it in case of data loss or system failure. The procedure ensures data integrity and minimizes downtime during the restoration process.

<br>

## Scope

* Establish a standardized and reliable method for performing regular backups and restoring data on a Linux server.

<br>

## Responsibilities

* The IT department at Team Knonsense is responsible for the implementation, maintenance and review of this policy.

<br>

## Prerequisites

* This will only be done by the IT department, following our set SOP.
[SOPs](https://github.com/knonsense/Documentation/tree/dev/SOPs)

<br>

## Procedure

* The procedure below outlines the implementation of a Disk-Based Backup and Restore process. Disks can be added to support customer storage requirements. Backup Storage will contain User endpoint restore point data, Linux Server Veeam Backup and Replication data, and primary storage backup.

**Backup: Disk-based Backup method**

* Identify Critical Data

  * Identify the critical data that needs to be backed up, including configuration files, databases, user files, and other relevant server data.

* Select Backup Type and Schedule

  * Daily Incremental Backups: Perform daily incremental backups to capture changes made to multimedia files and other critical data.

  * Weekly Full Backups: Conduct weekly full backups to capture a complete copy of all multimedia files and relevant data.

  * Hourly Restore points and Snapshotting: Employ backup solutions that support restore points or snapshotting capabilities.

* Regular Testing and Validation

  * Regularly test the backup and restore process to ensure data integrity and the ability to recover data successfully.

<br>

## References

* [Veeam](https://www.veeam.com/linux-cloud-server-backup-agent.html?ad=menu-solutions)

<br>

## Definitions

* **Backup:** the process of creating copies or replicas of digital data to protect against data loss, corruption, or accidental deletion

<br>

## Revision History

* 5/16/2023 - Adrian Mundo

* 5/18/2023 - Raphael Chookagian
