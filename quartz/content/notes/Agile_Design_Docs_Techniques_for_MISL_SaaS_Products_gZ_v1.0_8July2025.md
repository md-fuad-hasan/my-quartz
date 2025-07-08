---
marp: true
---

[[Agile_SaaS_C4_Design_Context_n_Capability_Map_README_gZ_v1.0_8July2025]]

Here’s a **comprehensive guide** to Agile-friendly design documentation techniques that complement architecture models (like C4) but focus on **requirements analysis, design elaboration, and testing**—especially useful for SaaS product development in **MISL SylviaNG** projects.

This includes:

1. **User Stories (Epic, Mid, Detailed Levels)**
2. **Story Tests (Acceptance Criteria / BDD Style)**
3. **Interface & Collaboration Diagrams (UML Communication Diagrams)**
4. **Robustness Diagrams (for Early Design Analysis)**
5. **Class Diagrams (Static Object Structure)**
6. **Sequence Diagrams (Dynamic Interactions Over Time)**

---

# 📝 **Agile Design Documentation Techniques for MISL SaaS**

---

## ✅ **1. User Stories (Epic → Mid → Detail Levels)**

User Stories in Agile are **incrementally refined**:

- **Epics:** Large, coarse-grained features that span multiple sprints.
- **Mid-Level Stories (Capabilities / Features):** Smaller, deliverable chunks within an Epic.
- **Detailed User Stories:** Sprint-ready, actionable, with acceptance criteria.

---

### **Example for SylviaNG Payroll SaaS – Payroll Run Epic:**

#### **Epic Story:**

> **As a Payroll Manager, I want to automate payroll processing, so that I can ensure accurate and timely salary disbursement.**

---

#### **Mid-Level Story (Feature Story):**

> **As a Payroll Manager, I want to generate payslips for employees in bulk after payroll is processed.**

---

#### **Detailed Story:**

> **As a Payroll Manager, I want to download payslips as PDFs for employees after completing payroll, so that I can archive them.**

---

### **Agile Practice:**

- Keep **Epic → Mid → Detail** linkage traceable.
- Link these stories to **BPMN Diagrams, C4 Components, and Sequence Diagrams** for better traceability.

---

## ✅ **2. Story Tests / Acceptance Criteria (BDD Style)**

Agile Story Tests ensure shared understanding via **examples** and **expected outcomes**.

---

#### **Sample Story Test (for Payslip Download Story):**

```gherkin
Scenario: Successful Payslip PDF Download
Given payroll has been processed for July 2025
And the Payroll Manager is logged in
When the Payroll Manager downloads payslips
Then the system generates a PDF for each employee
And marks the download as completed in the payroll log
```

---

#### ✅ Key Guidelines:

- Use **Gherkin / BDD** style for clarity.
- Automate these tests wherever possible.
- Link story tests to Sequence Diagrams (to show flow behind the test).

---

## ✅ **3. Interface / Collaboration Diagrams (UML Communication Diagrams)**

Used to **show objects/components collaborating** to fulfill a user story.

---

#### **Example: Collaboration Diagram for "Payroll Run + Payslip Download"**

```
[Payroll Manager] → (Payroll Controller) → (Payroll Calculator) → (PDF Generator)
                                         ↘ (Payroll Log Service)
```

---

#### ✅ Best Practices:

- Show main collaborating objects/services.
- Use these to **refine or validate** your C4 Container Diagrams.
- Focus on _business-relevant interactions_ (skip low-level technical details here).

---

## ✅ **4. Robustness Diagrams (Early Design Analysis Tool)**

Originating from ICONIX Process, these help clarify **boundary, control, and entity classes** before detailed design.

---

#### **Symbols:**

| Type     | Symbol/Shape | Purpose                       |
| -------- | ------------ | ----------------------------- |
| Actor    | Stick Figure | External user or system       |
| Boundary | Rounded Box  | UI or API boundary interface  |
| Control  | Diamond      | Orchestrates the process      |
| Entity   | Rectangle    | Business object / data object |

---

#### **Example: Robustness Diagram for Payslip Download**

```
[Payroll Manager] —> (Payslip Download Screen) —> ◇ (Payslip Download Controller) —> [Payslip Entity]
```

---

#### ✅ Best Uses:

- Quickly analyze story before jumping into code.
- Validate responsibilities (UI, logic, data separation).
- Can be refined into Class and Sequence Diagrams.

---

## ✅ **5. Class Diagrams (Static Structure Modeling)**

Class diagrams document **the object model** (entities, attributes, methods, relationships).

---

#### **Example Class Diagram (Partial Payslip Model):**

```
+-------------------+
|   Payslip         |
+-------------------+
| - id              |
| - employeeId      |
| - period          |
| - totalAmount     |
+-------------------+
| +generatePDF()    |
| +sendToEmployee() |
+-------------------+

Payslip *--1 Employee
```

---

#### ✅ Best Practices:

- Keep class diagrams **high-level** in Agile (focus on core business objects).
- Model only **significant relationships** (composition, aggregation, inheritance).
- Avoid excessive modeling—keep it evolving with the code.

---

## ✅ **6. Sequence Diagrams (Dynamic Interactions Over Time)**

Show **time-ordered interactions** between objects/services in a scenario.

---

#### **Example Sequence Diagram: Payslip Download**

```
Payroll Manager → Payslip Controller → Payroll Service → PDF Generator → Storage Service
```

#### **Steps:**

1. Payroll Manager requests download.
2. Controller validates request.
3. Payroll Service fetches payslip data.
4. PDF Generator generates the document.
5. Storage Service stores & returns download link.

---

#### ✅ Key Usage:

- Model **critical flows** (especially across microservices or external APIs).
- Align with Story Tests & BPMN flows.
- Limit to **key components** per diagram (avoid overwhelming detail).

---

## ✅ **How They Fit Together (Workflow Map):**

```
User Story (Epic → Mid → Detail)
        ↓
Story Tests (Acceptance Criteria)
        ↓
Robustness Diagram (Boundary, Control, Entity)
        ↓
Collaboration Diagram (Object Collaborations)
        ↓
Class Diagram (Static Structure)
        ↓
Sequence Diagram (Dynamic Flow of Operations)
```

---

## ✅ **Practical Guidelines for MISL SylviaNG Agile Projects:**

| Artifact                         | Purpose                                                | When to Create                                |
| -------------------------------- | ------------------------------------------------------ | --------------------------------------------- |
| User Stories                     | Capture business value and needs                       | Product Backlog Grooming, Sprint Planning     |
| Story Tests                      | Ensure shared understanding & test cases               | During Sprint Planning or Refinement          |
| Robustness Diagrams              | Validate system boundary & logic early                 | Before detailed design, early design analysis |
| Interface/Collaboration Diagrams | Map object/service collaborations for complex stories  | During Feature Design, or Service Design      |
| Class Diagrams                   | Define object relationships & data models              | During Development or Refactoring             |
| Sequence Diagrams                | Capture complex workflows or microservice interactions | Before/after key implementation phases        |

---

## ✅ **Tools You Can Use (MISL-Friendly)**

| Diagram Type          | Suggested Tools                        |
| --------------------- | -------------------------------------- |
| User Stories & Tests  | Jira, Confluence, GitHub Issues        |
| UML Diagrams          | PlantUML, Mermaid (for Markdown / Git) |
| BPMN & Process Models | Camunda Modeler, BPMN.io               |
| Sequence Diagrams     | PlantUML, Mermaid Sequence, Lucidchart |

---

## ✅ **Key Tip for Agile Teams:**

> “Create diagrams just enough to clarify and unblock delivery—not as a deliverable in itself. Make them evolve alongside code.”

---
