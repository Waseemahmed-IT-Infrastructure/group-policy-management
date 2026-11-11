
# Group Policy Troubleshooting Guide

## Overview

This document covers common Group Policy issues and basic troubleshooting steps in a Windows Active Directory environment.

## 1. GPO Not Applying

If a Group Policy is not applying to a user or computer:

1. Open Group Policy Management Console (GPMC).
2. Check whether the GPO is linked to the correct OU.
3. Verify that the GPO link is enabled.
4. Review security filtering and permissions.
5. Check whether the relevant user or computer settings are enabled.
6. Review inheritance and GPO precedence.

## 2. Refresh Group Policy

Open Command Prompt and run:

    gpupdate /force

This requests a Group Policy refresh.

Some settings may require signing out or restarting the computer.

## 3. Check Applied Policies

Run:

    gpresult /r

This displays a summary of applied Group Policy information.

To generate a detailed HTML report:

    gpresult /h report.html

Open the report to review applied and denied GPOs.

Run Command Prompt with appropriate permissions when checking computer policies.

## 4. Check OU and Security Filtering

Verify:

- The user or computer is in the correct OU.
- The GPO is linked to the appropriate location.
- Security filtering allows the intended objects to apply the policy.
- WMI filtering is not excluding the computer.
- The GPO or relevant link is not disabled.

## 5. Check Domain Connectivity

Group Policy processing can depend on communication with domain controllers.

Check:

- Network connectivity
- DNS configuration
- Domain controller availability
- Domain authentication
- Time synchronization

## 6. Review Event Viewer

1. Open Event Viewer.
2. Navigate to Applications and Services Logs.
3. Open Microsoft > Windows > GroupPolicy > Operational.
4. Review relevant errors and warnings.
5. Compare event times with the policy refresh attempt.

## Common Issues

| Issue | Initial Check |
|---|---|
| GPO not applying | OU link and security filtering |
| Policy update fails | Domain connectivity and DNS |
| User settings missing | User OU and policy configuration |
| Computer settings missing | Computer OU and policy configuration |
| Unexpected policy settings | GPO precedence and inheritance |
| Policy processing errors | Group Policy Operational log |

## Best Practices

- Test policy changes on approved test users or computers.
- Document changes before deployment.
- Back up important GPOs.
- Avoid changing production policies without approval.
- Confirm the result after troubleshooting.

## Note

This is a general troubleshooting guide. Commands and procedures should be used according to the organization's change management policies.
