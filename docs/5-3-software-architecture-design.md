# 5-3-software-architecture-design
|                 | **NAME** | **TITLE** | **SIGNATURE** |
| --------------: | -------- | --------- | ------------- |
| **PREPARED BY** |          |           |               |
|   **REVIEW BY** |          |           |               |
| **APPROVED BY** |          |           |               |

## TABLE OF CONTENT
1. PURPOSE
2. SCOPE
3. DEFINITIONS, ACRONYMS, AND ABBREVIATIONS
4. ARCHITECTURE DESIGN
    - 4.1 SOFTWARE LAYERED ARCHITECTURE
    - 4.2 SOFTWARE COMMUNICATION DIAGRAM
    - 4.3 SOFTWARE STATE DIAGRAM
5. SOFTWARE OF UNKNOWN PROVENANCE AND OTS
   - 5.1 FUNCTION AND REQUIREMENT OF SOUP / OTS
6. UPDATE AND VERIFICATION OF SOFTWARE ARCHITECTURE

## 1. PURPOSE
This document provides a comprehensive architectural overview of the software, using a number of different architectural views to depict different aspects of the system. It is intended to capture and convey the significant architectural decisions which have been made on the system.

## 2. SCOPE
The scope of this document is to transform the software requirement to architecture that describes the architectural structure, goal and constraints, and identify the software items. In this document , describe the top level software components and their interactions/relationships.

## 3. DEFINITIONS, ACRONYMS, AND ABBREVIATIONS
**SOUP (software of unknown provenance)** - software item that is already developed and generally available and that has not been developed for the purpose of being incorporated into the medical device (also known as "off-the-shelf software") or software item previously developed for which adequate records of the development processes are not available.

**Off-the-Shelf (OTS) Software:** A generally available software component used by a device manufacturer for which the manufacturer cannot claim complete software life cycle control (e.g., operating system, printer/display libraries).

**LEGACY SOFTWARE:** medical device software which was legally placed on the market and is still marketed today but for which there is insufficient objective evidence that it was developed in compliance with the current version of this standard.

## 4. ARCHITECTURE DESIGN

![Figure 4.3]

Req refers to the software requirement(s). Refer to the Software Requirement Document (SRS-XX Rev. X) for detailed information

| System requirement ID | MR Description             | Software requirement ID | SR Description                                                          | Software Item ID | SI Description                        |
| --------------------- | -------------------------- | ----------------------- | ----------------------------------------------------------------------- | ---------------- | ------------------------------------- |
| MR01                  | Annotation UI              | SR01                    | The software shall manage the frontend UI for Imaging features          | SI01-01          | display dental with periodontal stage |
| MR02                  | Annotation Service         | SR02                    | The software shall manage the backend process for Imaging features      | SI02-01          | perform periodontal analysis          |
| MR03                  | Management UI              | SR03                    | The software shall manage the frontend for foundational features        | SI03-01          | account management UI                 |
|                       |                            |                         |                                                                         | SI03-02          | feature management UI                 |
|                       |                            |                         |                                                                         | SI03-03          | audit logging UI                      |
|                       |                            |                         |                                                                         | SI03-04          | file management UI                    |
|                       |                            |                         |                                                                         | SI03-05          | setting management UI                 |
|                       |                            |                         |                                                                         | SI03-06          | language management UI                |
|                       |                            |                         |                                                                         | SI03-07          | Patient Report Management UI          |
| MR04                  | Management Service         | SR04                    | The software shall manage the backend for foundational features         | SI04-01          | account management backend            |
|                       |                            |                         |                                                                         | SI04-02          | feature management backend            |
|                       |                            |                         |                                                                         | SI04-03          | audit logging backend                 |
|                       |                            |                         |                                                                         | SI04-04          | file management backend               |
|                       |                            |                         |                                                                         | SI04-05          | setting management backend            |
|                       |                            |                         |                                                                         | SI04-06          | language management backend           |
|                       |                            |                         |                                                                         | SI04-07          | Patient Report Management backend     |
| MR05                  | Messaging Queue            | SR05                    | The software shall manage all events and messaging for data integration | SI05-01          | pub/sub and event management          |
| MR6                   | Data Pre Processing        | SR06                    | The software shall manage pre-processing for the data pipeline          | SI06-01          | pre-processing data pipeline          |
| MR7                   | Machine Learning Inference | SR07                    | The software shall manage inference for ML model                        | SI07-01          | ML model inference                    |
| MR8                   | Data Post Processing       | SR08                    | The software shall manage post-processing for data pipeline             | SI08-01          | post-processing data pipeline         |
| MR9                   | Data Lake                  | SR09                    | The software shall manage catalog for datasets                          | SI09-01          | storage for unstructured data         |
| MR10                  | Database                   | SR10                    | The software shall manage the database for all iDental Services         | SI10-01          | storage for structure data            |

### 4.1 Software Layered Architecture

Each layer in a software architecture by layers has a specific set of functionality and objectives. Here's a brief overview of each layer:

- **Presentation layer** - This layer is responsible for presenting the data to the user. It handles user input, displays data in a user-friendly format, and interacts with the user interface. The objective of this layer is to provide a seamless user experience.

- **Application service layer** - This layer contains the business logic of the application. It is responsible for processing data, implementing rules, and enforcing policies. The objective of this layer is to ensure that the application functions according to the business requirements.

- **Domain layer** - This layer encapsulates business logic and domain rules. It models real-world concepts like entities, value objects, and aggregates while remaining independent of external systems such as databases or user interfaces. Key principles include encapsulation, separation of concerns, and using a ubiquitous language shared with domain experts to ensure clarity and alignment with business needs.

- **External output device (Data storage) layer** - This layer is responsible for data storage and retrieval. It interacts with the database management system to store and retrieve data. The objective of this layer is to ensure that the application can efficiently handle large amounts of data.

- **Data Processing layer** - This layer is responsible for implementing machine learning algorithms in the application. It provides predictive and prescriptive analytics capabilities to the application. The objective of this layer is to improve application performance and provide insights to the business.

- **External Input Device (Integration) layer** - This layer integrates the application with other systems. It provides a way for the application to communicate with external systems, such as third-party APIs. The objective of this layer is to ensure seamless integration with other systems.

### 4.2 SOFTWARE COMMUNICATION DIAGRAM
**Description:**
Annotation UI sends a request to the periodontal estimation handler
periodontal estimation handler receives command from UI and performs inference and measure by invoking the periodontal estimation module

**LIST OF IDENTIFIED SOFTWARE ITEMS:**
- SI01-01: display dental with periodontal stage
- SI02-01: perform periodontal analysis
- SI07-01: ML model inference

### 4.3 SOFTWARE STATE DIAGRAM
**Description:** The state diagram represents the asynchronous workflow of an AI inference API for dental X-ray image processing, encompassing four main stages: pre-processing, inference, and post-processing, with transitions occurring as the system progresses through each state. Starting from a raw input image, the pre-processing phase ensures data quality through filtering and normalization. The curated data then enters the inference stage, where two machine learning models perform periodontal measurement and detection alongside teeth segmentation tasks, producing inferenced results. Finally, the post-processing stage enhances these outputs by extracting contours and locating as well as improving anatomical structures, yielding the final post-processed state. Each state transition is designed to satisfy software requirements MR6, MR7, and MR8, ensuring modular and reliable data handling throughout the pipeline.

- SI06-01: The software shall manage pre-processing for data pipeline
- SI07-01: The software shall manage inference for ML model
- SI08-01: The software shall manage post-processing for data pipeline

## 5. SOFTWARE OF UNKNOWN PROVENANCE AND OTS

### 5.1 FUNCTION AND REQUIREMENT OF SOUP / OTS
The system integrates several key OTS components to deliver a comprehensive dental imaging and management solution. CVAT handles image annotation, ABP Platform manages authentication and core services, Syncfusion provides UI components, PyTorch powers ML inference, OpenCV processes images, PostgreSQL stores data, and RabbitMQ manages messaging. These components work together to create a scalable, secure, and efficient dental imaging platform.

| Name/Version/Supplier                               | Function                                                                                                                                          | Performance requirements                                                          | Maintenance Support/End of Support date/Known vulnerabilities | Risk Analysis | Note                                           |
| --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | ------------------------------------------------------------- | ------------- | ---------------------------------------------- |
| CVAT/2.3.0/CVAT Co.                                 | Provides annotation tools for labeling and processing image data.                                                                                 | Auto-annotation(Render periodontal stage visualization) (map to SU0101-02)        | Regular community updates, Active development                 | Low           | Open source tool with strong community support |
|                                                     |                                                                                                                                                   | Must support multi-layer image visualization (maps to SU0101-03)                  |                                                               |               |                                                |
|                                                     |                                                                                                                                                   | Must handle DICOM and standard image formats (maps to SU0101-04)                  |                                                               |               |                                                |
| ABP/7.4.0/Volosoft                                  | Used as a foundational framework for managing backend architecture and user authentication.                                                       | Must support user authentication. (maps to SU0401-01)                             | Commercial support available, Regular security patches        | Medium        | Enterprise-grade framework                     |
|                                                     |                                                                                                                                                   | Must handle role-based access control (maps to SU0401-02)                         |                                                               |               |                                                |
|                                                     |                                                                                                                                                   | Must provide audit logging capabilities (maps to SU0403-01)                       |                                                               |               |                                                |
|                                                     |                                                                                                                                                   | Must support multi-tenancy architecture (maps to SU0401-03)                       |                                                               |               |                                                |
|                                                     |                                                                                                                                                   | Must integrate with existing authentication systems (maps to SU0401-02)           |                                                               |               |                                                |
| Syncfusion/21.2.3/Syncfusion Inc.                   | Provides UI components for visualization and user interface elements.                                                                             | Must provide responsive UI components for account management (maps to SU0301-01)  | Commercial support with SLA, Regular updates                  | Low           | Commercial UI component library                |
|                                                     |                                                                                                                                                   | Must support data grid with filtering and sorting (maps to SU0303-02)             |                                                               |               |                                                |
|                                                     |                                                                                                                                                   | Must include file management components (maps to SU0304-02)                       |                                                               |               |                                                |
|                                                     |                                                                                                                                                   | Must support localization for English and Traditional Chinese (maps to SU0306-01) |                                                               |               |                                                |
|                                                     |                                                                                                                                                   | Must provide settings management UI components (maps to SU0305-01)                |                                                               |               |                                                |
| PyTorch/2.0.1/Meta                                  | A deep learning framework that provides tools for building and training machine learning models, including neural networks and tensor operations. | Must support dental segmentation model inference (maps to SU0701-01)              | Active development, Regular security updates                  | Medium        | Industry-standard ML framework                 |
| OpenCV/4.8.0/Intel Corporation                      | An open-source computer vision and machine learning software library. OpenCV provides tools for real-time image processing.                       | Must perform contour extraction with precision (maps to SU0801-01)                | Active community maintenance, Regular updates                 | Low           | Widely used computer vision library            |
|                                                     |                                                                                                                                                   | Must support anatomy structure location detection (maps to SU0801-02)             |                                                               |               |                                                |
|                                                     |                                                                                                                                                   | Must provide image enhancement capabilities (maps to SU0801-03)                   |                                                               |               |                                                |
|                                                     |                                                                                                                                                   | Must process images in real-time (under 100ms)                                    |                                                               |               |                                                |
| PostgreSQL/15.3/PostgreSQL Global Development Group | Serves as the main relational database management system, handling data storage, retrieval, and management.                                       | Must support efficient indexing for dental records (maps to SU1001-02)            | Long-term support, Regular security patches                   | Low           | Enterprise-ready database system               |
|                                                     |                                                                                                                                                   | Must provide backup and restore functionality (maps to SU1001-03)                 |                                                               |               |                                                |
| RabbitMQ/3.12.2/VMware                              | Provides a messaging broker to enable communication and coordination between distributed application components.                                  | Must handle event subscriptions reliably (maps to SU0501-01)                      | Commercial support available, Regular updates                 | Low           | Industry-standard message broker               |
|                                                     |                                                                                                                                                   | Must support message logging and tracking (maps to SU0501-02)                     |                                                               |               |                                                |
|                                                     |                                                                                                                                                   | Must implement retry mechanism for failed deliveries (maps to SU0501-03)          |                                                               |               |                                                |

**Monitoring Methods:** |- Subscribe to vendor newsletters and security advisories

- Regular version compatibility checks (monthly)
- Monitor community forums and issue trackers
- Automated dependency vulnerability scanning
- Performance metric tracking through logging systems

## UPDATE AND VERIFICATION OF SOFTWARE ARCHITECTURE
Before this document is released, all software architecture shall be reviewed to ensure the following:

| Item                                                                                                                   | Pass/Fail | Check by |
| ---------------------------------------------------------------------------------------------------------------------- | --------- | -------- |
| implement system and software requirements including those relating to Risk control                                    | Pass      | AAA      |
| The software architecture is able to support interfaces between software items and between software items and hardware | Pass      | BBB      |
| Architecture supports proper operation of any soup item                                                                | Pass      | CCC      |

Corresponding detailed verification shall be documented in the Software Integration and verification report. The document shall update as required in the software development and maintenance plan.

[Figure 4.3]: ../assets/5-3-4-1.png