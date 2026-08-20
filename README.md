# Overview

From a technical perspective, systems that integrate and coordinate the healthcare management systems of individual hospitals (such as electronic medical records and departmental systems) at the city or state/prefecture level do exist.

Technically, these are referred to as **Healthcare Information Exchange Platforms**, or internationally as **HIE (Health Information Exchange)** and **EHR (Electronic Health Record: Regional/Lifelong Electronic Health Record) systems**.

However, from a technical perspective, there are three major architectures (design structures) for achieving this type of "integration." From the model closest to what you may imagine as "integrated management through a single system" to the more practical models that are widely adopted today, the technical structures are as follows.

---

## 1. Centralized Model

This is the technical architecture closest to the idea of **"integrating and centrally managing everything through one massive system."**

**How it works:**

A massive database called a **Central Clinical Data Repository (CDR)** is built in a city or state data center.

Raw patient data—including diagnoses, prescriptions, test results, and medical images—is transmitted in real time from each hospital's system (such as vendor-provided EHR systems like Epic or Cerner) to the central repository, where it is synchronized and stored.

**Advantages:**

Data retrieval is extremely fast, and large-scale statistics and analytics, such as AI-based regional healthcare forecasting, can be performed relatively easily.

**Disadvantages:**

Building and maintaining the server infrastructure can be extremely expensive.

In addition, if the central database is compromised by a cyberattack, there is a critical security risk in which the data of all patients across the entire region could be exposed at once, making the central database a **single point of failure**.

---

## 2. Federated Model

This is currently one of the most technically practical architectures and is adopted by many cities and states.

**How it works:**

Raw patient data remains stored on each hospital's own servers and internal systems.

The central system contains only a **Master Patient Index (MPI)** and a **Record Locator Service (RLS)**, which function like an index or table of contents indicating **which hospital holds data for a particular patient**.

**Technical Integration Flow:**

1. A doctor at Hospital A examines a patient.
2. A query is sent to the integrated system (the index server) asking, **"Is there any previous data for this patient?"**
3. The index system responds that **"data exists at Hospital B and Hospital C."**
4. The system automatically and securely accesses the servers of Hospitals B and C, retrieves the data on demand, and displays the information together in an integrated interface.

**Advantages:**

Each hospital can maintain full control over its own data, while the risk of information leakage is distributed rather than concentrated in one central location.

---

## 3. Hybrid Model

This architecture combines the advantages of the two models described above and is currently a major trend.

**How it works:**

Only **core data that must be immediately available during emergencies or visits to other hospitals**—such as allergy information, contraindicated medications, current prescriptions, and recent medical summaries—is stored centrally, following the centralized model.

Large data such as high-resolution medical images and detailed nursing records remain stored at individual hospitals and are retrieved only when needed, following the federated model.

In this way, the system combines centralized and federated information exchange.

---

## Middleware Supporting These Systems

Because individual hospitals use healthcare systems from different vendors, including different electronic medical record systems, middleware known as an **Interface Engine**—such as **Mirth Connect** or **Rhapsody**—is used to physically and technically connect these systems.

The interface engine translates each hospital's local data format in real time into the international standard **HL7 FHIR**, which acts as a common language.

This enables integrated coordination across hospitals at the city, state, or regional level.

---

## Real-World Examples

**United States — HIE (Example: Manifest MedEx):**

At the state level, HIE systems connect the medical record systems of millions of patients across healthcare organizations, allowing healthcare professionals to access a patient's previous medical history from different hospitals, including during emergency transportation and treatment.

**Japan — Regional Healthcare Information Network (Example: Ajisai Net in Nagasaki Prefecture):**

The system technically connects core hospitals with regional clinics and enables healthcare providers to mutually access electronic medical records and other healthcare information.

---

# Reference Links

## Option 1

https://github.com/openhie

https://github.com/openhie/openinfoman

---

## Option 2

https://github.com/ehrbase/ehrbase

https://github.com/kakoni/awesome-healthcare

---

## Option 3

https://github.com/ciyex-org/ciyex

---

## Blockchain, Decentralized Federated Networks

https://github.com/Zzocker/EHR-on-blockchain

https://github.com/shamil-t/ehr-blockchain

---

## Healthcare Systems (Additional References)

https://github.com/HCW-home/backend

https://github.com/ciips-code/aiotp

https://github.com/openemr/openemr

https://github.com/ciips-code/aiotp

https://github.com/openmrs

https://github.com/librehealthio/lh-ehr

https://github.com/aminezouari52/telemedicine-website

---

## Clinical / Medical LLM

https://huggingface.co/m42-health/Llama3-Med42-70B
