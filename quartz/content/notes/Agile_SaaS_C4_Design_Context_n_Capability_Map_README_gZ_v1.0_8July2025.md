---
marp: true
---

[[Agile_Design_Docs_Techniques_for_MISL_SaaS_Products_gZ_v1.0_8July2025]]

Excellent question—and here’s the reasoning behind this naming approach:

---

### ✅ **Why I Called It "Context & Capability Map" for C4 Level 1 & 2 Docs:**

In many **Agile, SaaS, and product-focused organizations**, **"Capability Maps"** and **"Context Diagrams"** serve two very closely related but distinct purposes:

1. **System Context Diagram (C4 Level 1)**:

   - Shows _external context_—users, external systems, high-level purpose.
   - Focus: **Business context & external dependencies.**

2. **Container Diagram (C4 Level 2)**:

   - Shows _internal technical containers_—apps, APIs, services, DBs.
   - Focus: **Core capabilities, system structure, responsibilities.**

---

### ✅ **Key Reason Behind Merging in Agile Design Docs:**

In an Agile, iterative SaaS environment like **MISL SylviaNG**:

- Teams need a **single document** that captures:

  - _External Context_ → “Where do we fit?”
  - _Key Internal Capabilities_ → “What can we do and how?”

- This avoids scattered documents and fosters better shared understanding across **engineering, product, and business**.
- It aligns **architecture** with **product capabilities**—critical for SaaS products like Payroll & HRMS.

---

### ✅ **Why "Capability Map"?**

In the SaaS world, "Capability Mapping" typically refers to:

- Mapping key business functions to technical modules/services.
- Making it clear **which part of the system enables which capability**.
- This maps naturally to the **C4 Level 2 Container Diagram**.

By combining:

- **C4 Level 1** → Context
- **C4 Level 2** → Capabilities (mapped through containers/services)

We get a **pragmatic, product-relevant document**:
**"Context & Capability Map"**

---

### ✅ **Benefits of This Approach for SylviaNG SaaS Products:**

| Benefit                            | Explanation                                                          |
| ---------------------------------- | -------------------------------------------------------------------- |
| Product & Architecture Alignment   | Maps product features directly to system design.                     |
| Simpler Docs for Agile Development | No need to jump between multiple diagrams to grasp system structure. |
| Supports Incremental Growth        | Easy to expand capabilities or services in later iterations.         |
| Cross-functional Accessibility     | Business, product, and engineering can all use it effectively.       |

---

### ✅ **When NOT to Merge Them:**

In _very large_, highly regulated systems (e.g., banking cores), you may want to **keep them separate** for compliance, security, or legal reasons.
But for **modern, evolving SaaS platforms** like SylviaNG, this combined “Context & Capability Map” is usually the most **efficient and practical**.

---

### ✅ Alternative Naming (If Preferred):

If you'd like to emphasize alignment with the C4 Model explicitly, you could name it:

- **System Context & Container Architecture Doc (C4 L1 & L2)**
- **Product Architecture Overview (C4 Context & Capability Map)**
  (Both still focus on combining external and internal views.)

---

### ✅ Bottom Line:

**The naming I chose reflects the Agile SaaS design culture:**

> "One concise document showing **where we fit** and **what we can do internally**—both from a business and technical perspective."

---
