# Technical Guide

## 2022-01-25

#note

---

## Solution Design
- Clinicians use the ABL Blood Gas Machine to produce blood gas results
- The ABL Blood Gas Machine sends the results to ACQURE server (PathWest/Radiometer)
- The ACQURE server sends the results to all our HLM Datapads (once only). It does not queue or resend the messages. Only online Datapads receive the feed.
- The HLM Datapad checks to see if the Patient ID in the message received matches the Patient ID of the patient of the case currently running in Sorin Recorder
- The perfusionist accepts the results into Sorin Recorder

## Setup Instructions
1. Create a technical design document using your hospital's approved template. The document should include:
	1. IP addresses of each HLM Datapad
2. Advice PathWest that you will be integrating your HLM to receive blood gas results via HL7. Ask them to confirm that the BGA is connected to their AQURE server to send blood gas results via HL7.