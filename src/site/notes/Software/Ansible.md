---
{"dg-publish":true,"permalink":"/software/ansible/","tags":["Software"],"dg-note-properties":{"tags":["Software"],"source":"personal_notes","last_updated":"2026-05-05"}}
---


#Software

Ansible is an IT automation and configuration management tool. At Promega, [[People/Adam Bellin\|Adam Bellin]] is using it to build a modular PCS (Process Control System) configuration automation system.

The system models the PCS using profiles and groups. Each profile defines the roles and characteristics of a system component, such as acting as an HMI client, a VM running specific software, or a primary or secondary server. Components can belong to multiple profiles. Dependencies between components are defined manually and allow the system to understand what downstream effects a given action will have at runtime.

As of April 2026, IT has built a dedicated server with remote access into the dev PCS. Capabilities include rebooting servers, starting servers, installing software, taking switch configuration backups, and running command-line commands on any PCS server from a central location.

Documentation fed into the system includes the SCADA DS, network architecture drawings, network schema, and switch configurations. The long-term goal is a living configuration document describing the full PCS state that can be run to verify the system matches the desired state, or automatically correct it if it does not.

[[People/Adam Bellin\|Adam Bellin]] built this configuration using [[Claude Code\|Claude Code]].

> [!info]- Details & Notes
>
> **See also:** [[People/Adam Bellin\|Adam Bellin]], [[Definitions/Operations Engineering\|Operations Engineering]]
