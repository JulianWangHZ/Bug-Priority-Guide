<!-- README.md -->
# 🚦 Bug Priority Guide (P0–P4)

[English](README.md) | [中文](README_zh.md)

Bugs are classified by **urgency** into five levels (**P0–P4**), each with a clear target **fix window**. This guide standardizes scheduling in development and operations to protect system stability and user experience.

---

## 📚 Table of Contents <a id="toc"></a>
- [Why Priority?](#why-priority)
- [Definitions at a Glance](#definitions-at-a-glance)
- [Priority Levels](#priority-levels)
  - [🔴 P0 — Critical (fix same day)](#p0)
  - [🟡 P1 — High (fix within 5 business days)](#p1)
  - [🟣 P2 — Medium (fix within 2 weeks)](#p2)
  - [🔵 P3 — Low (fix within 1 month, or as appropriate)](#p3)
  - [🟢 P4 — Non-priority (report only)](#p4)
- [Remediation Time Targets](#remediation-time-targets)
- [Distinguishing P2 vs P3](#p2-vs-p3)

---

## Why Priority? <a id="why-priority"></a>

Priority expresses **when** a bug should be addressed. Clear levels and time targets help teams allocate resources, coordinate releases, and avoid unnecessary operational risk.

---

## Definitions at a Glance <a id="definitions-at-a-glance"></a>

- **P0–P4**: five urgency levels, each with a target **fix window**  
- Applied across feature development and production operations  
- Used alongside severity (impact) to make balanced, auditable decisions

---

## Priority Levels <a id="priority-levels"></a>

### 🔴 P0 — Critical (fix same day) <a id="p0"></a>
**Definition**
- System or major functionality is completely unavailable  
- Core business is fully blocked  
- Must be addressed immediately or all users are affected

**Examples (common)**
- Global **login outage** (sign-in fails for all users)  
- **Checkout/payment** succeeds on client but order or capture is not recorded  
- Critical **API/service outage** (dashboards/lists do not load for all tenants)

---

### 🟡 P1 — High (fix within 5 business days) <a id="p1"></a>
**Definition**
- Affects primary functionality while the system remains usable  
- Serious disruption without a full outage

**Examples (common)**
- Core **form submission** fails (“Save/Submit” returns an error) for many users; data must be re-entered or a different browser used  
- **Password reset / 2FA codes** not delivered to a large subset of users; support can verify or reset accounts manually  
- **File upload** for common types (PDF/CSV) fails; users must email files to support or switch to a workaround  
- **Settings/profile changes** cannot be saved in-app; an admin can update values via the admin console

---

### 🟣 P2 — Medium (fix within 2 weeks) <a id="p2"></a>
**Definition**
- Impacts secondary features or specific scenarios  
- Risks data correctness or increases manual workload  
- Should be fixed promptly to prevent persistent friction

**Examples (common)**
- List **sorting/pagination** inconsistent (e.g., newest not first; last page duplicates or misses items)  
- **Filter state** not retained after navigation; users must re-apply filters  
- **Autosave** intermittently fails; manual save works reliably  
- **Notifications/badge counts** update several minutes late  
- **CSV export** headers/order require light cleanup in a spreadsheet tool

---

### 🔵 P3 — Low (fix within 1 month, or as appropriate) <a id="p3"></a>
**Definition**
- Minor UI issues or small delays; tasks remain completable  
- Experience/appearance problems with no material business risk  
- Schedule as optimization or routine release fix

**Examples (common)**
- **Button/icon alignment** slightly off on mobile but remains clickable  
- **Loading/skeleton** shows briefly; counts update after a few seconds  
- **Truncated long names** in lists, full value still accessible via tooltip/detail

---

### 🟢 P4 — Non-priority (report only; optional fix) <a id="p4"></a>
**Definition**
- Pure visual/style details with no functional/business impact  
- Optional fix that may be queued as a future enhancement

**Examples (common)**
- **Copy tone/microcopy** preference (e.g., emoji usage)  
- Non-standardized **version string** format (e.g., `4.0.1-1203beta`)  
- Request for **polish-only animation** or subtle visual refinement

---

## 📌 Remediation Time Targets <a id="remediation-time-targets"></a>

- 🔴 **P0**: **same day**  
- 🟡 **P1**: **within 5 business days**  
- 🟣 **P2**: **within 2 weeks**  
- 🔵 **P3**: **within 1 month**, or as appropriate  
- 🟢 **P4**: **report only**; fix is optional

---

## 📌 Distinguishing P2 vs P3 <a id="p2-vs-p3"></a>

- **🟣 P2 — Medium**
  - Functional issues that create **manual rework** or **confusing outcomes**  
  - ✅ Examples: list **sorting/pagination** incorrect; export **headers/order** require cleanup

- **🔵 P3 — Low**
  - **UI/UX** quirks that do **not** prevent task completion  
  - ✅ Examples: minor **alignment/spacing**; **truncation** with tooltip; brief **delayed counters**
