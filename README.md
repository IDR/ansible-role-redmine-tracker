IDR submission ticketing system
===============================

[![Build Status](https://github.com/IDR/ansible-role-redmine-tracker/workflows/Build/badge.svg)](https://github.com/IDR/ansible-role-redmine-tracker/actions)

This is an email ticketing system for handling IDR data submissions.
The primary aim is to manage multiple complex email threads concerning data submissions to the IDR.

This role is ***not*** intended to be a generic Redmine role.
A PostgreSQL server is required.


Parameters
----------
- `redmine_tracker_image`: Redmine Docker image
- `redmine_tracker_port`: Publish this port, set to `0` to disable
- `redmine_tracker_db_host`: PostgreSQL host
- `redmine_tracker_db_user`: PostgreSQL user
- `redmine_tracker_db_password`: PostgreSQL password
- `redmine_tracker_db_name`: PostgreSQL database name
- `redmine_tracker_gmail_enabled`: Fetch emails from a Gmail account, default `false`
- `redmine_tracker_gmail_user`: Gmail user
- `redmine_tracker_gmail_password`: Gmail password
- `redmine_tracker_gmail_schedule`: Fetch emails from Gmail on this Cron schedule
- `redmine_tracker_docker_data_volume`: Volume for redmine files


Outputs
-------
This role sets the following variable which can be used in other tasks:
- `redmine_internal_ip`: Internal IP of the Redmine container

These are intended for use when you don't want to expose the container ports using standard Docker port-forwarding (set `redmine_port: 0`).


Example playbook
----------------
See [`molecule/default/playbook.yml`](molecule/default/playbook.yml)


Author Information
------------------

ome-devel@lists.openmicroscopy.org.uk
