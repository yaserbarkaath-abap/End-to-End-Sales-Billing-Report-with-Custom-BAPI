<h1>End-to-End Sales Billing Report with Custom BAPI</h1>

<p>I’m excited to share my hands on experience with an assignment where I developed a complete ABAP report (<b>ZA_2</b>) to manage sales order and billing data including display, update, and messaging functionalities.</p>

<hr>

<h3>📋 Requirement Overview:</h3>
<ul>
  <li>Create an ALV report using tables: <b>VBAP, VBAK, VBRK, VBRP, VBPA, MARA</b></li>
  <li>Selection screen with: Sales Order, Invoice Type, Billing Date (default = current date), Material, Material Type, New Sales Order Quantity</li>
  <li>Two radio buttons: Change Sales Order Quantity / Display Sales Order Document</li>
  <li>ALV Grid with sorting, filtering, export to Exce and /XML</li>
  <li>On Change mode: Update Sales Order QTY via BAPI → show success/error message</li>
  <li>On success: send email notification to user</li>
</ul>

<hr>

<h3>🛠️ How I Implemented It:</h3>
<ol>
  <li><b>Report Development (SE38):</b> Modular forms for ALV output & BAPI update</li>
  <li><b>Selection Screen:</b> Select-options, parameters, radio buttons, default billing date</li>
  <li><b>ALV Grid:</b> REUSE_ALV_GRID_DISPLAY + custom toolbar (Sort, Filter, Export)</li>
  <li><b>XML Transformation (STRANS):</b> Z_XML_A2 + GUI_DOWNLOAD</li>
  <li><b>Custom BAPI (SE37):</b> ZBAPI_A2_CSOQ for updating sales order quantity</li>
  <li><b>Business Object (SWO1):</b> Released for workflows/external calls</li>
  <li><b>Messaging:</b> Simulated email alerts via <code>cl_bcs_message</code></li>
</ol>

<hr>

<h3>🔍 T-Codes Used:</h3>
<ul>
  <li>SE38 – Report Development</li>
  <li>SE11 – Table/View Definitions</li>
  <li>SE37 – BAPI Creation</li>
  <li>SE41 – ALV Toolbar Customization</li>
  <li>STRANS – XML Transformation</li>
  <li>SWO1 – Business Object Setup</li>
  <li>SCOT – Email Config (attempted)</li>
</ul>

<hr>

<h3>📦 Tables Used:</h3>
<ul>
  <li>VBAK, VBAP – Sales Order Header & Item</li>
  <li>VBRK, VBRP – Billing Header & Item</li>
  <li>VBPA – Sales Partner</li>
  <li>MARA – Material Master</li>
</ul>

<hr>

<h3>🚀 Key Learnings:</h3>
<ul>
  <li>Modular ABAP programming</li>
  <li>ALV reporting with toolbar customization</li>
  <li>Custom BAPI creation & release</li>
  <li>SAP messaging frameworks</li>
  <li>XML transformation & export</li>
</ul>
