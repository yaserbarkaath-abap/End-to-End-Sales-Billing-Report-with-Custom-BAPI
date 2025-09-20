# End-to-End-Sales-Billing-Report-with-Custom-BAPI
I’m excited to share my hands-on experience with Assignment 
where I developed a complete ABAP report (ZA_2)
To manage sales order and billing data — including display, update, and messaging functionalities.

------------------------------------------------------------------------------------------------------------------------

**📋 Requirement Overview:**
**Create an ALV report using tables:** 
VBAP, VBAK, VBRK, VBRP, VBPA, MARA.
**Selection screen with: Select-options**
Sales Order, Invoice Type, Billing Date (defaulted to current date), Material, Material Type, New Sales Order Quantity.
**Two radio buttons:**
Change Sales Order Quantity
Display Sales Order Document
**Display ALV Grid with**
sorting, filtering, export to Excel/XML.
**Click on Change radio button:**
Change the sales order QTY using BAPI and display success/error message based on the BAPI return
**On successful change through BAPI**
send an email to the user letting them know that sales order QTY has been updated successfully

------------------------------------------------------------------------------------------------------------------------

**🛠️ How I Implemented It:**
**1️⃣ Report Development (SE38)**
**Created report ZA_2 with modular forms:**
Display_Data – for ALV output.
Change_CSOQ – for updating quantity via BAPI.
**2️⃣ Selection Screen**
Used SELECTION-SCREEN blocks with:
SELECT-OPTIONS for filtering.
PARAMETERS for input fields.
RADIOBUTTON GROUP for mode selection.
Defaulted billing date to SY-DATUM.
**3️⃣ ALV Grid Display**
Used REUSE_ALV_GRID_DISPLAY with custom field catalog.
**Added toolbar options:**
Sort, Filter, Export to Excel/XML.
Created GUI status using SE41 to add custom buttons like XML export.
**4️⃣ XML Transformation (STRANS)**
Created a simple transformation Z_XML_A2 to convert internal table data to XML format.
Used CALL TRANSFORMATION and GUI_DOWNLOAD to export XML.
**5️⃣ Custom BAPI Creation (SE37)**
Created function module ZBAPI_A2_CSOQ to update sales order quantity.
Included logic to return success/error messages.
**6️⃣ Business Object Setup (SWO1)**
Created a custom business object.
Added method to call the BAPI.
Implemented and released the object for use in workflows or external calls.
**7️⃣ Messaging Logic**
Since SCOT configuration was not available in the SAP Learning Hub practice system, I couldn’t use standard email functionality.
Instead, I used cl_bcs_message to simulate email alerts.
Commented out cl_document_bcs and cl_cam_address_bcs logic for future use in real SAP environments.

------------------------------------------------------------------------------------------------------------------------

**🔍 T-Codes Used:**
T-Code  Purpose
SE38  Report development
SE11   Table/view definitions
SE37   BAPI creation
SE41   GUI status for ALV toolbar
STRANS  XML transformation
SWO1    Business Object creation & releaseZBUSA_2BAPI structure setup
SCOT(Attempted) email config – not available in SAP Learning Hub

------------------------------------------------------------------------------------------------------------------------

**📦 Tables Used:**
VBAK, VBAP – Sales Order Header & Item
VBRK, VBRP – Billing Header & Item
VBPA – Sales Partner
MARA – Material Master

------------------------------------------------------------------------------------------------------------------------

**This assignment helped me gain practical experience in:**
Modular ABAP programming
ALV reporting with toolbar customization
Custom BAPI creation and release
SAP messaging frameworks
XML transformation and export


