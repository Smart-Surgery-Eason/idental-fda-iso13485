# Software Detail Design
| PREPARED BY | NAME | TITLE | SIGNATURE |
| :---------- | :--- | :---- | :-------- |
| REVIEW BY   |      |       |           |
| APPROVED BY |      |       |           |

## TABLE OF CONTENTS
- [Software Detail Design](#software-detail-design)
  - [TABLE OF CONTENTS](#table-of-contents)
  - [1. PURPOSE](#1-purpose)
  - [2. SCOPE](#2-scope)
  - [3. DEFINITIONS, ACRONYMS, AND ABBREVIATIONS](#3-definitions-acronyms-and-abbreviations)
  - [4. SOFTWARE ARCHITECTURE OVERVIEW](#4-software-architecture-overview)
  - [5. DEVELOPMENT PLATFORM AND TOOL](#5-development-platform-and-tool)
  - [6. DETAIL DESIGN](#6-detail-design)
    - [6.1 SOFTWARE ITEM SI01-01](#61-software-item-si01-01)
    - [6.2 SOFTWARE ITEM SI02-01](#62-software-item-si02-01)
    - [6.3 SOFTWARE ITEM SI03-01](#63-software-item-si03-01)
    - [6.4 SOFTWARE ITEM SI03-02](#64-software-item-si03-02)
    - [6.5 SOFTWARE ITEM SI03-03](#65-software-item-si03-03)
    - [6.6 SOFTWARE ITEM SI03-04](#66-software-item-si03-04)
    - [6.7 SOFTWARE ITEM SI03-05](#67-software-item-si03-05)
    - [6.8 SOFTWARE ITEM SI03-06](#68-software-item-si03-06)
    - [6.9 SOFTWARE ITEM SI04-01](#69-software-item-si04-01)
    - [6.10 SOFTWARE ITEM SI04-02](#610-software-item-si04-02)
    - [6.11 SOFTWARE ITEM SI04-03](#611-software-item-si04-03)
    - [6.12 SOFTWARE ITEM SI04-04](#612-software-item-si04-04)
    - [6.13 SOFTWARE ITEM SI04-05](#613-software-item-si04-05)
    - [6.14 SOFTWARE ITEM SI04-06](#614-software-item-si04-06)
    - [6.15 SOFTWARE ITEM SI05-01](#615-software-item-si05-01)
    - [6.16 SOFTWARE ITEM SI06-01](#616-software-item-si06-01)
    - [6.17 SOFTWARE ITEM SI07-01](#617-software-item-si07-01)
    - [6.18 SOFTWARE ITEM SI08-01](#618-software-item-si08-01)
    - [6.19 SOFTWARE ITEM SI09-01](#619-software-item-si09-01)
    - [6.20 SOFTWARE ITEM SI10-01](#620-software-item-si10-01)

## 1. PURPOSE

This document is to subdvide the software until it is represented by software units.

## 2. SCOPE

The scope of this document is to document the detail of software unit design, including hardware, program, interface, performance and functional specifications.

## 3. DEFINITIONS, ACRONYMS, AND ABBREVIATIONS

## 4. SOFTWARE ARCHITECTURE OVERVIEW

Please refer to Software Architecture Design Document.

| ![][asset-00001] |
| :---------- |

## 5. DEVELOPMENT PLATFORM AND TOOL

Please reference 5.1 Software Development and Maintenance Plan > [8.3.2. SOFTWARE DEVELOPMENT TOOLS](https://docs.google.com/document/d/1_i8uMje-_tTCxqQKz1w-gne2RPgpQ5YV/edit#heading=h.1pxezwc)

## 6. DETAIL DESIGN
### 6.1 SOFTWARE ITEM SI01-01
This Software item handles display of dental with periodontal stage visualization and manages the frontend UI imaging features.
| SOFTWARE Unit | Description | Hazard Class |
| --------------------- | :------------------------------------ | :----------- |
| SU0101-01 | Render the length of periodontal estimation | class A |
| SU0101-02 | Auto-annotation(Render periodontal stage visualization) | class A |
| SU0101-03 | View, zoom, and navigate through imaging layers | class A |
| SU0101-04 | Handle image loading and layout for UI | class A |
### 6.2 SOFTWARE ITEM SI02-01
This Software item performs periodontal analysis computations and processing.
| SOFTWARE Unit | Description | Hazard Class |
| --------------------- | :--------------------------- | :----------- |
| SU0201-01 | Compute periodontal analysis | class B |
| SU0201-02 | Send results back the UI layer | class B |
### 6.3 SOFTWARE ITEM SI03-01
This Software item manages account management UI functionality including user interfaces for account creation, editing and deletion.
| SOFTWARE Unit | Description | Hazard Class |
| --------------------- | :------------------- | :----------- |
| SU0301-01 | Display an interactive account management interface | class B |
| SU0301-02 | User input validation | class B |
| SU0301-03 | Account session management | class B |
### 6.4 SOFTWARE ITEM SI03-02
This Software item handles feature management UI allowing users to enable/disable features based on permissions.
| SOFTWARE Unit | Description | Hazard Class |
| --------------------- | :------------------- | :----------- |
| SU0302-01 | Render a feature management interface | class B |
### 6.5 SOFTWARE ITEM SI03-03
This Software item manages audit logging UI functionality for viewing and filtering system logs.
| SOFTWARE Unit | Description | Hazard Class |
| --------------------- | :--------------- | :----------- |
| SU0303-01 | An UI allows users to view | class A |
| SU0303-02 | An UI allows users to filter | class A |
| SU0303-03 | User could export log entries | class A |
### 6.6 SOFTWARE ITEM SI03-04
This Software item handles file management UI including archive, file listing and file transfer operations.
| SOFTWARE Unit | Description | Hazard Class |
| --------------------- | :---------------- | :----------- |
| SU0304-01 | An archive button | class B |
| SU0304-02 | Display and manage file list | class B |
| SU0304-03 | Handle file upload/download | class B |
### 6.7 SOFTWARE ITEM SI03-05
This Software item manages settings management UI for application preferences and configurations.
| SOFTWARE Unit | Description | Hazard Class |
| --------------------- | :------------------- | :----------- |
| SU0305-01 | Render a settings management interface | class B |
| SU0305-02 | Display settings options | class B |
| SU0305-03 | Auto-save settings changes | class B |
### 6.8 SOFTWARE ITEM SI03-06
This Software item handles language management UI including English and Traditional Chinese localization.
| SOFTWARE Unit | Description | Hazard Class |
| --------------------- | :------------------- | :----------- |
| SU0306-01 | Present english locale UI | class B |
| SU0306-02 | Present traditional chinese locale UI | class A |
| SU0306-03 | Switch between language locales | class B |
### 6.9 SOFTWARE ITEM SI04-01
This Software item manages account management backend services including user authentication and profile management.
| SOFTWARE Unit | Description | Hazard Class |
| --------------------- | :------------------------ | :----------- |
| SU0401-01 | Backend services for managing user accounts | class B |
| SU0401-02 | Process user registration and login | class B |
| SU0401-03 | Handle account deletion and updates | class B |
### 6.10 SOFTWARE ITEM SI04-02
This Software item handles feature management backend services for enabling/disabling features and managing permissions.
| SOFTWARE Unit | Description | Hazard Class |
| --------------------- | :------------------------ | :----------- |
| SU0402-01 | Backend to enable, disable features | class B |
| SU0402-02 | Manage feature state persistence | class B |
| SU0402-03 | Synchronize features across sessions | class B |
### 6.11 SOFTWARE ITEM SI04-03
This Software item manages audit logging backend functionality for recording and retrieving system logs.
| SOFTWARE Unit | Description | Hazard Class |
| --------------------- | :------------------- | :----------- |
| SU0403-01 | Create an audit logging backend to record and retrieve user actions | class A |
| SU0403-02 | Append log entries from services | class A |
### 6.12 SOFTWARE ITEM SI04-04
This Software item handles file management backend services for secure file operations.
| SOFTWARE Unit | Description | Hazard Class |
| --------------------- | :-------------------- | :----------- |
| SU0404-01 | Backend that allows secure file operations | class B |
| SU0404-02 | Maintain file metadata | class B |
| SU0404-03 | Manage file permissions | class B |
### 6.13 SOFTWARE ITEM SI04-05
This Software item manages settings management backend for storing and retrieving application preferences.
| SOFTWARE Unit | Description | Hazard Class |
| --------------------- | :------------------------ | :----------- |
| SU0405-01 | Backend to store and retrieve application preferences | class B |
| SU0405-02 | Load settings defaults | class B |
| SU0405-03 | Save and update user preferences | class B |
### 6.14 SOFTWARE ITEM SI04-06
This Software item handles language management backend services including localization APIs.
| SOFTWARE Unit | Description | Hazard Class |
| --------------------- | :------------------------ | :----------- |
| SU0406-01 | Compute english locale API | class B |
| SU0406-02 | Compute traditional chinese locale API | class B |
| SU0406-03 | Fetch and apply localization data | class B |
### 6.15 SOFTWARE ITEM SI05-01
This Software item manages pub/sub and event management for data integration.
| SOFTWARE Unit | Description | Hazard Class |
| --------------------- | :-------------------------- | :----------- |
| SU0501-01 | Manage event subscriptions | class B |
| SU0501-02 | Dispatch and log event messages | class B |
| SU0501-03 | Retry failed message deliveries | class B |
### 6.16 SOFTWARE ITEM SI06-01
This Software item handles pre-processing data pipeline including filtering and normalization.
| SOFTWARE Unit | Description | Hazard Class |
| --------------------- | :-------------------------- | :----------- |
| SU0601-01 | Filtering | class B |
| SU0601-02 | Normalization | class B |
### 6.17 SOFTWARE ITEM SI07-01
This Software item manages ML model inference for dental segmentation tasks.
| SOFTWARE Unit | Description | Hazard Class |
| --------------------- | :---------------- | :----------- |
| SU0701-01 | Dental segmentation tasks | class A |
### 6.18 SOFTWARE ITEM SI08-01
This Software item handles post-processing data pipeline including contour extraction and anatomy structure processing.
| SOFTWARE Unit | Description | Hazard Class |
| --------------------- | :--------------------------- | :----------- |
| SU0801-01 | Contour extraction | class A |
| SU0801-02 | Anatomy structure locating | class A |
| SU0801-03 | Anatomy structure enhancement | class A |
### 6.19 SOFTWARE ITEM SI09-01
This Software item manages storage for unstructured data with metadata and versioning capabilities.
| SOFTWARE Unit | Description | Hazard Class |
| --------------------- | :--------------------------- | :----------- |
| SU0901-01 | Store data with metadata and versioning | class B |
### 6.20 SOFTWARE ITEM SI10-01
This Software item handles storage for structured data including indexing and backup functionality.
| SOFTWARE Unit | Description | Hazard Class |
| --------------------- | :------------------------- | :----------- |
| SU1001-02 | Indexing | class B |
| SU1001-03 | Backup and restore functionality | class B |## 7. UPDATE AND VERIFICATION OF SOFTWARE DETAIL DESIGN
Before this document is released, all software unit shall be reviewed to ensure the following:

| Item                                                   | Pass/Fail | Check by |
| :----------------------------------------------------- | :-------- | :------- |
| implements the software architecture                   | Pass      | AAA      |
| free from contradiction with the software architecture | Pass      | BBB      |

Corresponding detailed verification shall be documented in the Software unit verification report.

The document shall update as required in the software development and maintenance plan.

[asset-00001]: ../assets/5-4-figure-01.png