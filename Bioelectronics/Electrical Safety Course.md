# Electrical Safety Course

## 2022-02-15

#note

---

# Electrical Standards
- AS/NAS 3003: *Electrical installation - Patient areas*
- AS/NZS 3551: *Management programs for medical equipment*
- AS/NZS 2500: *Sage use of medical electrical equipment in health care*

![[Pasted image 20220215085958.png]]

---
# Medical Equipment Definition
> Any instrument, apparatus or appliance, including software, whether used alone or in combination, together with any accessories necessary for its correct operation, that:
> - makes physical or electrical contact with the patient
> - transfers energy to or from the patient
> - detects such energy transfer to or from the patient
> - is intended to diagnose, treat or monitor a patient.


- Note, the above definition encompasses all devices - including those that **were not** originally designed as medical equipment.
- If a device is supplied as part of, or interfaced with, other medical equipment, it is considered as medical equipment.
	- *e.g.* Monitors, phones, tablets, servers
- Hence, the need for standards such as **ISO 80001:2014** *Application of risk management for IT-networks incorporating medical equipment*

---
# Applied Parts
- Any part of electrical equipment that can come into contact with the patient *in normal use* is classified as an applied part. 
- Applied parts are classified as type B, BF or CF parts, along with defibrillator proof alternatives.

### Type B
* Non-Isolated applied part
* Offers the lowest degree of protection against electric shock
* Current that may flow between the patient and a Type B Applied Part will be limited only by the 'impedance' of the patient and therefore may result in electrocution

![[Pasted image 20220215093759.png]]

### Type BF
- Body-Protected applied part
- Provides additional protection against electrocution a long as it is not in contact with ventricular muscle mass


### Type CF
- Cardiac-Protected applies part
- Provides further protection against electrocution even if the applied part is in direct contact with the heart

### Defibrillator Proof
- Similar to BF and CF applied parts but additionally are suitable for use with defibrillators
- This means that equipment connected to the patient is protected against high frequency current

---
# Class I and Class II Electrical Equipment
* Medical equipment with additional safety precautions against electrical shock, beyond just basic insulation, is classified as either **Class I** or **Class II** electrical equipment.

### Class I
- Protectively earthed equipment
- Includes an additional safety precaution in that means are provided for accessible parts of metal or internal parts of metal to be protectively earthed
- **An additional safety earth is connected** to the earthing conductor in the fixed wiring of the installation so that the accessible parts of the equipment cannot become live
- Typically no symbol is included to indicate that a device is Class I

### Class II
- Equipment in which protection against electric shock does not rely on basic insulation only but in which additional safety precautions, such as **double insulation**, are provided
- No reliance for protective earthing or installation conditions
- Includes all equipment with non-conductive case which ensures that user contact with potentially live parts is prevented
- Class II equipment may have a functional earth, but this **does not** provide any electrical shock protection
- Class II equipment is required to be marked with the following symbol:
 ![[Pasted image 20220215120210.png]]

---
# Electrical Hazards
- Electric shocks occur when the boy forms part on an electric circuit

### Macroshock
- When the human body becomes a conductor of electric current by means **other than directly through the heart**.
- All patient areas are required to be wired at least as body-protected areas to reduce the likelihood of macroshock

### Microshock
- Current as small as 100 µA, **which flows through a small cross-section of ventricular heart muscle**
- **Microshock may not be obvious** as no outward and physically visible stimulus or contraction occurs.**

---
## Patient Areas
- A patient area is the location where low-voltage (mains operated to 230V) medical electrical equipment is intended to be used on a patient
- Notably, this **does** **not include areas such as corridors and lifts** where such equipment is only used in an emergency situation

![[Pasted image 20220215132609.png]]
### Patient Location
* Any intended location of the bed, table or seating arrangement for a patient, **whether or not occupied by the patient**
* The patient location can extend to the entire room

### Patient Environments
* The space extending **1500 mm** around all possible patient locations in a cardiac-protected electrical area
* Where adjacent patient environments overlap, the **combined area is deemed one patient environment**
* A patient environment may contain **one or more patient locations**

### Patient Areas
* The boundary of a patient area extends to the walls enclosing the patient location(s)

## Equipotential Earthing
- Equipotential earthing systems are designed to reduce the potential difference appearing between any conducting surfaces in the vicinity of the patient to a level **well below that which would produce microshock electrocution**
	- i.e. Connecting everything conductive to ground so that the potential difference between any two surfaces is very very low
- All Class I electrical equipment shall be earthed via the EP junction or node if any earthed parts are accessible in the patient environment
- In our testing all **non-isolated metallic structures need to be 0.1 Ω to the EPJ**, including GPO earths
