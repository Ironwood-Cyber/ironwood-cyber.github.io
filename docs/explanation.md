# Understanding Configurations, Seed Elements, and Sentry Setup

This page explains the concepts behind configurations, seed elements, scope definitions, and the setup process used within the platform. 

If you’ve already read the how-to guide, this page helps you understand *why* those steps exist and how they fit together.

---


That Enlight™  model is shaped by two core concepts:

1. **Configurations** – How you want Enlight™  to run an assessment 
2. **Seed elements** – The starting element that Enlight™  uses to start performing assessments

---

## Configs: Enlight™ 's blueprint

A configuration is a blueprint that kicks off an assessment.

It determines:

- How aggressive scanning can be (sets exploitation levels)
- Seed elements to kick off from 

Think of a configuration as the settings that you can create for different type of assessments.

**Why this matters:**  
Different environments require different testing behaviors.  
Production systems might need strict resource limits, while internal sandbox environments can tolerate deeper testing.  
Configurations let you control this balance.

---

## Seed Elements

Seed elements are the initial pieces of information that Enlight™  uses to understand your attack surface.

Common seed elements include:

- Domain names
- IP Subnets
- IP Addresses  
- Global credentials


From these seeds, the platform expands outward, mapping the environment and identifying related assets.

### Domain names

These are used for external perimeter assessments. These are domain names like [yourcompany].com which are checked in our perimeter scan for security findings.

### IP subnets

These are available subnets that you want assessed within an internal assessment. When this is selected, Enlight™  will run an assessment on the whole known network.

### IP address

This is the individual host that you want to run an assessment on. When this is selected, Enlight™  will kick off assessments at the host level and from there, see if it can map out other relationships and findings within the network.

### Global Credentials

Global Credentials are creds that can be used by Enlight™  to further exploit and run deeper assessments against an asset. For example, you can provide a credential like u: admin and p: password that is reused across the assessment. The purpose of providing a global credential, whether with privs or not, is to better understand the attack surface if an attacker was to compromise accounts/gain a foothold/etc. 

When credentials are found in the assessment, they create more global credential seed elements which can then be used for additional checks. All autonomously.

**Why this matters:**  

A single seed element can reveal dozens or hundreds of related assets. Enlight™  will be able to find related assets, but more seed elements mean a more comprehensive exploration surface. 

On the other end, incorrect or missing seeds can lead to incomplete analysis or irrelevant targets.

Seed elements directly impact assessments. For example, if you have a seed element on a subnet in 10.0.0.1, but there is only one host there...that's all you'll see. 

---


## Credentials and Environment Data: Understanding Authenticated Context

Many modern applications require authentication for meaningful testing.

Providing credentials allows the platform to:

- Traverse authenticated areas  
- Assess authorization controls  
- Validate role-based access 

These credentials never change the nature of the testing; they simply give the engine the visibility it needs.

**Why this matters:**  

Unauthenticated testing only shows one layer of risk.  
Authenticated testing reveals deeper, more realistic attack paths.

---

## Sentry Agents

Sentry agents are created by Ironwood Cyber to facilitate secure internal assessments from our cloud Enlight™  engine. Each agent registers with a license and establishes a authenticated session with our cloud services.

**Why this matters:**  

External perimeter assessments are nice, but you can only truly understand your attack surface with an internal overview. Sentry helps accomplish this.


## How These Components Work Together

You can think of the system like a security “recipe”

1. **Configurations** → Recipe to let Enlight™  cook 
2. **Seed elements** → What ingredients to use  
3. **Sentry Agent (for internal)** → Additional utensils needed to move the ingredients

(and if going off that analogy, Enlight™  would be the chef!)

None of these pieces is useful alone; they gain value when combined.

Together, they form a coherent, governed testing experience.


---

## Summary

Configurations and seed elements are not “setup tasks.”  

They are the foundation of how the platform understands your environment. Understanding these concepts helps you shape assessments that are accurate, safe, and aligned with real operational needs.

