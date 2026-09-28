# Streamlining IT Procurement: Automating Standard Laptop Request

## Project Overview
This ServiceNow project automates the IT procurement workflow for ordering standard laptops using **Flow Designer** and **Service Catalog**. It eliminates manual intervention by automatically triggering task creation and assignment to the Hardware team upon request approval.

---

## Project Artifacts & Details

- **Flow Name:** `Standard laptop task`
- **Application:** Global
- **Run As:** System User
- **Associated Service Catalog Item:** Standard Laptop
- **Assignment Group:** Hardware
- **Generated Records:**
  - **RITM:** `RITM0010001` (Requested Item)
  - **SCTASK:** `SCTASK0010001` (Catalog Task)

---

## Step-by-Step Implementation Workflow

### Step 1: Flow Creation (Flow Designer)
1. Navigated to **Process Automation > Flow Designer**.
2. Created a new Flow named **`Standard laptop task`**.
3. Configured properties:
   - **Application:** Global
   - **Run As:** System user
4. Configured Trigger:
   - **Trigger:** Service Catalog
5. Added Action:
   - **Action Name:** `Create Catalog Task`
   - **Request Item:** Dragged and dropped the `Requested Item Record` from the data panel.
   - **Short Description:** `Laptop need to Configured`
   - **Description:** `Laptop need to Configured`
   - **Assignment Group:** `Hardware`
   - **Approval:** `Approved`
6. **Saved** and **Activated** the flow.

---

### Step 2: Flow Assignment to Service Catalog
1. Navigated to **Service Catalog > Maintain Items**.
2. Opened catalog item **`Standard Laptop`**.
3. Under the **Process Engine** tab, assigned Flow: **`Standard laptop task`**.
4. Saved the record.

---

### Step 3: End-to-End Testing & Verification
1. Opened **Service Catalog > Hardware > Standard Laptop**.
2. Clicked **Order Now** to place a request.
3. Approved the generated Request record (`REQ0010001`).
4. Verified that Requested Item (`RITM0010001`) triggered the flow.
5. Confirmed that Catalog Task (`SCTASK0010001`) was automatically generated with Short Description **`Laptop need to Configured`** and assigned to **`Hardware`**.

---

## Exported Data
The raw XML data for both `RITM0010001` and `SCTASK0010001` is stored in the file [`servicenow_data.xml`](./servicenow_data.xml).
# servicenow-laptop-procurement
Automating Standard Laptop Procurement Process in ServiceNow using Flow Designer
