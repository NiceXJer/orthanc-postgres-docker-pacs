# Enterprise DICOM PACS & Zero-Footprint Medical Image Viewing Stack

A production-ready PACS (Picture Archiving and Communication System) infrastructure running on Docker. This stack deploys an **Orthanc PACS core** indexed by a **PostgreSQL database** for metadata persistence, integrated with an embedded **OHIF Web Viewer**, and tested against traditional **DICOM Modality/Viewer endpoints (MicroDicom)**.

---

## 🏗️ Architecture & Network Topology

The solution separates DICOM binary/metadata storage from web viewing layers while supporting both traditional C-STORE/C-FIND network protocols and modern DICOMweb REST interfaces.

```mermaid
flowchart TD
    A["MicroDicom\nDICOM Viewer / Modality"]

    B["Orthanc Server\nDocker Container\nDICOM: 4242 | HTTP: 8042\nREST API / DICOMweb"]

    C["PostgreSQL 15\nDICOM Index & Metadata DB"]

    D["Integrated OHIF Viewer\nZero-Footprint Web Viewer"]

    A -- "C-ECHO / C-STORE\nC-FIND / C-MOVE" --> B
    B -- "Indexed Queries" --> C
    B -- "DICOMweb (WADO-RS/QIDO-RS)" --> D
```
# Orthanc PACS & DICOM Healthcare IT Lab

Containerized healthcare IT lab demonstrating **PACS deployment, DICOM networking, PostgreSQL integration, REST/DICOMweb APIs, and browser-based medical image viewing**.

## Tech Stack

* Orthanc (Docker)
* PostgreSQL
* MicroDicom
* Integrated OHIF Viewer
* Docker Compose
* REST / DICOMweb

## Validated Workflow

| Capability             | Status |
| ---------------------- | ------ |
| Docker deployment      | ✅      |
| PostgreSQL integration | ✅      |
| DICOM C-ECHO           | ✅      |
| DICOM C-FIND           | ✅      |
| DICOM C-MOVE           | ✅      |
| REST API access        | ✅      |
| OHIF web viewing       | ✅      |

## What I Implemented

* Containerized Orthanc PACS deployment
* PostgreSQL-backed DICOM metadata indexing
* DICOM modality configuration and workflows
* REST/DICOMweb administration
* Browser-based DICOM visualization with OHIF
* Docker networking and infrastructure troubleshooting

## Skills Demonstrated

**Docker · Docker Compose · PostgreSQL · DICOM · DICOMweb · REST APIs · PACS Administration · Linux-style Networking · Healthcare IT**

---

Portfolio / educational project — no real patient data included.
