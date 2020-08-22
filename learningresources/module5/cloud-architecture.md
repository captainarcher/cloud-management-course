# Developing a Cloud Architecture

## Introduction

In order to determine the appropriate Cloud Architecture for your organization, you must first complete several activities - an audit of IT systems and processes, complete an IT inventory, and compile IT requirements.  You must also develop competency with diagramming software.

## IT Systems Audit and Inventory

There are five phases of this process:

* Scoping
* Planning
* Data Gathering
* Analysis
* Reporting

### Scoping
Scoping is where you determine your areas of focus for the audit.  This is also where you determine any areas that are out-of-scope.  For example, if you are tasked with performing work for a particular organization, then that organization would be your area of focus and other organizations would likely be out-of-scope.  As part of the scoping phase you will read any information that pertains to previous audit and inventory activities.  If you were provided any additional background information, then this information will be key to defining an appropriate scope.

### Planning
The planning phase phase of the process is where you further refine the scope and increase the level of detail in your plan.  This is also when your project planning documents begin to take shape and you begin engaging stakeholders in the planning process.  As your plan becomes closer to a final version, you will begin communicating your project schedule to stakeholders and solicit their input.  This is also when you will define the project work flow and begin compiling a risk matrix.  

### Data Gathering
Data gathering is when we gather data by the following primary methods:

<li>Interviewing stakeholders to collect user stories
<li>Reviewing documentation
<li>Observing and documenting key business processes<br><br>

This also happens to be the primary phase for identifying future opportunities for automation, so it is critical to really focus on creating detailed documentation as you go.  As part of this process, you will end with an inventory of the following: systems, data, data flows, process flows, stakeholders, and software.

### Analysis
The analysis phase is when we conduct in-depth analysis of the data, identify recommendations, and begin compiling your report.  During this process, you will use Strengths, Weaknesses, Opportunities, and Threats or [SWOT](https://en.wikipedia.org/wiki/SWOT_analysis) to aid in your analysis.

### Reporting
The reporting phase is the final phase and is where you will prepare your initial report to management if you are seeking approval to begin a cloud project.  If your organization does not require approval to proceed, then you will use this report to begin compiling specific IT requirements and ultimately decide on an appropriate Cloud architecture.

## IT Requirements

After you have completed your IT Systems Audit and Inventory, then you are ready to begin creating very detailed business requirements for each IT system.  Your business requirements must be detailed enough for someone unfamiliar with the system to be able to either develop software to meet the requirements, or be able to find an existing system that meets all requirements. <br>

The recommended approach is to compile a separate business requirements document \(BRD\) for each individual system and then use that BRD document to define whether to build or buy a solution.  In addition to defining the requirements, prioritization and classification are critical.  Prioritization is where you determine how important the requirement is, relative to business resource limitations.  Classification is where you determine whether the requirement is a functional or non-functional requirement and then further break that requirement down into more specialized requirements.

You may wish to review this [Business Requirements Document Overview](https://www.youtube.com/watch?v=Q4xFImKTqqM) video.

### Example - Financial System Requirements

<li>The system must be able to process a minimum of 15,000 employees per payroll cycle.<br>
<li>The system must be able to process payroll for all employees within 2 hours.<br>
<li>The system must have 99.99% availability to employees during U.S. Business Hours, defined as 8am to 6pm Pacific Time Monday through Friday.<br>
<li>The system must have 95% availability to employees outside of U.S. Business Hours, defined as 6pm Friday through 8am Monday \(Pacific Time\).<br>
<li>The system must be accessible from the Internet.<br>
<li>The system must provide mobile app interfaces.<br>
<li>The average page load time for a non-login page must be less than 5 seconds as measured by an external provider, such as ThousandEyes.<br>
<li>The system must have an API that permits integration with other systems.<br>
<li>The system must not require new capital budget allocations.<br>

In Lab 4, you will define requirements using the example BRD document hyperlinked from the lab.

## Diagramming Software

I recommend that you utilize [LucidChart (free for students)](https://www.lucidchart.com/pages/usecase/education) for project deliverables, but you may use any diagramming software as long as it can output clear, professional-looking diagrams.  [CloudCraft](https://cloudcraft.co) is great for AWS diagrams, but does not support other cloud platforms.  [Draw.io](https://draw.io) is another potential diagramming software.  CSUSM also provides Microsoft Visio via Cougar Apps.

## Creating a Cloud Architecture

Be sure to review the Cloud Architecture video linked from the main Module 5 page.

## Sample Cloud Architecture diagrams


[<li>SaaS Providers - Image Source: Corradino, Hitch, Moua, Scannell, Tran (2019)](https://github.com/captainarcher/cloud-management-course/tree/master/learningresources/module5/cloud-architecture-examples/detailed-external-saas-providers-final.png)<br>

[<li>High-Level Architecture - Image Source: Corradino, Hitch, Moua, Scannell, Tran (2019)](https://github.com/captainarcher/cloud-management-course/tree/master/learningresources/module5/cloud-architecture-examples/high-level-architecture-diagram-using-gcp-and-other-products-final.png)<br>

[<li>GCP Hosted System Detailed Architecture - Image Source: Corradino, Hitch, Moua, Scannell, Tran (2019)](https://github.com/captainarcher/cloud-management-course/tree/master/learningresources/module5/cloud-architecture-examples/detailed-gcp-hosted-system-detailed-final.png)<br>

[<li>GCP Cluster Nodes  - Image Source: Corradino, Hitch, Moua, Scannell, Tran (2019)](https://github.com/captainarcher/cloud-management-course/tree/master/learningresources/module5/cloud-architecture-examples/detailed-cluster-node-final.png)<br>

[<li>GCP Detailed VPC - Image Source: Corradino, Hitch, Moua, Scannell, Tran (2019)](https://github.com/captainarcher/cloud-management-course/tree/master/learningresources/module5/cloud-architecture-examples/detailed-vpc-final.png)<br>

[<li>GCP Network Management and Security Structure - Image Source: Corradino, Hitch, Moua, Scannell, Tran (2019)](https://github.com/captainarcher/cloud-management-course/tree/master/learningresources/module5/cloud-architecture-examples/detailed-network-management-and-security-structure-final.png)<br>


## Attribution
 Corradino, C., Hitch, G., Moua, J., Scannell, J., and Tran, N. (2019) Cloud Architecture Diagrams. California State University - San Marcos.  Unpublished.
