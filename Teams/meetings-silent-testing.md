---
title: Meetings Silent Testing 
ms.author: guypaskar
author: PeerDiego
manager: hadarweiss
f1.keywords:
- NOCSH
audience: Admin
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- Hybrid
- M365-email-calendar
ms.date: 08/01/2025
description: "You're reading instructions on the benefits of Meetings Silent Testing."
--- 

# Silent Test Call -- Admin Guide

## Overview

**Silent Test** **Call** feature allows IT Admins of Microsoft Teams to
schedule and simulate a test call between users of a subnet in their
organization and Microsoft Calling Servers. It enables proactive
monitoring of call quality and network monitoring by having these calls
run according to the schedule set silently in the background without
interrupting users. Once the calls are run, IT Admins can view a report
detailing call quality and potential issues so proactive measures can be
taken to help improve end user calling and meeting experience.

### Why Silent Test?

Existing monitoring tools (CQD, Real-Time Monitoring, Alerts) are
reactive; they detect issues after users experience them. Silent Test
Call offers **proactive monitoring**, allowing IT teams to detect and
address network issues before they affect users.

Imagine scenarios such as:

- **Network Changes**: You have updated your network firewall rules or
  Wi-Fi configurations. Running Silent Test Calls helps validate
  performance proactively before users report issues.

- **New Location Setup**: You are launching a new office location. Even
  with only a few Teams clients available, Silent Tests can provide
  early indicators of network readiness.

- **Routine Health Checks**: Scheduling daily or weekly Silent Tests
  allows continuous monitoring to catch degradations early, reducing the
  risk of outages impacting end users.

By integrating Silent Test Calls into your operational routines, you can
detect and resolve potential issues proactively, ensuring better
reliability and user satisfaction.

**Key Points:**

- Tests run silently in the background on the Teams client at scheduled
  times.

- Test runs for 60 seconds on user's machine in the background.

- Tests are targeted at a specific subnet.

- Test will run only on Desktop client - Windows and MAC

- Tests only run if the device is idle (user is not in an active Teams
  call).

- No user experience disruption: no notifications, sounds, or visible
  changes.

**Endpoint Requirements:**

- Device must be located in the targeted subnet.

- Teams' client must be installed and running.

- Device must be powered ON.

- User must not be on an active Teams call.

- Teams user signed in to the device must have a Teams Premium license.

## How to Schedule a Silent Test Call

Silent Test Calls can be scheduled via the **Teams Admin Center (TAC)**:

To schedule test you must be either Global Admin or Teams Admin role.

1. Open **Teams Admin Center**.

2. Navigate to **Analytics & Reports** → **Silent Test Calls**.

3. Click **Schedule Test**.

4. Fill out the form:

    - Subnet ID; multiple subnets can be entered comma separated. Subnet
      IDs must be in valid CIDR format. E.g. 192.168.1.0/24. Only IPv4
      is currently supported.

    - Frequency (One-time, Daily, Weekly, etc.)

    - Start date and time

5. Save the schedule.

6. View scheduled tests at the bottom of the page. You can **edit** or
    **abort** existing schedules if necessary.

:::image type="content" source="./images/doppler/silent-testing-summary.png" alt-text="A screenshot of the Silent Testing summary page.":::

:::image type="content" source="./images/doppler/silent-testing-scheduling.png" alt-text="A screenshot of the Silent Testing scheduling feature.":::

[\[TO Do\] update screen shot with Flat Table]{.mark}

## How to View Silent Test Reports

On the silent test call, click on Download Report button to download a
Power BI report file.

Once at test is completed, open the Power BI report, Login with your
Admin credentials and choose the subnet/test name to view a report.

If you haven't set up PowerBI, please use the instruction below to set
it up:

### Set Up Instructions

- Download and configure using:

  - [Set up CQD Power BI
    Connector](https://learn.microsoft.com/en-us/microsoftteams/cqd-power-bi-connector)

  - [CQD Power BI Query
    Templates](https://learn.microsoft.com/en-us/microsoftteams/cqd-power-bi-query-templates)

Reports

When you first open the Power BI report, you'll see an overview of your
results from using Silent Test Calls.

:::image type="content" source="./images/doppler/silent-test-summary.png" alt-text="A screenshot of a Silent Test report":::

As you click on data points such as subnet or building name, the report
will change to reflect that scope.

:::image type="content" source="./images/doppler/silent-test-summary-filtered.png" alt-text="A screenshot of a filtered Silent Test report.":::

## Licensing Details

- Silent Test Call will be a **Teams Premium feature** at General
  Availability (GA).

- **During private preview, there will be NO license enforcement**.

- All participating tenants can access and schedule Silent Test Calls
  regardless of Teams Premium licensing during preview.
