
## Late Export Declarations Analysis (Excel, BPMN 2.0)

## Executive Summary

This report analyses the issue of Late Export Declarations within the Marketing Department, which significantly impacted the BOI stock adjustment process and compliance with Thai Customs regulations. The late submission of export declarations led to inefficiencies, delayed stock adjustments, and potential risks of penalties and lost tax benefits.

Through a root cause analysis using a Fishbone Diagram, the primary reasons for these delays were identified, including lack of assigned responsibility, incorrect information in export declarations, unclear workflows, and system malfunctions. The Marketing Department addressed these challenges by implementing a structured action plan based on the 5W1H methodology, focusing on process improvements, responsibility assignments, and workflow optimisation.

A testing period was conducted from January to March 2020, and the results demonstrated a 100% reduction in Late Export Declarations, from 149 cases (7.5%) in Q4 2019 to 0 cases in Q1 2020. The implementation of automated reminders, improved amendment handling, early validation, and streamlined data collection for BOI submission played a crucial role in ensuring smoother operations and sustained compliance.

## Table of Content

[Executive Summary](#executive-summary)  
[1. Introduction](#1-introduction)  
[1.1. Overview](#11-overview)  
[1.2. Proroblem Statement](#12-problem-statement)  
[1.3. Project Objective](#13-project-objective)  
[1.4. Data Description](#14-data-description)    
[2. Key Findings](#2-key-findings)  
   [2.1. Total Shipping Errors](#21-total-shipping-errors)  
   [2.2. Late Export Declarations by Consignee](#22-late-export-declarations-by-consignee)  
   [2.3. Late Export Declarations by Transportation](#23-late-export-declarations-by-transportation)  
   [2.4. Late Export Declarations by Leadtime](#24-late-export-declarations-by-leadtime)  
[3. Root Cause Analysis](#3-root-cause-analysis)  
[3.1. Fishbone Diagram](#31-fishbone-diagram)  
   [3.2. Root Cause Validation](#32-root-cause-validation)  
[4. Action Plan](#4-action-plan)  
[5. Improved Workflow (BPMN 2.0)](#5-improved-workflow-bpmn-20)  
   [5.1 AS-IS Process](#51-as-is-process)  
   [5.2 TO-BE Process](#52-to-be-process)  
[6. Results](#6-results)  
[7. Conclusion](#7-conclusion)  


## 1. Introduction
### 1.1. Overview

In Thailand, export declarations are essential for ensuring that businesses comply with customs regulations and facilitate the smooth movement of goods across borders. They serve as a legal requirement for all exports and are integral to maintaining compliance with Thai Customs Law and international trade regulations.

For companies benefiting from BOI (Board of Investment) privileges, export declarations are even more important. They allow businesses to access tax exemptions, import duty reductions, and other trade incentives under the BOI program. These declarations ensure that companies can correctly adjust their BOI stock and maintain eligibility for privileges like VAT exemptions and corporate income tax reductions.

By submitting accurate and timely export declarations, companies not only avoid the risk of fines, delays, or penalties but also streamline their operations. They can ensure that all tax exemptions and customs benefits are properly claimed, making their supply chain more efficient and competitive. Furthermore, proper export declarations provide essential documentation for stock adjustments related to BOI requirements, ensuring that any goods imported duty-free and used for export production are correctly accounted for in the company's records.

### 1.2. Problem Statement
Through a thorough analysis of the Marketing department's operational issues, it has been identified that the late Export Declarations is a significant contributor to many of the challenges impacting the BOI stock adjustment process. These delays not only disrupt the accurate reporting and adjustment of imported goods under BOI privileges but may also result in customs-related penalties and missed tax exemptions.

The Marketing Department believes that this issue can be effectively addressed internally through better management of the export declaration process. By improving BOI stock adjustments and ensuring timely submission of export declarations, the department can reduce delays, optimise compliance, and ultimately enhance operational efficiency.

### 1.3. Project Objective
The main objective of this project is to address and resolve the issue of late return of export declarations that has been disrupting the BOI stock adjustment process and affecting overall operational efficiency. The key goals are:

- Analyse the Root Cause: Investigate the underlying reasons for the delays in export declarations and their impact on the BOI stock adjustment process.

- Develop and Implement Solutions: Identify and implement practical solutions to eliminate delays and improve the timeliness and accuracy of export declarations.

- Improve Operational Efficiency: Streamline the export declaration process to minimise disruptions, reduce redundant process, and ensure smoother BOI stick adjustment.

### 1.4. Data Description
The dataset includes the following columns:

**Shipments Table**

| **Column Name**        | **Description**                                                                                               |
|------------------------|---------------------------------------------------------------------------------------------------------------|
| **SEQ**                | Unique identifier for each export transaction.                                                                |
| **Invoice No.**        | Unique identifier for the export invoice.                                                                     |
| **BuyerName**          | Name of the buyer receiving the goods.                                                                        |
| **Consignee**          | Individual or company receiving the goods.                                                                    |
| **Ship Date**          | Date when the goods are shipped.                                                                              |
| **ETD**                | Estimated date and time of departure from the origin.                                                         |
| **ETA**                | Estimated arrival date and time at the destination.                                                           |
| **Leadtime (Days)**    | Number of days from shipment to arrival.                                                                      |
| **Currency**           | Currency used for the transaction.                                                                            |
| **Destination**        | Country or location of the shipment destination.                                                              |
| **Transportation**     | Mode of transportation (air, sea, road).                                                                      |
| **Term**               | Payment or delivery terms (e.g., FOB, CIF).                                                                   |
| **Origin**             | Country or location where the goods originate.                                                                |
| **Vessel**             | Name of the vessel (sea) or flight (air).                                                                     |
| **Airfreight**         | Air shipping cost or amount (if applicable).                                                                   |
| **CnSize 20F**         | Quantity of 20-foot containers used.                                                                          |
| **CnSize 40F**         | Quantity of 40-foot containers used.                                                                          |
| **CnSize 40FH**        | Quantity of 40-foot high-cube containers used.                                                                 |
| **LCL**                | Shipments that do not fill a full container.                                                                  |
| **Export Declaration** | Status of the export declaration (on time or late).                                                           |
| **Shipping Errors**    | Type of error in shipping (e.g., late export declaration, transportation delay).                              |



**Export Declarations Table**

| **Column Name**        | **Description**                                                                                               |
|------------------------|---------------------------------------------------------------------------------------------------------------|
| **SEQ**                | Unique identifier for each export transaction.                                                                |
| **Invoice Ref**        | Reference number for the export invoice.                                                                      |
| **ETD**                | Estimated time of departure from the origin.                                                                  |
| **Reference No.**      | Internal tracking reference for the export shipment.                                                           |
| **Declaration No.**    | Unique identifier for the export declaration filed with customs.                                              |

## 2. Key Findings

### 2.1. Total Shipping Errors

![Image](https://github.com/user-attachments/assets/89d045e7-b941-44c2-bfa7-54f7047b0477)

- The data highlights that Late Export Declarations and Airfreight due to Production Delay were the most significant contributors to shipping errors, accounting for over 96% of total issues. 
- However, since the Marketing Department cannot resolve production delays, the focus was first placed on addressing Late Export Declarations.

### 2.2. Late Export Declarations by Consignee

![Image](https://github.com/user-attachments/assets/4d67bb0b-d1c4-44dc-943d-00323becdeec)

- MB JAPAN is the primary concern, as it represents the bulk of Late Export Declarations.
- Focusing on resolving issues related to MB JAPAN first would likely have the most impact on reducing Late Export Declarations.

### 2.3. Late Export Declarations by Transportation

![Image](https://github.com/user-attachments/assets/67f7124f-1471-4e28-b163-c436a865a2bb)

- Air shipments have the highest number of Late Export Declarations (85 cases, 57.05%) compared to sea shipments (64 cases, 42.95%).
- Since Air shipments have more delays, this suggests potential issues such as last-minute document processing, customs clearance delays, or tight shipping schedules.
- Even though Sea shipments have fewer late declarations, they still contribute significantly (almost 43%), meaning there may be inefficiencies in sea freight scheduling or documentation as well."							
### 2.4. Late Export Declarations by Leadtime
![Image](https://github.com/user-attachments/assets/4e9ff2ab-b2a1-4576-9720-249b25bd2306)

- The majority of Late Export Declarations occur within short lead times (3 to 7 days), which corresponds to the lead time of air shipments.
- 3-day lead time has the highest number (85 cases), followed by 7 days (22 cases) and 8 days (17 cases).
- As the lead time increases beyond 10 days, the number of late declarations significantly decreases.						
## 3. Root Cause Analysis
### 3.1. Fishbone Diagram

**Purpose**			

- This Fishbone Diagram aims to identify, analyse, and visually map out the potential factors contributing to the root cause of late export declarations for shipments between October and December 2019.			
- It helps break down complex issues into more manageable components for effective problem-solving.
  
**Diagram**

A Fishbone Diagram is used to analyse root causes by visualising four categories: Manpower, Material, Method, and Machine as shown below.

![Image](https://github.com/user-attachments/assets/89393ae3-ac45-46dd-bd4b-0eba14a318d7)

**Structure**

![Image](https://github.com/user-attachments/assets/84ee6eef-67df-4340-9dea-881e6b40c0e6)

The delay in Export Declarations is primarily caused by **the lack of assigned responsibility**, where no designated person follows up, leading to process inefficiencies. Additionally, **incorrect information in Export Declarations**, often due to changes in shipping details like vessel delays, results in frequent corrections and slows down approvals. Furthermore, **an unclear workflow**, with no standardised guidelines and lengthy follow-up timeframes, contributes to the delays. These issues can be effectively resolved internally by the Marketing Department through process improvement, clear responsibility assignment, and improved coordination.

### 3.2. Root Cause Validation

The 3 Gen Methodology (Genchi, Genbutsu, Genjitsu) is a structured approach used to validate root causes by focusing on direct observation, real data, and actual circumstances rather than assumptions. This methodology ensures that proposed solutions are based on real-world evidence, leading to more effective and sustainable improvements, as shown below.

**Purpose**	

- The 3 Gen problem-solving methodology (also referred to as Genchi, Genbutsu, Genjitsu) focuses on directly observing the situation and verifying actual data to gain a complete understanding and effectively resolve issues.							
-  To ensure that decisions and solutions are grounded in factual information rather than assumptions or second-hand accounts.							

**Findings**

The causes of the late export declarations occurred across various aspects during the observed period from October to December 2019.

![Image](https://github.com/user-attachments/assets/cddac549-f502-4c50-9bbc-4372f84e2da0)



## 4. Action Plan

The **5W1H** (Who, What, When, Where, Why, and How) method is used to create an action plan based on the Fishbone Diagram analysis. This approach provides a clear, actionable, and well-structured solution, as shown below.


**Purpose**		

To ensure a structured, comprehensive, and effective approach to problem-solving and implementing solutions for the late Export Declarations issue, including identifying required actions, reasons for taking them, responsible persons, locations and scopes, and the timeframe for execution.						

![Image](https://github.com/user-attachments/assets/3c5823e1-53ac-49fd-9de2-7e8eabbfd504)

**The document processing system malfunction remains unaddressed as it falls outside the responsibilities of the Marketing department.


## 5. Improved Workflow (BPMN 2.0)


### 5.1. AS-IS Process
![Image](https://github.com/user-attachments/assets/9ab6ed5a-2ebe-406c-b263-a6a7b3fb886a)

This process flow represents the existing Export Declaration & BOI Stock Adjustment process, involving Freight Forwarders, Logistics Teams, META, and Thailand BOI.												
												
**Key Issues Identified**		

- **Delays Due to Missing Export Declarations**: Export Declarations are often incomplete or missing, requiring manual follow-ups. The Logistics Team has to send follow-up emails to Freight Forwarders, delaying the process.

- **Manual Amendment Handling**: If an Export Declaration contains incorrect details, it must go through a manual verification process, and the team must wait for the corrected Export Declaration, causing further delays.

- **Incomplete Stock Adjustments**: If there are issues in the Export Declaration or missing information, the BOI stock adjustment cannot be completed. The Logistics Team must inform stakeholders about incomplete stock, leading to extra steps and manual interventions.

- **End-of-Month Bottleneck**: The BOI Team collects the summary list only at the end of the month, causing a workload surge. If any data is missing or incorrect, the adjustment request cannot proceed, further delaying stock updates.

- **Risk of Inaccuracies**: Since stock adjustment is dependent on correct and complete Export Declarations, any issue can cause inaccurate BOI stock adjustments. The process lacks automation, increasing the chance of human error in manual verification and data entry.


### 5.2. TO-BE Process

![Image](https://github.com/user-attachments/assets/ed7dcd6a-0cd3-4f2e-85f4-40cc2c89cc4b)

**Key Improvements**

- **Automated Reminder System**: Instead of relying on manual follow-ups, an automated reminder email is now sent one week before month-end, ensuring timely action.

- **Early Validation of Export Declarations**: The Logistics Team now checks the Export Declaration correctness upon receipt, allowing errors to be identified earlier in the process. If incorrect, an amendment request is immediately sent instead of delaying it until month-end.

- **Improved Amendment Handling**: The process now has a clear amendment request flow, reducing miscommunication and ensuring that necessary corrections are made before submission to BOI.

- **Streamlined Data Collection for BOI Submission**: The receipt list is now recorded and consolidated as part of an organised workflow, preventing last-minute rushes at month-end. The BOI team collects the summary list systematically, ensuring all required data is available for stock adjustments.

- **Enhanced BOI Stock Adjustment Process**: By integrating real-time validation and structured data handling, the process ensures compliance with BOI regulations. The improved structure minimises inventory discrepancies and provides a clear audit trail for BOI stock movements.

## 6. Results

**Key Metrics**

![Image](https://github.com/user-attachments/assets/631b507d-e6e0-4b71-9396-8526d89d5a03)

- The testing period successfully demonstrated the effectiveness of process improvements in eliminating late export declarations, reducing cases from 149 (7.5%) in Oct-Dec 2019 to 0 in Jan-Mar 2020, achieving a 100% improvement. 
- This outcome was achieved through the implementation of a structured action plan, which included assigned responsibilities, enhanced tracking mechanisms, and streamlined workflows.

**Shipping Errors overtime**

![Image](https://github.com/user-attachments/assets/38638f21-0894-4edc-a062-2a3c727aad67)

![Image](https://github.com/user-attachments/assets/12f5017a-d3c2-44f0-8e38-ab3fec8240c7)

- The data highlights a significant reduction in Late Export Declarations after January 2020 compared to the previous months (Oct-Dec 2019), indicating successful process improvements.
- Before the improvement, there were 149 cases in Q4 2019, which dropped to 0 cases in Q1 2020—a 100% reduction, demonstrating a sustained positive trend rather than a one-time fix. 
- The reduction is likely due to better process controls including clear workflow and a support from automated email.

## 7. Conclusion

The elimination of Late Export Declarations within the Marketing Department highlights the effectiveness of process improvement and structured problem-solving methodologies. The findings confirm that internal improvements, such as clearer responsibilities, better tracking, and workflow enhancements, can significantly enhance efficiency and compliance.

By integrating proactive tracking workflow, automation, and systematic validation, the department not only resolved existing inefficiencies but also established a robust, scalable process that prevents future delays. The success of this initiative reinforces the importance of continuous improvement and strategic problem-solving in ensuring operational excellence and compliance with BOI and Thai Customs regulations.
