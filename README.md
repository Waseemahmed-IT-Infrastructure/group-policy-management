
# Group Policy Management

## Overview

This repository covers Group Policy administration in a Windows Server and Active Directory environment.

Group Policy is used to centrally manage Windows settings, security configurations and user or computer policies.

## Tools

- Group Policy Management Console (GPMC)
- Active Directory Users and Computers
- Windows Server
- Command Prompt
- Event Viewer

## Common Administration Tasks

- Creating and editing Group Policy Objects (GPOs)
- Linking GPOs to Organizational Units (OUs)
- Reviewing user and computer policies
- Managing security filtering
- Checking GPO inheritance
- Troubleshooting policy application issues
- Reviewing policy changes

## Creating and Linking a GPO

1. Open Group Policy Management.
2. Expand the required domain.
3. Navigate to Group Policy Objects.
4. Right-click and select New.
5. Enter a descriptive GPO name.
6. Edit the required policy settings.
7. Link the GPO to the appropriate OU.
8. Verify the scope and security filtering.
9. Test the policy on approved users or computers.

## Group Policy Processing

GPOs can be linked to:

- Sites
- Domains
- Organizational Units

Policy processing generally follows the Local, Site, Domain and OU order.

Inheritance, enforcement, security filtering and WMI filtering can affect the final applied settings.

## Common GPO Settings

Examples include:

- Password and account policies
- Windows Firewall settings
- Screen lock settings
- Network drive mapping
- Printer deployment
- Windows Update configuration
- Desktop and user environment restrictions

## Basic Troubleshooting

Useful commands:

### Refresh Group Policy

    gpupdate /force

### View Applied Policies

    gpresult /r

### Generate a Policy Report

    gpresult /h report.html

The generated report can help identify applied and denied GPOs.

## Troubleshooting Checklist

| Issue | What to Check |
|---|---|
| GPO not applying | OU link, security filtering and policy scope |
| Settings not updated | Policy refresh and client connectivity |
| User policy missing | User OU and filtering |
| Computer policy missing | Computer OU and filtering |
| Conflicting settings | GPO precedence and inheritance |
| Policy processing error | Event Viewer and Group Policy logs |

## Best Practices

- Test new policies before wider deployment.
- Use clear and consistent GPO names.
- Keep documentation of policy changes.
- Review security filtering before deployment.
- Back up GPOs before major changes.
- Avoid modifying production policies without approval.

## Note

This repository contains general technical documentation and illustrative examples. No internal domain names, company configurations or sensitive information are included.
