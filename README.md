# Edge-to-Cloud Image Pipeline: Raspberry Pi 3B & Oracle Cloud Infrastructure (OCI)

## 📌 Project Overview
This project implements an automated, end-to-end data ingestion pipeline designed for **Edge Computing**. Using a **Raspberry Pi 3 Model B**, the system captures visual data through a USB camera and securely transmits it to **OCI Object Storage**. 

The solution focus on scalability and security, utilizing professional cloud authentication methods to manage non-structured data (images) in a production-ready environment.

---

## 🏗 Architecture
The architecture is divided into two main layers:

### 1. Edge Layer (Hardware & Local Processing)
* **Gateway:** Raspberry Pi 3 Model B.
* **Capture:** USB UVC Camera.
* **Environment:** Linux (Raspberry Pi OS) with Python-based automation.
* **Key Features:** Automated frame capture, local buffer management, and secure request signing.

### 2. Cloud Layer (Oracle Cloud Infrastructure)
* **Object Storage:** Secure Buckets for high-availability image storage.
* **IAM (Identity and Access Management):** Strict policy enforcement for device-to-cloud communication.
* **Authentication:** Industry-standard **API Key Pair** (RSA Private/Public keys) to sign requests via OCI SDK.

---

## 🛠 Tech Stack
* **Languages:** Python 3.x
* **Cloud Provider:** Oracle Cloud Infrastructure (OCI)
* **Tools/SDKs:** OCI Python SDK, OpenCV (for image capture).
* **Security:** RSA Key Pair Authentication, IAM Policies.

---

## 🚀 Technical Workflow
1.  **Capture:** A Python service manages the USB camera interface to trigger image captures.
2.  **Authentication:** The system retrieves the local Private Key to generate a signed header for the OCI API.
3.  **Ingestion:** The file is uploaded to the designated OCI Bucket using the `oci.object_storage.ObjectStorageClient`.
4.  **Logging:** Every transaction is logged locally and verified against the cloud response to ensure data integrity.

---

## 📋 Prerequisites
* Raspberry Pi 3B with Python installed.
* An active Oracle Cloud account.
* OCI CLI/SDK configured with a valid `config` file and Private Key (.pem).

---

## 🔧 Future Improvements
* [ ] Integration with OCI Vision AI for real-time object detection.
* [ ] Implementation of a local SQLite buffer for offline-first capabilities.
* [ ] Dashboard visualization for uploaded metadata.

---

**Developed by:** [Wellington Carlos / UNIVESP]
*Focusing on Data Engineering, IoT, and Cloud Solutions.*
