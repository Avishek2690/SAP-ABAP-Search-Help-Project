# SAP-ABAP-Search-Help-Project
<!--SAP ABAP project demonstrating the implementation of Elementary and Collective Search Helps using LIKP and LIPS tables. Developed a unified F4 help interface to improve data retrieval, user navigation, and search functionality within SAP applications.
-->

## Project Overview

This project demonstrates the development of a custom SAP ABAP Collective Search Help by combining multiple Elementary Search Helps into a single reusable search interface.

The solution enables users to retrieve both Delivery Header and Delivery Item information through a unified F4 help, improving usability and simplifying data selection within SAP applications.

---

## Business Scenario

In many SAP business processes, users need quick access to delivery-related information while entering or searching for documents.

Instead of maintaining separate search helps for:

- Delivery Header Data (LIKP)
- Delivery Item Data (LIPS)

a Collective Search Help was designed to provide both datasets through a single search interface.

This approach improves user experience and reduces navigation complexity.

---

## Objective

The objective of this project was to:

- Create custom Elementary Search Helps.
- Develop a Collective Search Help.
- Integrate multiple search helps into a single F4 Help.
- Enable efficient delivery document search.
- Demonstrate SAP Data Dictionary (DDIC) concepts.

---

## Technical Implementation

### Step 1: Elementary Search Help for LIKP

Created an Elementary Search Help using the LIKP (Delivery Header) table.

#### Fields Included

| Field | Description |
|---------|-------------|
| VBELN | Delivery Number |
| ERNAM | Created By |
| BZIRK | Sales District |

---

### Step 2: Elementary Search Help for LIPS

Created an Elementary Search Help using the LIPS (Delivery Item) table.

#### Fields Included

| Field | Description |
|---------|-------------|
| VBELN | Delivery Number |
| POSNR | Item Number |
| ERNAM | Created By |

---

### Step 3: Collective Search Help

Created a Collective Search Help that combines:

- ZAVI_MINIPRO_SH1_LIKP
- ZAVI_MINIPRO_SH2_LIPS

The collective search help allows users to switch between Delivery Header and Delivery Item information within the same search interface.

---

### Step 4: Program Integration

Integrated the Collective Search Help into an ABAP report using the MATCHCODE OBJECT parameter.

```abap
PARAMETERS:
  p_vbeln TYPE char10
  MATCHCODE OBJECT ZAVI_MINIPRO_SH3_CTIVE.
```

This enables F4 search functionality directly from the selection screen.

---

## Tables Used

| Table | Description |
|---------|-------------|
| LIKP | Delivery Header Data |
| LIPS | Delivery Item Data |

---

## Technologies Used

- SAP ABAP
- SAP Data Dictionary (DDIC)
- Elementary Search Help
- Collective Search Help
- Matchcode Object
- Selection Screen Programming

---

## Project Architecture

## Project Flow

```text
                    ┌────────────┐      ┌────────────┐
                    │    LIKP    │      │    LIPS    │
                    │  Header    │      │    Item    │
                    └─────┬──────┘      └─────┬──────┘
                          │                   │
                          ▼                   ▼

                    ┌────────────┐      ┌────────────┐
                    │ SH1_LIKP   │      │ SH2_LIPS   │
                    │ Elementary │      │ Elementary │
                    └─────┬──────┘      └─────┬──────┘
                          │                   │
                          └─────────┬─────────┘
                                    ▼

                       ┌─────────────────────┐
                       │      SH3_CTIVE      │
                       │   Collective SH     │
                       └──────────┬──────────┘
                                  │
                                  ▼

                       ┌─────────────────────┐
                       │   ABAP Selection    │
                       │   Screen 🔍 F4 Help │
                       └──────────┬──────────┘
                                  │
                                  ▼

                       ┌─────────────────────┐
                       │   User Selection    │
                       │    Delivery Data    │
                       └─────────────────────┘
```
## Screenshots

### ABAP Program

![ABAP Program](screenshots/01-program-code.png)

---

### Elementary Search Help – LIKP

![LIKP Search Help](screenshots/02-sh-likp.png)

---

### Elementary Search Help – LIPS

![LIPS Search Help](screenshots/03-sh-lips.png)

---

### Collective Search Help Configuration

![Collective Search Help](screenshots/04-collective-sh.png)

---

### Final Output

![Output](screenshots/05-output.png)

---

## Key Learnings

Through this project, I gained practical experience in:

- SAP Data Dictionary (DDIC)
- Search Help Creation
- Elementary Search Helps
- Collective Search Helps
- Matchcode Objects
- Selection Screen Development
- SAP ABAP Report Integration

---

## Outcome

Successfully developed and integrated a custom Collective Search Help that combines delivery header and item information into a single reusable F4 Help.

The solution improves user navigation, simplifies document search, and demonstrates practical implementation of SAP Data Dictionary concepts.

---

## Author

**Avishek Chourasiya**

SAP ABAP Developer Intern | Computer Science Student

LinkedIn:
linkedin.com/in/avishek-chourasiya
