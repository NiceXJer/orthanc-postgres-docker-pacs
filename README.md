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
