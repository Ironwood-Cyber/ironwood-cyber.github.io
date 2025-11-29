# How to

This guide walks you through creating the core configuration items your platform needs in order to run assessments effectively.  

Use this when setting up a new workspace, onboarding a new environment, or preparing your system for continuous testing.

---

## Overview

Before an assessment can run successfully, the platform needs:

- **A configuration profile** 
- **Seed elements** (targets, assets, the initial root data) 
- **Sentry Agent** (for internal scans)

This guide explains how to create each one. For more information on each, check out the explanation section.

---

## Creating a configuration profile

Configuration profiles define how the platform behaves when running tests.  
To create one:

1. Go to **Configure** on the left sidebar menu.  
2. Select **Create Configuration** in the Configurations table.  
3. On the first page, enter the Config Name  
4. Set the auto-exploitation level with theh slider. Use the slider to choose which exploitation level you're comfortable with. A low exploitation level will give you light scanning and probing of the network. A high exploitation level will use credentials found and try to move laterally, escalate priviledges in the network, and create shell sessions.
5. Add the **Seed Elements** to the configuration. Click [here](how-to-guides.md/#adding-a-seed-element) to see how to add a seed element.
6. Add any Sentry agents to the config. A Sentry agent is needed to run internal scans on your network. To see how to setup Sentry, click [here](how-to-guides.md/#setting-up-the-sentry-agent). Each agent serves as a launching point to run the assessment tools.
7. Review and create a configuration.

Congrats! Now you have your own setup config to start assessments from!

## Adding a Seed Element

Seed elements are the initial objects you want the platform to use during analysis.  
These can include:

- Domains  
- IP ranges  
- IP subnets
- Global Credentials

For more information on the seed element type, click here.

1. Navigate to the right hand side
2. Under **Add A New Seed Element** select an element.  
3. Choose the element type (e.g., domain, IP, subnet, global credentials).  
4. Either include the seed element in the assessment, or have it excluded from the assessment. This is done when you don't want to assess a larger network for example.
4. Once added, it will create the seed element in the left hand side of the menu.

> **Recommendation:** Start with a small, verified list of seed elements and expand as your system matures. Sometimes you will find new seed elements on an assessment that can be added, such as global credentials.

---

## Setting up the Sentry Agent

The [sentry agent](explanation.md/#sentry-agents) is used for internal perimeter testing.

1. On the left side menu, click on the download icon
2. Download the agent installer and license key
3. Set up the agent installer and license key on the host from which you want to perform an internal assessment from. For example, you can use your own workstation to run a scan on the network that your workstation is on.
4. After installing, the Sentry agent should be live in the Sentry Agents table in the Cofig (Gear Icon) tab.


## Troubleshooting

If something isn’t working, you can reach out to support for [help](https://ironwoodcyber.com/contact).

