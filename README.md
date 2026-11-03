/* =====================================================================
   MAY HARVEST CORPORATION - PRODUCT QUEUING SYSTEM
   ISANG JAVASCRIPT FILE LANG (CSS + HTML + JS nasa loob na nito)

   Paano gamitin:
   1) I-save ang file na ito bilang  app.js
   2) Gumawa ng index.html (sa parehong folder) na may ganito:

        <!DOCTYPE html>
        <html lang="en">
        <head><meta charset="UTF-8"></head>
        <body>
        <script src="app.js"></script>
        </body>
        </html>

   Note: kailangan pa rin sa parehong folder ang
         "MHC New Background-1024.jpg" (background image).
   ===================================================================== */

(function buildPage() {

    /* ---------- PAGE TITLE / VIEWPORT ---------- */
    document.documentElement.lang = "en";
    document.title = "May Harvest Corporation - Product Queuing System";

    if (!document.querySelector('meta[name="viewport"]')) {
        var meta = document.createElement("meta");
        meta.name = "viewport";
        meta.content = "width=device-width, initial-scale=1.0";
        document.head.appendChild(meta);
    }

    /* ---------- CSS ---------- */
    var PAGE_CSS = `

/* =========================================================
   GLOBAL
========================================================= */

* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;

    font-family:
        Arial,
        Helvetica,
        sans-serif;
}

html {
    min-height: 100%;
}

body {

    min-height: 100vh;

    color: #1e293b;

    /*
     * MHC BACKGROUND
     *
     * Make sure this file is in the same folder
     * as this HTML file.
     */

    background-color: #087a3a;

    background-image:
        linear-gradient(
            rgba(255,255,255,0.08),
            rgba(255,255,255,0.08)
        ),
        url("MHC New Background-1024.jpg");

    background-size: cover;

    background-position:
        center center;

    background-repeat: no-repeat;

    background-attachment: fixed;
}


/* =========================================================
   HEADER
========================================================= */

header {

    background:
        linear-gradient(
            135deg,
            rgba(5,74,42,0.98),
            rgba(15,23,42,0.98)
        );

    color: white;

    padding:
        14px 25px;

    display: flex;

    justify-content:
        space-between;

    align-items:
        center;

    gap: 15px;

    flex-wrap: wrap;

    box-shadow:
        0 3px 12px rgba(0,0,0,0.25);

    position: relative;

    z-index: 60;
}


/* =========================================================
   MHC BRAND
========================================================= */

.brand-area {

    display: flex;

    align-items: center;

    gap: 15px;
}


.logo-container {

    width: 75px;

    height: 75px;

    background: white;

    border-radius: 12px;

    padding: 5px;

    display: flex;

    align-items: center;

    justify-content: center;

    flex-shrink: 0;

    box-shadow:
        0 3px 10px rgba(0,0,0,0.25);
}


.mhc-logo {

    width: 100%;

    height: 100%;

    object-fit: contain;

    border-radius: 8px;
}


.brand-text h1 {

    font-size: 22px;

    font-weight: 800;

    color: white;

    margin: 0;

    letter-spacing:
        0.3px;
}


.brand-text h2 {

    font-size: 15px;

    font-weight: 700;

    color: #86efac;

    margin:
        4px 0;

    letter-spacing:
        0.8px;
}


.brand-text small {

    color: #cbd5e1;

    font-size: 12px;
}


#clock {

    font-size: 14px;

    color: #dcfce7;

    font-weight: bold;

    text-align: right;
}


/* =========================================================
   NAVIGATION
========================================================= */

.navbar {

    background:
        rgba(255,255,255,0.97);

    border-bottom:
        1px solid #e2e8f0;

    display: flex;

    gap: 5px;

    padding:
        10px 20px;

    position: sticky;

    top: 0;

    z-index: 50;

    box-shadow:
        0 2px 7px rgba(0,0,0,0.08);
}


.nav-btn {

    background:
        #f1f5f9;

    color:
        #334155;

    border: none;

    padding:
        11px 18px;

    border-radius:
        7px;

    cursor: pointer;

    font-weight:
        bold;

    transition:
        0.2s;
}


.nav-btn:hover {

    background:
        #dcfce7;

    color:
        #166534;
}


.nav-btn.active {

    background:
        #15803d;

    color:
        white;
}


/* =========================================================
   MAIN CONTAINER
========================================================= */

.container {

    max-width:
        1500px;

    margin:
        auto;

    padding:
        20px;
}


/* =========================================================
   SCREENS
========================================================= */

.screen {

    display:
        none;
}


.screen.active {

    display:
        block;
}


/* =========================================================
   CARDS
========================================================= */

.card {

    background:
        rgba(255,255,255,0.96);

    border-radius:
        12px;

    padding:
        20px;

    box-shadow:
        0 3px 12px rgba(0,0,0,0.12);

    margin-bottom:
        20px;
}


.card h2 {

    margin-bottom:
        18px;
}


/* =========================================================
   REGISTRATION
========================================================= */

.registration-container {

    max-width:
        700px;

    margin:
        20px auto;
}


.registration-title {

    text-align:
        center;

    margin-bottom:
        20px;

    background:
        rgba(255,255,255,0.93);

    padding:
        18px;

    border-radius:
        12px;

    box-shadow:
        0 2px 8px rgba(0,0,0,0.10);
}


.registration-title h2 {

    font-size:
        28px;

    color:
        #166534;
}


.registration-title p {

    color:
        #64748b;

    margin-top:
        5px;
}


/* =========================================================
   FORM
========================================================= */

.form-grid {

    display:
        grid;

    grid-template-columns:
        1fr 1fr;

    gap:
        15px;
}


.form-group.full {

    grid-column:
        1 / -1;
}


label {

    display:
        block;

    font-weight:
        bold;

    font-size:
        14px;

    margin-bottom:
        6px;
}


input,
select {

    width:
        100%;

    padding:
        12px;

    border:
        1px solid #cbd5e1;

    border-radius:
        7px;

    font-size:
        15px;

    background:
        white;
}


input:focus,
select:focus {

    outline:
        none;

    border-color:
        #16a34a;

    box-shadow:
        0 0 0 3px rgba(22,163,74,0.10);
}


/* =========================================================
   BUTTONS
========================================================= */

button {

    border:
        none;

    border-radius:
        7px;

    padding:
        10px 15px;

    cursor:
        pointer;

    font-weight:
        bold;

    transition:
        0.2s;
}


button:hover {

    opacity:
        0.9;

    transform:
        translateY(-1px);
}


.btn-primary {

    background:
        #15803d;

    color:
        white;
}


.btn-success {

    background:
        #16a34a;

    color:
        white;
}


.btn-warning {

    background:
        #f59e0b;

    color:
        white;
}


.btn-danger {

    background:
        #dc2626;

    color:
        white;
}


.btn-secondary {

    background:
        #64748b;

    color:
        white;
}


.btn-dark {

    background:
        #0f172a;

    color:
        white;
}


.big-button {

    width:
        100%;

    padding:
        15px;

    font-size:
        17px;

    margin-top:
        10px;
}


/* =========================================================
   REGISTRATION SUCCESS
========================================================= */

.success-ticket {

    display:
        none;

    background:
        #ecfdf5;

    border:
        2px solid #22c55e;

    border-radius:
        12px;

    padding:
        25px;

    text-align:
        center;

    margin-top:
        20px;

    box-shadow:
        0 3px 10px rgba(0,0,0,0.10);
}


.success-ticket.show {

    display:
        block;
}


.success-ticket h2 {

    color:
        #15803d;

    margin-bottom:
        10px;
}


.queue-big {

    font-size:
        65px;

    font-weight:
        bold;

    color:
        #15803d;

    margin:
        15px 0;
}


.ticket-info {

    line-height:
        1.8;

    margin-bottom:
        15px;
}


/* =========================================================
   DASHBOARD STATS
========================================================= */

.stats {

    display:
        grid;

    grid-template-columns:
        repeat(5, 1fr);

    gap:
        15px;

    margin-bottom:
        20px;
}


.stat-card {

    background:
        rgba(255,255,255,0.96);

    border-radius:
        12px;

    padding:
        18px;

    box-shadow:
        0 3px 10px rgba(0,0,0,0.12);
}


.stat-card h3 {

    color:
        #64748b;

    font-size:
        13px;

    margin-bottom:
        8px;
}


.stat-number {

    font-size:
        30px;

    font-weight:
        bold;
}


.blue {

    color:
        #2563eb;
}


.orange {

    color:
        #f59e0b;
}


.green {

    color:
        #16a34a;
}


.gray {

    color:
        #64748b;
}


.red {

    color:
        #dc2626;
}


/* =========================================================
   DASHBOARD GRID
========================================================= */

.dashboard-grid {

    display:
        grid;

    grid-template-columns:
        350px 1fr;

    gap:
        20px;
}


/* =========================================================
   CURRENT TRUCK
========================================================= */

.current-truck {

    background:
        linear-gradient(
            135deg,
            #166534,
            #15803d
        );

    color:
        white;

    padding:
        25px;

    border-radius:
        12px;

    text-align:
        center;

    margin-bottom:
        20px;

    box-shadow:
        0 4px 12px rgba(0,0,0,0.20);
}


.current-label {

    font-size:
        14px;

    color:
        #dcfce7;
}


.current-queue {

    font-size:
        55px;

    font-weight:
        bold;

    margin:
        10px;
}


.current-truck-number {

    font-size:
        22px;

    font-weight:
        bold;
}


.current-info {

    margin-top:
        8px;

    color:
        #dcfce7;
}


/* =========================================================
   DISPATCH BUTTON
========================================================= */

.dispatch-box {

    background:
        rgba(255,255,255,0.96);

    padding:
        20px;

    border-radius:
        12px;

    box-shadow:
        0 3px 10px rgba(0,0,0,0.12);

    margin-bottom:
        20px;
}


.dispatch-box h2 {

    color:
        #166534;

    margin-bottom:
        15px;
}


.dispatch-box button {

    width:
        100%;

    margin-bottom:
        10px;
}


/* =========================================================
   TABLE
========================================================= */

.queue-header {

    display:
        flex;

    justify-content:
        space-between;

    align-items:
        center;

    gap:
        10px;

    margin-bottom:
        15px;

    flex-wrap:
        wrap;
}


.queue-header input {

    max-width:
        280px;
}


.table-container {

    overflow-x:
        auto;
}


table {

    width:
        100%;

    border-collapse:
        collapse;

    min-width:
        1100px;
}


th,
td {

    padding:
        12px;

    border-bottom:
        1px solid #e2e8f0;

    text-align:
        left;

    font-size:
        13px;
}


th {

    background:
        #f0fdf4;

    color:
        #166534;
}


tr:hover {

    background:
        #f8fafc;
}


/* =========================================================
   STATUS BADGES
========================================================= */

.badge {

    display:
        inline-block;

    padding:
        5px 9px;

    border-radius:
        20px;

    font-size:
        11px;

    font-weight:
        bold;
}


.badge-waiting {

    background:
        #dbeafe;

    color:
        #1d4ed8;
}


.badge-called {

    background:
        #fef3c7;

    color:
        #92400e;
}


.badge-loading {

    background:
        #ffedd5;

    color:
        #c2410c;
}


.badge-completed {

    background:
        #dcfce7;

    color:
        #166534;
}


.badge-departed {

    background:
        #e2e8f0;

    color:
        #475569;
}


.badge-priority {

    background:
        #fee2e2;

    color:
        #b91c1c;
}


/* =========================================================
   ACTIONS
========================================================= */

.actions {

    display:
        flex;

    gap:
        5px;

    flex-wrap:
        wrap;
}


.actions button {

    font-size:
        11px;

    padding:
        7px 9px;
}


/* =========================================================
   NOTICE
========================================================= */

.notice {

    padding:
        13px;

    background:
        #eff6ff;

    border-left:
        4px solid #2563eb;

    color:
        #1e40af;

    border-radius:
        5px;

    margin-bottom:
        20px;
}


/* =========================================================
   REPORTS
========================================================= */

.report-card {

    background:
        rgba(255,255,255,0.96);

    border-radius:
        12px;

    padding:
        25px;

    box-shadow:
        0 3px 12px rgba(0,0,0,0.12);
}


/* =========================================================
   MODAL
========================================================= */

.modal {

    display:
        none;

    position:
        fixed;

    inset:
        0;

    background:
        rgba(15,23,42,0.65);

    z-index:
        100;

    align-items:
        center;

    justify-content:
        center;

    padding:
        20px;
}


.modal.show {

    display:
        flex;
}


.modal-content {

    background:
        white;

    border-radius:
        12px;

    padding:
        25px;

    width:
        100%;

    max-width:
        500px;

    max-height:
        90vh;

    overflow-y:
        auto;
}


/* =========================================================
   PRINT
========================================================= */

@media print {

    body * {

        visibility:
            hidden;
    }


    #printTicket,
    #printTicket * {

        visibility:
            visible;
    }


    #printTicket {

        position:
            absolute;

        left:
            0;

        top:
            0;

        width:
            100%;
    }

}


/* =========================================================
   PRINT TICKET
========================================================= */

#printTicket {

    display:
        none;
}


.print-ticket-inner {

    width:
        80mm;

    margin:
        auto;

    padding:
        10px;

    text-align:
        center;

    font-family:
        Arial,
        Helvetica,
        sans-serif;
}


.print-ticket-inner h2 {

    font-size:
        20px;

    margin-bottom:
        5px;
}


.print-ticket-queue {

    font-size:
        50px;

    font-weight:
        bold;

    margin:
        10px 0;
}


.print-line {

    border-top:
        1px dashed #000;

    margin:
        10px 0;
}


.print-detail {

    text-align:
        left;

    font-size:
        13px;

    line-height:
        1.7;
}


/* =========================================================
   MOBILE
========================================================= */

@media (max-width: 1000px) {

    .stats {

        grid-template-columns:
            repeat(3, 1fr);
    }


    .dashboard-grid {

        grid-template-columns:
            1fr;
    }

}


@media (max-width: 700px) {

    header {

        padding:
            12px 15px;
    }


    .brand-area {

        width:
            100%;

        gap:
            10px;
    }


    .logo-container {

        width:
            58px;

        height:
            58px;
    }


    .brand-text h1 {

        font-size:
            16px;
    }


    .brand-text h2 {

        font-size:
            11px;

        letter-spacing:
            0.4px;
    }


    .brand-text small {

        font-size:
            10px;
    }


    #clock {

        width:
            100%;

        text-align:
            left;

        font-size:
            12px;
    }


    .container {

        padding:
            10px;
    }


    .form-grid {

        grid-template-columns:
            1fr;
    }


    .form-group.full {

        grid-column:
            auto;
    }


    .stats {

        grid-template-columns:
            repeat(2, 1fr);
    }


    .navbar {

        overflow-x:
            auto;

        padding:
            8px 10px;
    }


    .nav-btn {

        white-space:
            nowrap;

        font-size:
            12px;

        padding:
            10px 12px;
    }


    .registration-title h2 {

        font-size:
            23px;
    }


    .queue-big {

        font-size:
            50px;
    }


    .current-queue {

        font-size:
            45px;
    }

}


/* =========================================================
   EXTRA SMALL MOBILE
========================================================= */

@media (max-width: 420px) {

    .brand-text h1 {

        font-size:
            14px;
    }


    .brand-text h2 {

        font-size:
            10px;
    }


    .brand-text small {

        display:
            none;
    }


    .logo-container {

        width:
            50px;

        height:
            50px;
    }


    .stats {

        grid-template-columns:
            1fr 1fr;

        gap:
            8px;
    }


    .stat-card {

        padding:
            13px;
    }


    .stat-number {

        font-size:
            24px;
    }

}

`;

    var styleEl = document.createElement("style");
    styleEl.textContent = PAGE_CSS;
    document.head.appendChild(styleEl);

    /* ---------- HTML (page layout) ---------- */
    var PAGE_HTML = `


<!-- =====================================================
     HEADER
===================================================== -->

<header>

    <div class="brand-area">

        <div class="logo-container">

            <img
                src="data:image/png;base64,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"
                alt="May Harvest Corporation Logo"
                class="mhc-logo"
            >

        </div>


        <div class="brand-text">

            <h1>
                MAY HARVEST CORPORATION
            </h1>

            <h2>
                PRODUCT QUEUING SYSTEM
            </h2>

            <small>
                Offline Product Queuing & Blast Freezing Management
            </small>

        </div>

    </div>


    <div id="clock"></div>

</header>


<!-- =====================================================
     NAVIGATION
===================================================== -->

<nav class="navbar">

    <button
        class="nav-btn active"
        onclick="showScreen('blastInventory', this); renderBlastInventory()"
    >
        \ud83d\udccb Blast Product Log & Inventory
    </button>

    <button
        class="nav-btn"
        onclick="showScreen('registration', this)"
    >
        \ud83d\udce6 Product Queuing for Blast
    </button>


    <button
        class="nav-btn"
        onclick="showScreen('dashboard', this)"
    >
        \u2744\ufe0f Blast Freezing Dashboard
    </button>


    <button
        class="nav-btn"
        onclick="showScreen('liveBoard', this)"
    >
        \ud83d\udcfa Live TV Queue Board
    </button>





    <button
        class="nav-btn"
        onclick="showScreen('reports', this)"
    >
        \ud83d\udcca Reports / Backup
    </button>

</nav>


<div class="container">

<!-- =====================================================
     BLAST PRODUCT LOG & INVENTORY
===================================================== -->
<section id="blastInventory" class="screen active">
  <div class="registration-container">
    <div class="registration-title">
      <h2>\ud83d\udccb Blast Product Log &amp; Inventory</h2>
      <p>Register products scheduled for blast freezing, record their volumes, and review the current inventory.</p>
    </div>
    <div class="card">
      <h3 style="margin-top:0">Register Product for Blast Freezing</h3>
      <form id="blastInventoryForm" class="form-grid">
        <div class="form-group"><label for="blastLogDate">Date *</label><input id="blastLogDate" type="date" required></div>
        <div class="form-group"><label for="blastLogProductionDate">Production Date *</label><input id="blastLogProductionDate" type="date" required></div>
        <div class="form-group"><label for="blastLogProduct">Product Name *</label><input id="blastLogProduct" type="text" placeholder="e.g., HJAC, CCM, MDS" required></div>
        <div class="form-group"><label for="blastLogVolume">Volume *</label><input id="blastLogVolume" type="number" min="0.01" step="0.01" placeholder="e.g., 5000" required></div>
        <div class="form-group"><label for="blastLogUnit">Unit *</label><select id="blastLogUnit" required><option value="kg">kg</option><option value="MT">MT</option><option value="boxes">boxes</option><option value="cases">cases</option></select></div>
        <div class="form-group"><label for="blastLogCategory">Product Category *</label><select id="blastLogCategory" required><option value="Marinated">Marinated</option><option value="Timplados">Timplados</option><option value="Branded">Branded</option><option value="Deboned">Deboned</option><option value="Whole Chicken">Whole Chicken</option><option value="Giblets">Giblets</option></select></div>
        <div class="form-group full"><button class="btn-primary big-button" type="submit">ADD TO BLAST INVENTORY</button></div>
      </form>
    </div>
    <div class="card" style="margin-top:20px">
      <div style="display:flex;justify-content:space-between;align-items:center;gap:12px;flex-wrap:wrap"><h3 style="margin:0">Registered Products &amp; Inventory</h3><div style="display:flex;gap:8px;flex-wrap:wrap"><button type="button" class="btn-secondary" onclick="exportBlastInventory()">Export Inventory CSV</button><button type="button" class="btn-secondary" style="background:#b91c1c;color:#fff;border-color:#b91c1c" onclick="resetBlastInventory()">Reset All Inventory</button></div></div>
      <p style="color:#64748b;margin:8px 0 14px">Example: HJAC \u2014 5,000 kg; CCM \u2014 3,200 kg; MDS \u2014 1,500 kg. Records you add will appear in this inventory table.</p>
      <div id="blastInventorySummary" style="display:flex;gap:12px;flex-wrap:wrap;margin-bottom:14px"></div>
      <div style="display:grid;grid-template-columns:minmax(0,1.7fr) minmax(260px,1fr);gap:14px;margin:0 0 18px;align-items:start">
        <div class="card" style="margin:0;background:#fff7ed;border:1px solid #fed7aa;box-shadow:none;min-width:0">
          <div style="display:flex;justify-content:space-between;align-items:center;gap:8px;flex-wrap:wrap;margin-bottom:12px"><h3 style="margin:0;color:#9a3412">\ud83d\udccb Inventory by Category</h3><span style="font-size:11px;color:#9a3412">Remaining stock</span></div>
          <div id="blastCategoryInventoryBoard" style="display:flex;flex-direction:column;gap:10px"></div>
          <p id="blastCategoryInventoryEmpty" style="display:none;color:#9a3412;text-align:center;padding:14px">No categorized stock registered yet.</p>
        </div>
      </div>
      <div style="overflow-x:auto"><table style="width:100%;border-collapse:collapse;min-width:900px"><thead><tr style="background:#eff6ff;text-align:left"><th style="padding:10px">Production Date</th><th style="padding:10px">Registered At</th><th style="padding:10px">Product</th><th style="padding:10px">Available Volume</th><th style="padding:10px">Category</th><th style="padding:10px">Action</th></tr></thead><tbody id="blastInventoryRows"></tbody></table></div>
      <p id="blastInventoryEmpty" style="display:none;color:#64748b;text-align:center;padding:18px">No products registered yet. Add a product above to build the inventory.</p>
    </div>
    <div class="card" style="margin-top:20px">
      <div style="display:flex;justify-content:space-between;align-items:center;gap:12px;flex-wrap:wrap"><h3 style="margin:0">\ud83d\udcdc Inventory Movement History</h3><button type="button" class="btn-secondary" onclick="exportBlastHistory()">Export History CSV</button></div>
      <p style="color:#64748b;margin:8px 0 14px">Tracks when stock was registered and when volume was deducted by Product Queuing for Blast.</p>
      <div style="overflow-x:auto"><table style="width:100%;border-collapse:collapse;min-width:900px"><thead><tr style="background:#eff6ff;text-align:left"><th style="padding:10px">Date &amp; Time</th><th style="padding:10px">Activity</th><th style="padding:10px">Product</th><th style="padding:10px">Volume Change</th><th style="padding:10px">Remaining Stock</th><th style="padding:10px">Shift / Queue</th><th style="padding:10px">Details</th></tr></thead><tbody id="blastInventoryHistoryRows"></tbody></table></div>
      <p id="blastInventoryHistoryEmpty" style="display:none;color:#64748b;text-align:center;padding:18px">No inventory activity recorded yet.</p>
    </div>
  </div>
</section>

<!-- =====================================================
     TRUCK REGISTRATION
===================================================== -->

<section
    id="registration"
    class="screen"
>

    <div class="registration-container">


        <div class="registration-title">

            <h2>
                Product Queuing for Blast
            </h2>

            <p>
                Enter the product details to generate a queue number.
            </p>

        </div>


        <div class="card">

            <form id="registrationForm"><div class="form-grid">
<div class="form-group"><label for="queueDate">Date *</label><input id="queueDate" type="date" required></div>
<div class="form-group"><label for="queueShift">Shift *</label><select id="queueShift" required><option value="">Select shift</option><option value="Day Shift">Day Shift</option><option value="Mid Shift">Mid Shift</option><option value="Night Shift">Night Shift</option></select></div>
<div class="form-group full"><label>Products to Load *</label><p style="margin:0 0 10px;color:#64748b;font-size:13px;">Add multiple products here. All products submitted together will share ONE queue number and move together in the Blast Freezing Dashboard.</p>
<div id="productEntries">
  <div class="product-entry" style="display:grid;grid-template-columns:2fr 1fr 1fr 1.2fr 1fr auto;gap:10px;align-items:end;margin-bottom:10px;padding:12px;border:1px solid #d6e2ef;border-radius:8px;">
    <div class="form-group"><label>Product *</label><input class="product-name" type="text" placeholder="Enter product name" required autocomplete="off"></div>
    <div class="form-group"><label>Volume *</label><input class="product-volume" type="text" placeholder="Example: 5,000 kg" required autocomplete="off"></div>
    <div class="form-group"><label>Product Temperature (\u00b0C) *</label><input class="product-temperature" type="number" step="0.1" placeholder="4.0" required></div>
    <div class="form-group"><label>Production Date *</label><input class="product-production-date" type="date" required></div>
    <button class="btn-secondary remove-product-btn" type="button" onclick="removeProductEntry(this)" style="height:40px;display:none;">Remove</button>
  </div>
</div>

</div>
<div class="form-group"><label for="recorderChecker">Blast Receiver/Recorder *</label><input id="recorderChecker" type="text" placeholder="Enter blast receiver/recorder name" required autocomplete="off"></div>
<div class="form-group"><label for="forLayer">Layer Status *</label><select id="forLayer" required><option value="No">Not for Layer</option><option value="Yes">For Layer</option></select></div>
<div class="form-group"><label for="priority">Prioritization *</label><select id="priority" required><option value="FSI">FSI</option><option value="CCM">CCM</option><option value="Branded">Branded</option><option value="Unbranded">Unbranded</option><option value="Aged">Aged</option><option value="Repro">Repro</option></select></div>
<div class="form-group full"><button class="btn-primary big-button" type="submit">ADD PRODUCT TO QUEUE</button></div>
</div></form>

        </div>


        <!-- REGISTRATION SUCCESS -->

        <div
            id="registrationSuccess"
            class="success-ticket"
        >

            <h2>
                \u2713 Product Added to Queue Successfully
            </h2>


            <div
                class="queue-big"
                id="newQueueNumber"
            >
                Q001
            </div>


            <div
                class="ticket-info"
                id="newTicketInfo"
            >
            </div>


            <button
                class="btn-primary"
                onclick="printLastTicket()"
            >
                \ud83d\udda8\ufe0f PRINT QUEUE TICKET
            </button>


            <button
                class="btn-secondary"
                onclick="newRegistration()"
            >
                REGISTER MORE PRODUCTS
            </button>

        </div>

    </div>

</section>


<!-- =====================================================
     DASHBOARD
===================================================== -->

<section
    id="dashboard"
    class="screen"
>


    <div class="notice">

        <strong>Offline Mode:</strong>

        All queue information is saved on this
        computer/browser. No internet connection is required.

    </div>


    <!-- STATISTICS -->

    <div class="stats">


        <div class="stat-card">

            <h3>
                WAITING
            </h3>

            <div
                class="stat-number blue"
                id="waitingCount"
            >
                0
            </div>

        </div>


        <div class="stat-card">

            <h3>
                IN BLAST QUEUE
            </h3>

            <div
                class="stat-number orange"
                id="calledCount"
            >
                0
            </div>

        </div>


        <div class="stat-card">

            <h3>
                LOADING
            </h3>

            <div
                class="stat-number orange"
                id="loadingCount"
            >
                0
            </div>

        </div>


        <div class="stat-card">

            <h3>
                COMPLETED
            </h3>

            <div
                class="stat-number green"
                id="completedCount"
            >
                0
            </div>

        </div>


        <div class="stat-card">

            <h3>
                TOTAL TODAY
            </h3>

            <div
                class="stat-number gray"
                id="totalCount"
            >
                0
            </div>

        </div>

    </div>


    <!-- FOR BLAST INVENTORY -->
    <div class="card" id="forBlastInventoryCard" style="margin-bottom:20px">
        <div class="queue-header">
            <h2>\ud83d\udce6 For Blast Inventory</h2>
            <span style="color:#64748b;font-size:13px">Products registered in Product Queuing for Blast. Enter the volume for each blast in the queue table below; one registration can be split into different blasts.</span>
        </div>
        <div id="forBlastSummary" style="display:flex;gap:10px;flex-wrap:wrap;margin-bottom:12px"></div>
        <div class="table-container">
            <table>
                <thead><tr><th>Queue</th><th>Product</th><th>Production Date</th><th>Registered Volume</th><th>Already in Blast</th><th>Remaining For Blast</th><th>Status</th></tr></thead>
                <tbody id="forBlastInventoryRows"></tbody>
            </table>
        </div>
    </div>

    <div class="dashboard-grid">


        <!-- LEFT SIDE -->

        <div>


            <!-- PRODUCT TEMPERATURE WHILE FREEZING (replaces the old "Waiting for blast" panel) -->

            <div class="card temp-panel">
                <h2>\ud83c\udf21\ufe0f Product Temperature While Freezing</h2>
                <div class="temp-field">
                    <label for="tempTruckSelect">Product in Blast</label>
                    <select id="tempTruckSelect" onchange="window.tempSelectedId = this.value; renderTempPanel()"></select>
                </div>
                <div class="temp-field">
                    <label for="tempValue">Product Temperature (&deg;C)</label>
                    <input id="tempValue" type="number" step="0.1" placeholder="e.g. -18.5">
                </div>
                <div class="temp-field">
                    <label for="tempBy">Temperature Taken By</label>
                    <input id="tempBy" type="text" placeholder="Name of the person who took the temperature">
                </div>
                <div class="temp-field">
                    <label for="tempDecision">Decision</label>
                    <select id="tempDecision">
                        <option value="">Select decision</option>
                        <option value="For Extend">For Extend</option>
                        <option value="For Harvest">For Harvest</option>
                    </select>
                </div>
                <button type="button" id="tempSaveBtn" class="btn-primary" style="width:100%" onclick="saveFreezingTemperature()">Save Temperature</button>
                <div style="margin-top:16px;font-weight:bold;font-size:14px">Recent readings (latest first)</div>
                <div id="tempHistory"></div>
            </div>

            <!-- SEARCH -->

            <div class="card">

                <h2>
                    Queue Search
                </h2>


                <input
                    id="searchInput"
                    type="text"
                    placeholder="Search blast number or product..."
                    oninput="renderQueue()"
                >

            </div>

        </div>


        <!-- RIGHT SIDE -->

        <div class="card">

            <div class="queue-header">

                <h2>
                    \ud83d\udccb Today's Product Queue
                </h2>


                <button
                    class="btn-secondary"
                    onclick="renderQueue()"
                >
                    Refresh
                </button>

            </div>


            <div class="table-container">

                <table>

                    <thead>

                        <tr>

                            <th>Queue</th>
                            <th>Date</th>
                            <th>Shift</th>
                            <th>Product</th>
                            <th>Volume</th>
                            <th>Product Temp (\u00b0C)</th>
                            <th>Production Date</th>
                            <th>Blast Receiver/Recorder</th>
                            <th>For Layer</th>
                            <th>Blast Freezer</th>
                            <th>Start Blast Freezing</th>
                            <th>End Blast Freezing</th>
                            <th>Priority</th>
                            <th>Status</th>
                            <th>Action</th>

                        </tr>

                    </thead>


                    <tbody id="queueTable">
                    </tbody>

                </table>

            </div>

        </div>

    </div>

</section>


<!-- =====================================================
     LIVE TV BLAST FREEZING QUEUE BOARD
===================================================== -->
<section id="liveBoard" class="screen">
  <style>
    .tv-board{background:#081321;color:#e7eef8;border-radius:18px;padding:22px;min-height:70vh}
    .tv-board-head{display:flex;justify-content:space-between;align-items:center;gap:16px;flex-wrap:wrap;margin-bottom:20px}
    .tv-board-head h2{margin:0;color:#dbeafe;letter-spacing:1px}
    .tv-live{color:#4ade80;font-weight:800;letter-spacing:2px}
    .tv-layout{display:grid;grid-template-columns:minmax(0,1fr);gap:18px}
    .tv-now{border:2px solid #22c55e;border-radius:18px;background:linear-gradient(150deg,#0d3a32,#101b2d);padding:26px 16px;text-align:center;min-height:340px;display:flex;flex-direction:column;justify-content:center}
    .tv-pill{display:inline-block;align-self:center;background:#22c55e;color:#052e1a;border-radius:30px;padding:10px 20px;font-weight:900;letter-spacing:2px}
    .tv-number{font-size:clamp(42px,5vw,76px);font-weight:900;margin:22px 0 8px;color:#fff}
    .tv-product{font-size:clamp(20px,2vw,30px);font-weight:900;color:#facc15;overflow-wrap:anywhere}
    .tv-destination{margin-top:22px;border:2px solid #38bdf8;border-radius:12px;padding:13px;font-size:20px;font-weight:900;color:#38bdf8}
    .tv-blasts{display:grid;grid-template-columns:repeat(2,minmax(0,1fr));gap:14px}
    .tv-blast{background:#0e1a2a;border:2px solid #29384c;border-radius:16px;padding:18px;min-height:190px}
    .tv-blast h3{margin:0 0 12px;color:#38bdf8;letter-spacing:1px;display:flex;justify-content:space-between;gap:10px}
    .tv-count{font-size:12px;background:#1e293b;color:#cbd5e1;border-radius:6px;padding:4px 8px;white-space:nowrap}
    .tv-item{border-top:1px solid #29384c;padding:10px 0;display:grid;grid-template-columns:auto 1fr;gap:10px;align-items:center}
    .tv-item strong{color:#f8fafc;font-size:18px}.tv-item small{display:block;color:#94a3b8;margin-top:3px}.tv-temp{font-size:20px;font-weight:900;color:#67e8f9;margin-top:6px}.tv-dec{display:inline-block;font-size:12px;font-weight:800;padding:3px 9px;border-radius:999px;margin-left:6px;vertical-align:middle}.tv-dec.harvest{background:#166534;color:#bbf7d0}.tv-dec.extend{background:#78350f;color:#fde68a}.temp-panel .temp-field{margin-bottom:12px}.temp-reading{display:grid;grid-template-columns:1fr auto;gap:2px 8px;align-items:center;padding:8px 10px;border-radius:8px;margin-top:8px;border-left:5px solid #f59e0b;background:#fffbeb}.temp-reading.harvest{border-left-color:#16a34a;background:#f0fdf4}.temp-reading small{grid-column:1;color:#64748b}.temp-reading button{grid-row:1 / span 2;grid-column:2;padding:6px 10px;font-size:12px}.temp-empty{color:#64748b;font-size:13px;padding:8px 0}.tv-status{display:inline-block;margin-top:6px;padding:4px 8px;border-radius:6px;font-size:11px;font-weight:900;letter-spacing:.5px}.tv-status.started{background:#14532d;color:#bbf7d0}.tv-status.waiting{background:#1e3a8a;color:#bfdbfe}.tv-status.done{background:#334155;color:#e2e8f0}.tv-empty{color:#64748b;text-align:center;padding:28px 4px}.tv-layer-section{margin-top:20px;background:#102238;border:2px solid #a78bfa;border-radius:16px;padding:18px}.tv-layer-section h3{color:#c4b5fd;margin:0 0 12px;font-size:22px}.tv-layer-grid{display:grid;grid-template-columns:repeat(3,minmax(0,1fr));gap:12px}.tv-layer-item{background:#1e293b;border:1px solid #64748b;border-radius:10px;padding:14px}.tv-layer-item strong{font-size:18px;color:#fff}.tv-layer-item small{display:block;color:#cbd5e1;margin-top:5px}.tv-harvest-section{margin-top:20px;background:#102238;border:2px solid #f59e0b;border-radius:16px;padding:18px}.tv-harvest-section h3{color:#fcd34d;margin:0 0 12px;font-size:22px}.tv-harvest-grid{display:grid;grid-template-columns:repeat(3,minmax(0,1fr));gap:12px}.tv-status.harvesting{background:#78350f;color:#fde68a}@media(max-width:760px){.tv-layer-grid,.tv-harvest-grid{grid-template-columns:1fr}}
    @media(max-width:760px){.tv-layout{grid-template-columns:1fr}.tv-blasts{grid-template-columns:1fr}.tv-board{padding:12px}}
  </style>
  <div class="tv-board">
    <div class="tv-board-head"><h2>\u2744\ufe0f LIVE TV BLAST FREEZING QUEUE BOARD</h2><div class="tv-live">\u25cf LIVE QUEUE</div></div>
    <div class="tv-layout">
      <div class="tv-blasts" id="tvBlastCards"></div>
    </div>
    <div class="tv-layer-section"><h3>\ud83d\udce6 PRODUCT IN LAYERING AREA</h3><div class="tv-layer-grid" id="tvLayerItems"></div></div>
    <div class="tv-harvest-section"><h3>\ud83c\udf3e PRODUCT FOR HARVEST</h3><div class="tv-harvest-grid" id="tvHarvestItems"></div></div>
    <p style="color:#94a3b8;margin:18px 0 0">This board displays product queue data saved in this browser. Keep the dashboard and TV board on the same computer/browser to share records.</p>
  </div>
</section>



<!-- Blast activity entry modal -->
<div id="blastActivityModal" style="display:none;position:fixed;inset:0;background:rgba(15,23,42,.72);z-index:9999;overflow:auto;padding:24px;">
 <div style="background:#fff;max-width:1050px;margin:20px auto;padding:22px;border-radius:14px;box-shadow:0 20px 60px #0004;">
  <div style="display:flex;justify-content:space-between;align-items:center;gap:12px"><h2 style="margin:0">Blast Freezing Activity Log</h2><button class="btn-danger" onclick="closeBlastActivity()">Close</button></div>
  <p id="blastActivityQueueLabel" style="color:#64748b"></p>
  <div class="table-container"><table style="width:100%;min-width:900px"><thead><tr><th>Activity</th><th>Start Date & Time</th><th>End Date & Time</th><th>Duration</th><th>Remarks</th><th>Manning</th><th>Recorder / Team Leader</th><th>Blast Supervisor</th></tr></thead><tbody id="blastActivityRows"></tbody></table></div>
  <div style="display:flex;justify-content:flex-end;gap:10px;margin-top:16px"><button class="btn-success" onclick="downloadBlastActivityReport()">\ud83d\udce5 Download Activity Report</button><button class="btn-primary" onclick="saveBlastActivity()">Save Activity Log</button></div>
  <p style="font-size:12px;color:#64748b;margin-bottom:0">Activity details are for the Blast Freezing Dashboard records and will not be displayed on the Live TV Queue Board. Adding a product to Product Queuing automatically starts Barcode Scanning (Fresh Input). Clicking Start Blast Freezing automatically fills the Blast Freezing activity start time.</p>
 </div>
</div>

<!-- =====================================================
     REPORTS
===================================================== -->

<section
    id="reports"
    class="screen"
>

    <div class="report-card">

        <h2>
            \ud83d\udcca Reports & Backup
        </h2>


        <p
            style="
                margin-bottom:20px;
                color:#64748b;
            "
        >
            Because this system works offline,
            it is recommended that you regularly
            export your product queuing data as a backup.
        </p>


        <button
            class="btn-success"
            onclick="exportCSV()"
        >
            \ud83d\udce5 EXPORT TODAY'S QUEUE TO CSV
        </button>


        <button
            class="btn-secondary"
            onclick="backupJSON()"
        >
            \ud83d\udcbe BACKUP SYSTEM DATA
        </button>

        <button
            class="btn-success"
            onclick="exportAllBlastActivityReport()"
        >
            \u23f1\ufe0f DOWNLOAD ACTIVITY DURATION REPORT (TODAY)
        </button>


        <hr
            style="
                margin:25px 0;
                border:0;
                border-top:1px solid #e2e8f0;
            "
        >


        <h2>
            Daily Queue
        </h2>


        <p
            id="reportSummary"
            style="
                line-height:1.8;
                margin-top:10px;
            "
        >
        </p>


        <hr
            style="
                margin:25px 0;
                border:0;
                border-top:1px solid #e2e8f0;
            "
        >


        <h2>
            Daily Reset
        </h2>


        <p
            style="
                color:#64748b;
                margin-bottom:15px;
            "
        >
            Use this at the beginning of a new
            operating day. Export your data first
            if you need a permanent record.
        </p>


        <button
            class="btn-danger"
            onclick="resetDay()"
        >
            \u26a0\ufe0f RESET TODAY'S QUEUE
        </button>

    </div>

</section>

</div>


<!-- =====================================================
     PRINT TICKET
===================================================== -->

<div id="printTicket">

    <div class="print-ticket-inner">

        <h2 id="printPlantName">
            MAY HARVEST CORPORATION
        </h2>


        <div
            style="
                font-size:12px;
                margin-bottom:5px;
            "
        >
            PRODUCT QUEUING SYSTEM
        </div>


        <div class="print-line"></div>


        <div>
            QUEUE NUMBER
        </div>


        <div
            class="print-ticket-queue"
            id="printQueue"
        >
            Q001
        </div>


        <div class="print-line"></div>


        <div
            class="print-detail"
            id="printDetails"
        >
        </div>


        <div class="print-line"></div>


        <div>
            Your product has been added to the queue.
        </div>


        <br>


        <div>
            Thank you.
        </div>

    </div>

</div>


`;

    if (!document.body) {
        document.documentElement.appendChild(document.createElement("body"));
    }
    document.body.insertAdjacentHTML("afterbegin", PAGE_HTML);

})();


/* =====================================================================
   APPLICATION CODE (original script, walang binago)
   ===================================================================== */
/*
=========================================================
 MAY HARVEST CORPORATION
 PRODUCT QUEUING SYSTEM
=========================================================
*/


/* ======================================================
   STORAGE
====================================================== */

const STORAGE_KEY =
    "mhcTruckQueueData";

const QUEUE_KEY =
    "mhcTruckQueueNumber";

const DATE_KEY =
    "mhcTruckQueueDate";

const PLANT_NAME_KEY =
    "mhcPlantName";


/* ======================================================
   DATA
====================================================== */

let trucks =
    JSON.parse(
        localStorage.getItem(
            STORAGE_KEY
        )
    ) || [];

// Migrate previously saved records that used the old "Departed" status.
let migratedHarvestStatus = false;
trucks.forEach(item => {
    if (item.status === "Departed") {
        item.status = "Harvested";
        migratedHarvestStatus = true;
    }
});
if (migratedHarvestStatus) {
    localStorage.setItem(STORAGE_KEY, JSON.stringify(trucks));
}


let queueNumber =
    parseInt(
        localStorage.getItem(
            QUEUE_KEY
        )
    ) || 1;


/* ======================================================
   TODAY
====================================================== */

function todayString() {

    const now =
        new Date();

    return (
        now.getFullYear() +
        "-" +
        String(
            now.getMonth() + 1
        ).padStart(2, "0") +
        "-" +
        String(
            now.getDate()
        ).padStart(2, "0")
    );

}


/* ======================================================
   CHECK NEW DAY
====================================================== */

function checkNewDay() {

    const savedDate =
        localStorage.getItem(
            DATE_KEY
        );

    const today =
        todayString();


    if (!savedDate) {

        localStorage.setItem(
            DATE_KEY,
            today
        );

        return;

    }


    if (savedDate !== today) {

        queueNumber = 1;

        localStorage.setItem(
            QUEUE_KEY,
            queueNumber
        );

        localStorage.setItem(
            DATE_KEY,
            today
        );

    }

}


checkNewDay();


/* ======================================================
   SAVE DATA
====================================================== */

function saveData() {

    localStorage.setItem(
        STORAGE_KEY,
        JSON.stringify(trucks)
    );

    localStorage.setItem(
        QUEUE_KEY,
        queueNumber
    );

}


/* ======================================================
   TODAY'S TRUCKS
====================================================== */

function todaysTrucks() {

    const today =
        todayString();

    return trucks.filter(
        truck =>
            truck.date === today && truck.status !== "Allocated"
    );

}


/* ======================================================
   GENERATE QUEUE NUMBER
====================================================== */

function generateQueueNumber() {

    const number =
        queueNumber;

    queueNumber++;


    localStorage.setItem(
        QUEUE_KEY,
        queueNumber
    );


    return (
        "Q" +
        String(number).padStart(
            3,
            "0"
        )
    );

}


/* ======================================================
   NAVIGATION
====================================================== */

function showScreen(
    screenId,
    button
) {

    document
        .querySelectorAll(".screen")
        .forEach(
            screen =>
                screen.classList.remove(
                    "active"
                )
        );


    document
        .getElementById(screenId)
        .classList.add(
            "active"
        );


    document
        .querySelectorAll(".nav-btn")
        .forEach(
            btn =>
                btn.classList.remove(
                    "active"
                )
        );


    if (button) {

        button.classList.add(
            "active"
        );

    }


    if (
        screenId === "dashboard"
    ) {

        renderQueue();

        updateStats();

        displayCurrentTruck();

    }


    if (screenId === "liveBoard") {
        renderLiveBlastBoard();
    }


    if (
        screenId === "reports"
    ) {

        updateReport();

    }

}


// Live TV: show only the volume still waiting once part of a registered lot has been put in other blasts.
function tvVolumeText(t) {
    const lines = t.status === "Waiting" ? getAllocLines(t) : null;
    if (lines && lines.some(l => l.allocated > 0)) {
        const left = lines.filter(l => l.remaining > 0).map(l => l.product + " " + fmtVol(l.remaining) + " " + l.unit).join("; ");
        const total = lines.map(l => fmtVol(l.amount) + " " + l.unit).join("; ");
        return (left || "0") + " remaining (registered: " + total + ")";
    }
    return t.volume || "-";
}
// How long a product has been inside the blast (since Blast Freezing Started), e.g. "2h 15m".
function tvFormatMs(ms) {
    const total = Math.max(0, Math.floor(ms / 1000));
    const h = Math.floor(total / 3600), m = Math.floor((total % 3600) / 60), sec = total % 60;
    return h + "h " + String(m).padStart(2, "0") + "m " + String(sec).padStart(2, "0") + "s";
}

function tvBlastDuration(startIso) {
    if (!startIso) return "";
    const ms = Date.now() - new Date(startIso).getTime();
    return Number.isFinite(ms) ? tvFormatMs(ms) : "";
}

// Total time a finished product stayed in the blast (Start Queue -> Complete), e.g. "5h 20m 12s".
function tvBlastTotalDuration(t) {
    let start = t.blastStartTimestamp ? new Date(t.blastStartTimestamp) : null;
    let end = t.blastEndTimestamp ? new Date(t.blastEndTimestamp) : null;
    if (!start || !end || isNaN(start) || isNaN(end)) {
        // Older records: use the Blast Freezing activity start / end instead.
        const acts = typeof getBlastActivities === "function" ? getBlastActivities(t) : [];
        const a = acts.find(x => x.name === "Blast Freezing") || acts[3];
        if (a && a.start && a.end) { start = new Date(a.start); end = new Date(a.end); }
    }
    if (!start || !end || isNaN(start) || isNaN(end) || end < start) return "";
    return tvFormatMs(end - start);
}

function renderLiveBlastBoard() {
    const cards = document.getElementById("tvBlastCards");
    if (!cards) return;
    const all = todaysTrucks();
    const assigned = all.filter(t => t.assignedBlast);
    cards.innerHTML = ["Blast 1","Blast 2","Blast 3","Blast 4"].map(blast => {
      const items = assigned.filter(t => t.assignedBlast === blast && !["Completed", "Harvested"].includes(t.status));
      const blastStarted = items.some(t => t.status === "Loading" || !!t.blastStartTimestamp);
      return `<div class="tv-blast"><h3>\u2744\ufe0f ${blast.toUpperCase()} <span class="tv-count">${blastStarted ? "BLAST FREEZING STARTED" : "WAITING / QUEUED"}</span></h3>` +
        (items.length ? items.map(t => {
          const itemStarted = t.status === "Loading" || !!t.blastStartTimestamp;
          const stamp = t.loadingTime || (t.blastStartTimestamp ? new Date(t.blastStartTimestamp).toLocaleTimeString() : "");
          const dur = itemStarted ? tvBlastDuration(t.blastStartTimestamp) : "";
          const tr = itemStarted ? latestTempReading(t) : null;
          const tempHTML = !itemStarted ? "" : (tr
            ? `<div class="tv-temp">\ud83c\udf21\ufe0f Freezing Temp: ${escapeHTML(String(tr.temp))}\u00b0C <span class="tv-dec ${tempDecisionClass(tr.decision)}">${escapeHTML(String(tr.decision).toUpperCase())}</span></div><small>Taken by ${escapeHTML(tr.by)} \u00b7 ${escapeHTML(new Date(tr.time).toLocaleTimeString())}</small>`
            : `<small>\ud83c\udf21\ufe0f Freezing temperature: not yet recorded</small>`);
          return `<div class="tv-item"><strong>${escapeHTML(t.queue || "---")}</strong><div>${escapeHTML(t.product || t.loadType || "Product")}<small>${escapeHTML(t.volume || "Volume N/A")} \u00b7 ${escapeHTML(String(t.productTemperature || "N/A").replace(/\s*\u00b0C\s*$/i, ""))}\u00b0C \u00b7 ${escapeHTML(t.priority || "No priority")}</small><span class="tv-status ${itemStarted ? "started" : "waiting"}">${itemStarted ? "BLAST FREEZING STARTED" : "WAITING IN QUEUE"}</span>${itemStarted ? `<small>Start time: ${escapeHTML(stamp || "-")}</small>${dur ? `<small class="tv-duration" data-start="${escapeHTML(t.blastStartTimestamp)}" style="color:#fde047;font-weight:800">\u23f1 Duration in blast: ${dur}</small>` : ""}` : ""}${tempHTML}</div></div>`;
        }).join("") : `<div class="tv-empty">No products in queue</div>`) + `</div>`;
    }).join("");
    const layerBox = document.getElementById("tvLayerItems");
    if (layerBox) {
      const layerItems = all.filter(t => t.isForLayer && !["Loading", "Completed", "Harvested", "Cancelled"].includes(t.status) && !t.blastStartTimestamp);
      layerBox.innerHTML = layerItems.length ? layerItems.map(t =>
        `<div class="tv-layer-item"><strong>${escapeHTML(t.queue || "---")} \u00b7 ${escapeHTML(t.product || t.loadType || "Product")}</strong><small>Volume: ${escapeHTML(tvVolumeText(t))}</small><small>Shift: ${escapeHTML(t.queueShift || "-")} \u00b7 Status: ${escapeHTML(t.status || "Waiting")}</small></div>`
      ).join("") : `<div class="tv-empty" style="grid-column:1/-1">No products currently waiting for layering</div>`;
    }
    const harvestBox = document.getElementById("tvHarvestItems");
    if (harvestBox) {
      // For Harvest = blast freezing completed (waiting for harvest) or harvesting in progress. Removed once Harvest End is recorded.
      const harvestEnded = t => { const acts = getBlastActivities(t); const h = acts.find(a => a.name === "Harvesting") || acts[4]; return !!(t.harvestEndTimestamp || (h && h.end)); };
      const harvestItems = all.filter(t => t.status === "Completed" || (t.status === "Harvested" && !harvestEnded(t)))
        .sort((x, y) => String(x.blastEndTimestamp || x.harvestStartTimestamp || "").localeCompare(String(y.blastEndTimestamp || y.harvestStartTimestamp || "")));
      harvestBox.innerHTML = harvestItems.length ? harvestItems.map(t => {
        const harvesting = t.status === "Harvested";
        const stamp = harvesting ? (t.departedTime || "") : (t.completedTime || "");
        const blastDur = tvBlastTotalDuration(t);
        return `<div class="tv-layer-item"><strong>${escapeHTML(t.queue || "---")} \u00b7 ${escapeHTML(t.product || t.loadType || "Product")}</strong><small>Volume: ${escapeHTML(t.volume || "-")} \u00b7 ${escapeHTML(t.assignedBlast || "-")}</small><span class="tv-status ${harvesting ? "harvesting" : "waiting"}">${harvesting ? "HARVESTING" : "FOR HARVEST"}</span>${blastDur ? `<small style="color:#fde047;font-weight:800">\u23f1 Total Blast Freezing Time: ${blastDur}</small>` : ""}${stamp ? `<small>${harvesting ? "Harvest started" : "Blast freezing completed"}: ${escapeHTML(stamp)}</small>` : ""}</div>`;
      }).join("") : `<div class="tv-empty" style="grid-column:1/-1">No products for harvest</div>`;
    }
}


setInterval(() => {
    if (document.getElementById("liveBoard")?.classList.contains("active")) renderLiveBlastBoard();
}, 3000);

// Make the "Duration in blast" seconds tick every second (the full board only redraws every 3 seconds).
setInterval(() => {
    document.querySelectorAll("#tvBlastCards .tv-duration").forEach(el => {
        const d = tvBlastDuration(el.dataset.start);
        if (d) el.textContent = "\u23f1 Duration in blast: " + d;
    });
}, 1000);


/* ======================================================
   REGISTRATION
====================================================== */

function addProductEntry() {
    const entries = document.getElementById("productEntries");
    const row = document.createElement("div");
    row.className = "product-entry";
    row.style.cssText = "display:grid;grid-template-columns:2fr 1fr 1fr 1.2fr 1fr auto;gap:10px;align-items:end;margin-bottom:10px;padding:12px;border:1px solid #d6e2ef;border-radius:8px;";
    row.innerHTML = `<div class="form-group"><label>Product *</label><input class="product-name" type="text" placeholder="Enter product name" required autocomplete="off"></div>
      <div class="form-group"><label>Volume *</label><input class="product-volume" type="text" placeholder="Example: 5,000 kg" required autocomplete="off"></div>
      <div class="form-group"><label>Product Temperature (\u00b0C) *</label><input class="product-temperature" type="number" step="0.1" placeholder="4.0" required></div>
      <div class="form-group"><label>Production Date *</label><input class="product-production-date" type="date" required></div>
      <button class="btn-secondary remove-product-btn" type="button" onclick="removeProductEntry(this)" style="height:40px;">Remove</button>`;
    entries.appendChild(row);
    updateProductRemoveButtons();
}
function removeProductEntry(button) {
    const entries = document.querySelectorAll("#productEntries .product-entry");
    if (entries.length <= 1) return;
    button.closest(".product-entry").remove();
    updateProductRemoveButtons();
}
function updateProductRemoveButtons() {
    const entries = document.querySelectorAll("#productEntries .product-entry");
    entries.forEach(row => { const btn = row.querySelector(".remove-product-btn"); if (btn) btn.style.display = entries.length > 1 ? "inline-block" : "none"; });
}


/* ---- Tolerant matching helpers for Blast Product Log & Inventory ---- */
// Product names: ignore case, spaces, hidden characters and punctuation ("HJAC" = "hjac " = "H-J-A-C").
function normProductName(v) {
    return String(v == null ? "" : v).normalize("NFKC").toLowerCase().replace(/[^a-z0-9]/g, "");
}
// Dates: accept YYYY-MM-DD, M/D/YYYY, MM/DD/YYYY, M-D-YYYY and ISO timestamps -> YYYY-MM-DD.
function normDateStr(v) {
    const t = String(v == null ? "" : v).trim();
    if (!t) return "";
    let m = t.match(/^(\d{4})[-\/.](\d{1,2})[-\/.](\d{1,2})/);
    if (m) return m[1] + "-" + m[2].padStart(2, "0") + "-" + m[3].padStart(2, "0");
    m = t.match(/^(\d{1,2})[-\/.](\d{1,2})[-\/.](\d{4})$/);
    if (m) return m[3] + "-" + m[1].padStart(2, "0") + "-" + m[2].padStart(2, "0");
    return t;
}
function stockProdDate(stock) { return normDateStr(stock.productionDate || stock.date || ""); }
function stockQty(stock) { const n = Number(String(stock.volume == null ? 0 : stock.volume).replace(/,/g, "")); return Number.isFinite(n) ? n : 0; }
function stockMatches(stock, product, productionDate) {
    return normProductName(stock.product) === normProductName(product) &&
           stockProdDate(stock) === normDateStr(productionDate);
}

// Production Date is entered directly by the user. Availability is checked
// against Blast Product Log & Inventory using the exact product + date.
function checkProductProductionDate(row, showAlert = false) {
    if (!row) return false;
    const productInput = row.querySelector(".product-name");
    const dateInput = row.querySelector(".product-production-date");
    if (!productInput || !dateInput) return false;

    const productName = productInput.value.trim();
    const productionDate = dateInput.value;
    let message = row.querySelector(".production-date-message");
    if (!message) {
        message = document.createElement("small");
        message.className = "production-date-message";
        message.style.cssText = "display:block;margin-top:5px;font-weight:700;";
        dateInput.insertAdjacentElement("afterend", message);
    }

    if (!productName || !productionDate) {
        message.textContent = "";
        message.style.color = "#64748b";
        return false;
    }

    const matchingStock = getBlastInventory().filter(stock =>
        stockMatches(stock, productName, productionDate) && stockQty(stock) > 0
    );
    const available = matchingStock.reduce((sum, stock) => sum + stockQty(stock), 0);

    if (!matchingStock.length || available <= 0) {
        // Help the user: show which Production Dates DO have stock for this product.
        const otherDates = [...new Set(getBlastInventory()
            .filter(st => normProductName(st.product) === normProductName(productName) && stockQty(st) > 0)
            .map(st => stockProdDate(st)))];
        message.textContent = "\u26a0 No available product for this Production Date." +
            (otherDates.length ? " Available Production Date(s) for " + productName + ": " + otherDates.join(", ") : "");
        message.style.color = "#dc2626";
        dateInput.setCustomValidity("No available product for this Production Date.");
        if (showAlert) alert("No available product for this Production Date. Please check Blast Product Log & Inventory.");
        return false;
    }

    message.textContent = "\u2713 Available in Blast Product Log & Inventory: " +
        available.toLocaleString() + " " + (matchingStock[0].unit || "");
    message.style.color = "#15803d";
    dateInput.setCustomValidity("");
    return true;
}

document.getElementById("productEntries").addEventListener("input", function(event) {
    if (event.target.matches(".product-name, .product-production-date")) {
        checkProductProductionDate(event.target.closest(".product-entry"));
    }
});
document.getElementById("productEntries").addEventListener("change", function(event) {
    if (event.target.matches(".product-name, .product-production-date")) {
        checkProductProductionDate(event.target.closest(".product-entry"));
    }
});

document.getElementById("forLayer").addEventListener("change", function() {
    if (this.value !== "Yes") return;
    const rows = [...document.querySelectorAll("#productEntries .product-entry")];
    const allAvailable = rows.every(row => checkProductProductionDate(row));
    if (!allAvailable) {
        alert("Layering is not allowed. Enter a Production Date with available product in Blast Product Log & Inventory for every product first.");
        this.value = "No";
    }
});

document.getElementById("registrationForm").addEventListener("submit", function(event) {
    event.preventDefault();
    const queueDate = document.getElementById("queueDate").value;
    const queueShift = document.getElementById("queueShift").value;
    const dateShift = queueDate + " / " + queueShift;
    const recorderChecker = document.getElementById("recorderChecker").value.trim();
    const priority = document.getElementById("priority").value;
    const products = Array.from(document.querySelectorAll("#productEntries .product-entry")).map(row => ({
        product: row.querySelector(".product-name").value.trim(),
        volume: row.querySelector(".product-volume").value.trim(),
        productTemperature: row.querySelector(".product-temperature").value,
        productionDate: row.querySelector(".product-production-date").value
    }));

    // Each registered product becomes "For Blast" inventory: keep its numeric volume so it can be split across blasts.
    products.forEach(p => { const pv = parseQueueVolume(p.volume); if (pv) { p.amount = pv.amount; p.unit = pv.unit; } p.allocated = 0; });
    const inventoryForDates = getBlastInventory();
    for (const item of products) {
        const hasAvailableDate = inventoryForDates.some(stock =>
            stockMatches(stock, item.product, item.productionDate) && stockQty(stock) > 0
        );
        if (!item.productionDate || !hasAvailableDate) {
            alert("No available product for this Production Date. Product: " + item.product +
                "\\nProduction Date: " + (item.productionDate || "Not selected") +
                "\\nPlease check Blast Product Log & Inventory.");
            return;
        }
    }

    const now = new Date();
    // Barcode Scanning is NOT recorded automatically anymore. It is recorded together with Layering Start.
    const localQueueStart = new Date(now.getTime() - now.getTimezoneOffset() * 60000).toISOString().slice(0,16);
    const initialBlastActivities = [
        "Barcode Scanning (Fresh Input)", "Layering", "Transfer to Blast Freezing Room",
        "Blast Freezing", "Harvesting", "Barcoding Weighing (Frozen Output)"
    ].map((name, index) => ({
        name, start: "", end: "", remarks: "", manning: "", recorder: "", blastSupervisor: ""
    }));
    // Repeat product registrations are allowed; each submission becomes its own queue record.
    // One submission = one queue record, containing multiple product details.
    const record = {
        id: Date.now() + Math.floor(Math.random()*100000),
        queue: generateQueueNumber(), date: todayString(), queueDate, queueShift, dateShift,
        products,
        product: products.map(p => p.product).join(", "),
        volume: products.map(p => p.product + ": " + p.volume).join("; "),
        productTemperature: products.map(p => p.product + ": " + p.productTemperature + "\u00b0C").join("; "),
        productionDate: products.map(p => p.product + ": " + p.productionDate).join("; "),
        recorderChecker, priority, isForLayer: document.getElementById("forLayer").value === "Yes",
        arrival: now.toLocaleTimeString(), arrivalTimestamp: now.toISOString(), status: "Waiting", queueStarted: true, queueStartedAt: now.toISOString(),
        blastActivities: initialBlastActivities, splitCount: 0,
        truckNumber: products.map(p => p.product).join(", "), driverName: recorderChecker,
        company: dateShift, contact: "", loadType: products.map(p => p.product).join(", "),
        destination: products.map(p => p.productionDate).join(", "), reference: products.map(p => p.volume).join(", ")
    };
    // Validate and deduct queued product volumes from Blast Product Inventory.
    // Queue volume may be entered as "3,000", "3,000 kg", or "3,000.0 kg".
    const inventoryBeforeQueue = getBlastInventory();
    const deductions = [];
    for (const item of products) {
        const parsed = parseQueueVolume(item.volume);
        if (!parsed || parsed.amount <= 0) {
            alert(`Please enter a valid volume for ${item.product}. Example: 3,000 kg.`);
            return;
        }
        const matchingRows = inventoryBeforeQueue.filter(r =>
            stockMatches(r, item.product, item.productionDate) &&
            (!parsed.unit || String(r.unit || "").trim().toLowerCase() === parsed.unit.toLowerCase()) &&
            stockQty(r) > 0
        );
        const available = matchingRows.reduce((sum, r) => sum + stockQty(r), 0);
        if (!matchingRows.length) {
            alert(`No matching inventory found for ${item.product}${parsed.unit ? " (" + parsed.unit + ")" : ""}. Please register it in Blast Product Log & Inventory first.`);
            return;
        }
        if (available < parsed.amount) {
            alert(`Insufficient inventory for ${item.product}. Available: ${available.toLocaleString()} ${matchingRows[0].unit}; Requested: ${parsed.amount.toLocaleString()} ${matchingRows[0].unit}.`);
            return;
        }
        deductions.push({ product: item.product, productionDate: item.productionDate, amount: parsed.amount, unit: matchingRows[0].unit });
    }

    trucks.push(record);
    saveData();
    applyBlastInventoryDeductions(deductions);
    renderBlastInventory();
    document.getElementById("newQueueNumber").textContent = record.queue;
    document.getElementById("newTicketInfo").innerHTML = "<strong>Queue:</strong> " + escapeHTML(record.queue) +
        "<br><strong>Products in this queue:</strong><br>" + products.map(p => escapeHTML(p.product) +
        " \u2014 " + escapeHTML(p.volume) + " \u2014 " + escapeHTML(p.productTemperature) + " \u00b0C \u2014 Production: " + escapeHTML(p.productionDate)).join("<br>") +
        "<br><strong>Prioritization:</strong> " + escapeHTML(priority) + "<br><strong>Date:</strong> " + escapeHTML(queueDate) + "<br><strong>Shift:</strong> " + escapeHTML(queueShift) +
        "<br><strong>Blast Receiver/Recorder:</strong> " + escapeHTML(recorderChecker);
    document.getElementById("registrationSuccess").classList.add("show");
    window.lastRegisteredTruck = record;
    document.getElementById("registrationForm").reset();
    document.getElementById("productEntries").innerHTML = `<div class="product-entry" style="display:grid;grid-template-columns:2fr 1fr 1fr 1.2fr 1fr auto;gap:10px;align-items:end;margin-bottom:10px;padding:12px;border:1px solid #d6e2ef;border-radius:8px;"><div class="form-group"><label>Product *</label><input class="product-name" type="text" placeholder="Enter product name" required autocomplete="off"></div><div class="form-group"><label>Volume *</label><input class="product-volume" type="text" placeholder="Example: 5,000 kg" required autocomplete="off"></div><div class="form-group"><label>Product Temperature (\u00b0C) *</label><input class="product-temperature" type="number" step="0.1" placeholder="4.0" required></div><div class="form-group"><label>Production Date *</label><input class="product-production-date" type="date" required></div><button class="btn-secondary remove-product-btn" type="button" onclick="removeProductEntry(this)" style="height:40px;display:none;">Remove</button></div>`;
    updateStats(); renderQueue();
});

/* ======================================================
   NEW REGISTRATION
====================================================== */

function newRegistration() {

    document
        .getElementById(
            "registrationSuccess"
        )
        .classList.remove(
            "show"
        );


    document
        .getElementById(
            "truckNumber"
        )
        .focus();

}


/* ======================================================
   LOADING DOCK CAPACITY (8 DOORS)
====================================================== */
const LOADING_DOCK_CAPACITY = 8;

/* ======================================================
   CALL NEXT TRUCK
====================================================== */

function callNextTruck() {
    const blast = document.getElementById("blastSelect").value;
    const waiting = todaysTrucks().filter(truck => truck.status === "Waiting");

    if (waiting.length === 0) {
        alert("There are no waiting products to add to a blast queue.");
        return;
    }

    waiting.sort((a, b) => {
        const priorityOrder = { FSI: 0, CCM: 1, Branded: 2, Unbranded: 3, Aged: 4, Repro: 5 };
        const ap = priorityOrder[a.priority] ?? 99;
        const bp = priorityOrder[b.priority] ?? 99;
        if (ap !== bp) return ap - bp;
        return new Date(a.arrivalTimestamp || a.date) - new Date(b.arrivalTimestamp || b.date);
    });

    assignToBlast(waiting[0], blast);
}

function addToBlastQueue(id, selectId) {
    const product = trucks.find(t => t.id === id);
    const select = document.getElementById(selectId);
    if (!product || !select) return;
    assignToBlast(product, select.value);
}

function assignToBlast(product, blast) {
    if (product.status !== "Waiting") {
        alert("This product is already assigned to a blast queue or is being processed.");
        return;
    }

    product.assignedBlast = blast;
    product.status = "Called"; // Existing workflow status represents queued/assigned products.
    product.blastQueueTime = new Date().toISOString();
    saveData();
    renderQueue();
    updateStats();
    displayCurrentTruck();
    alert("PRODUCT ADDED TO BLAST QUEUE\n\nQueue: " + product.queue + "\nProduct: " + (product.product || product.loadType || "-") + "\nAssigned to: " + blast);
}


/* ======================================================
   START BLAST FREEZING
====================================================== */

function startLoading(id) {
    const truck = trucks.find(t => t.id === id);
    if (!truck) return;

    if (truck.status !== "Called") {
        alert("Please assign this product to a Blast Freezer queue first.");
        return;
    }
    if (!truck.assignedBlast) {
        alert("Please assign this product to a Blast Freezer first.");
        return;
    }

    // Start only the selected queue record. Other products assigned to the same freezer remain queued.
    const blastStart = new Date();
    truck.status = "Loading";
    truck.loadingTime = blastStart.toLocaleTimeString();
    truck.blastStartTimestamp = blastStart.toISOString();
    // Automatically record the exact dashboard click time in the Blast Freezing activity row.
    const activityRows = getBlastActivities(truck);
    const blastActivity = activityRows.find(a => a.name === "Blast Freezing") || activityRows[3];
    if (blastActivity && !blastActivity.start) blastActivity.start = new Date(blastStart.getTime() - blastStart.getTimezoneOffset() * 60000).toISOString().slice(0,16);
    truck.completedTime = "";
    truck.blastEndTimestamp = "";

    saveData();
    renderQueue();
    updateStats();
    displayCurrentTruck();
    if (typeof renderLiveBlastBoard === "function") renderLiveBlastBoard();
}


/* ======================================================
   COMPLETE LOADING
====================================================== */

function completeTruck(id) {

    const truck =
        trucks.find(
            t => t.id === id
        );


    if (!truck) return;


    truck.status =
        "Completed";


    const blastEnd = new Date();
    truck.completedTime = blastEnd.toLocaleTimeString();
    truck.blastEndTimestamp = blastEnd.toISOString();

    // Automatically record the completion click as the Blast Freezing activity end time.
    const activityRows = getBlastActivities(truck);
    const blastActivity = activityRows.find(a => a.name === "Blast Freezing") || activityRows[3];
    const localBlastEnd = new Date(blastEnd.getTime() - blastEnd.getTimezoneOffset() * 60000).toISOString().slice(0, 16);
    if (blastActivity) {
        // Fill the start too if this record somehow did not have one yet.
        if (!blastActivity.start) {
            const startSource = truck.blastStartTimestamp ? new Date(truck.blastStartTimestamp) : blastEnd;
            blastActivity.start = new Date(startSource.getTime() - startSource.getTimezoneOffset() * 60000).toISOString().slice(0, 16);
        }
        blastActivity.end = localBlastEnd;
    }

    saveData();
    renderQueue();
    updateStats();
    displayCurrentTruck();
    if (typeof renderLiveBlastBoard === "function") renderLiveBlastBoard();

}


/* ======================================================
   MARK FOR HARVEST
====================================================== */

function departTruck(id) {
    const truck = trucks.find(t => t.id === id);
    if (!truck) return;

    // Clicking "For Harvest" automatically starts the Harvesting activity in real time.
    const harvestStart = new Date();
    const localHarvestStart = new Date(harvestStart.getTime() - harvestStart.getTimezoneOffset() * 60000)
        .toISOString().slice(0, 16);
    const activityRows = getBlastActivities(truck);
    const harvestingActivity = activityRows.find(a => a.name === "Harvesting") || activityRows[4];
    if (harvestingActivity && !harvestingActivity.start) {
        harvestingActivity.start = localHarvestStart;
    }

    truck.status = "Harvested";
    truck.departedTime = harvestStart.toLocaleTimeString();
    truck.harvestStartTimestamp = truck.harvestStartTimestamp || harvestStart.toISOString();

    saveData();
    renderQueue();
    updateStats();
    displayCurrentTruck();
    if (typeof renderLiveBlastBoard === "function") renderLiveBlastBoard();
}


/* ======================================================
   CANCEL
====================================================== */

function cancelTruck(id) {

    const truck =
        trucks.find(
            t => t.id === id
        );


    if (!truck) return;


    if (
        !confirm(
            "Cancel queue " +
            truck.queue +
            "?"
        )
    ) {

        return;

    }


    truck.status =
        "Cancelled";


    truck.cancelledTime =
        new Date()
            .toLocaleTimeString();


    saveData();


    renderQueue();

    updateStats();

    displayCurrentTruck();

}


/* ======================================================
   STATUS BADGE
====================================================== */

function statusBadge(status) {

    let cls =
        "badge-waiting";


    if (
        status === "Called"
    ) {

        cls =
            "badge-called";

    }


    if (
        status === "Loading"
    ) {

        cls =
            "badge-loading";

    }


    if (
        status === "Completed"
    ) {

        cls =
            "badge-completed";

    }


    if (
        status === "Harvested"
    ) {

        cls =
            "badge-departed";

    }


    return `
        <span class="badge ${cls}">
            ${escapeHTML(status === "Called" ? "In Blast Queue" : status)}
        </span>
    `;

}


/* ======================================================
   PRIORITY BADGE
====================================================== */

function priorityBadge(priority) {

    if (
        priority ===
        "Priority"
    ) {

        return `
            <span class="badge badge-priority">
                PRIORITY
            </span>
        `;

    }


    return escapeHTML(priority || "-");

}


/* ======================================================
   PRODUCT QUEUE START CONTROL
====================================================== */
function startProductQueue(id) {
    const item = trucks.find(t => t.id === id);
    if (!item) return;
    if (item.status !== "Waiting" || item.assignedBlast) {
        alert("This queue has already been assigned or processing has started.");
        return;
    }
    item.queueStarted = true;
    item.queueStartedAt = new Date().toISOString();
    saveData();
    renderQueue();
    updateStats();
    alert("QUEUE STARTED\n\n" + (item.queue || "Queue") + " is now available to be assigned in the Blast Freezing Dashboard. Blast freezing has not started yet.");
}

function renderProductQueueControl() {
    const tbody = document.getElementById("productQueueControlRows");
    if (!tbody) return;
    const list = todaysTrucks().slice().sort((a,b) => new Date(a.arrivalTimestamp || a.date || 0) - new Date(b.arrivalTimestamp || b.date || 0));
    if (!list.length) {
        tbody.innerHTML = '<tr><td colspan="6" style="padding:16px;text-align:center;color:#64748b">No product queues registered today.</td></tr>';
        return;
    }
    tbody.innerHTML = list.map(item => {
        const canStartQueue = item.status === "Waiting" && !item.assignedBlast && item.queueStarted !== true;
        let status = item.status === "Loading" || item.blastStartTimestamp ? "Blast Freezing Ongoing" : item.assignedBlast ? "Assigned to " + item.assignedBlast : item.queueStarted ? "Queue Started \u2014 Ready for Assignment" : "Waiting for Start Queue";
        let action = canStartQueue ? `<button class="btn-primary" onclick="startProductQueue(${item.id})">Start Queue</button>` : `<span style="font-weight:700;color:${item.queueStarted || item.assignedBlast ? '#15803d' : '#64748b'}">${item.status === "Loading" || item.blastStartTimestamp ? "ONGOING" : item.assignedBlast ? "ASSIGNED" : item.queueStarted ? "STARTED" : "\u2014"}</span>`;
        return `<tr><td style="padding:10px"><strong>${escapeHTML(item.queue || "\u2014")}</strong></td><td style="padding:10px">${escapeHTML(item.product || item.loadType || "\u2014")}</td><td style="padding:10px">${escapeHTML(item.queueShift || "\u2014")}</td><td style="padding:10px">${escapeHTML(item.assignedBlast || "Not assigned")}</td><td style="padding:10px">${escapeHTML(status)}</td><td style="padding:10px">${action}</td></tr>`;
    }).join("");
}

/* ======================================================
   RENDER QUEUE
====================================================== */

function renderQueue() {

    const table =
        document
            .getElementById(
                "queueTable"
            );


    const searchElement =
        document
            .getElementById(
                "searchInput"
            );


    const search =
        searchElement
            ? searchElement.value
                .toLowerCase()
                .trim()
            : "";


    let list =
        todaysTrucks();


    if (search) {

        list =
            list.filter(
                truck =>
                    String(truck.assignedBlast || "")
                        .toLowerCase()
                        .includes(search)
                    ||
                    String(truck.product || truck.loadType || "")
                        .toLowerCase()
                        .includes(search)
            );

    }


    const statusOrder = {

        "Called": 1,

        "Loading": 2,

        "Waiting": 3,

        "Completed": 4,

        "Harvested": 5,

        "Cancelled": 6

    };


    list.sort(
        (a, b) => {

            if (
                statusOrder[a.status] !==
                statusOrder[b.status]
            ) {

                return (
                    statusOrder[a.status] -
                    statusOrder[b.status]
                );

            }


            return (
                new Date(
                    a.arrivalTimestamp
                ) -

                new Date(
                    b.arrivalTimestamp
                )
            );

        }
    );


    renderProductQueueControl();
    renderForBlastInventory();

    if (
        list.length === 0
    ) {

        table.innerHTML = `

            <tr>

                <td
                    colspan="10"
                    style="
                        text-align:center;
                        padding:40px;
                        color:#64748b;
                    "
                >

                    No products registered today.

                </td>

            </tr>

        `;

        return;

    }


    table.innerHTML =
        list.map(
            truck => {

                let actions = "";

                // Keep activity controls at the top of the Action column so
                // Layering Start is visible without horizontal scrolling.
                if (truck.status !== "Cancelled") {
                    actions += renderBlastActivityControls(truck);
                }

                if (
                    truck.status ===
                    "Waiting"
                ) {
                    actions += renderAllocPanel(truck);
                    actions += `
                        <button class="btn-danger" onclick="cancelTruck(${truck.id})">Cancel</button>
                    `;
                }


                if (
                    truck.status ===
                    "Called"
                ) {

                    actions += `

                        <button
                            class="btn-warning"
                            onclick="startLoading(${truck.id})"
                        >
                            Start Blast Freezing
                        </button>

                    `;

                }


                if (
                    truck.status ===
                    "Loading"
                ) {

                    actions += `

                        <button
                            class="btn-success"
                            onclick="completeTruck(${truck.id})"
                        >
                            Complete
                        </button>

                    `;

                }


                if (
                    truck.status ===
                    "Completed"
                ) {

                    actions += `

                        <button
                            class="btn-secondary"
                            onclick="departTruck(${truck.id})"
                        >
                            Harvest Start
                        </button>

                    `;

                }


                if (truck.status !== "Cancelled") {
                    actions += `<button class="btn-secondary" onclick="openBlastActivity(${truck.id})">Activity Log</button>`;
                }

                actions += `

                    <button
                        class="btn-dark"
                        onclick="printTicket(${truck.id})"
                    >
                        Print
                    </button>

                `;


                return `

                    <tr>

                        <td>
                            <strong>
                                ${escapeHTML(
                                    truck.queue
                                )}
                            </strong>
                        </td>


                        <td><strong>${escapeHTML(truck.queueDate || (truck.dateShift || truck.company || "-").split(" / ")[0])}</strong></td>
                        <td><strong>${escapeHTML(truck.queueShift || ((truck.dateShift || truck.company || "").split(" / ")[1]) || "-")}</strong></td>
                        <td>${escapeHTML(truck.product || truck.loadType || "-")}</td>
                        <td>${volumeCellHTML(truck)}</td>
                        <td>${truck.productTemperature !== undefined && truck.productTemperature !== "" ? escapeHTML(truck.productTemperature) + " \u00b0C" : "-"}</td>
                        <td>${escapeHTML(truck.productionDate || truck.destination || "-")}</td>
                        <td>${escapeHTML(truck.recorderChecker || truck.driverName || "-")}</td>
                        <td>${truck.isForLayer ? "YES" : "\u2014"}</td>
                        <td>${escapeHTML(truck.assignedBlast || "-")}</td>

                        <td>${escapeHTML(truck.loadingTime || "-")}</td>
                        <td>${escapeHTML(truck.completedTime || "-")}</td>

                        <td>
                            ${priorityBadge(
                                truck.priority
                            )}
                        </td>


                        <td>
                            ${statusBadge(
                                truck.status
                            )}
                        </td>


                        <td>

                            <div class="actions">

                                ${actions}

                            </div>

                        </td>

                    </tr>

                `;

            }
        ).join("");

}


/* ======================================================
   CALL SPECIFIC TRUCK
====================================================== */

/* ======================================================
   FOR BLAST INVENTORY + VOLUME PER BLAST (SPLITTING)
====================================================== */
function r2(n) { return Math.round((Number(n) + Number.EPSILON) * 100) / 100; }
function fmtVol(n) { return Number(n).toLocaleString(undefined, { maximumFractionDigits: 2 }); }
// Returns per-product volume lines of a registered queue, or null for old records that cannot be split.
function getAllocLines(parent) {
    if (!parent || !Array.isArray(parent.products) || !parent.products.length) return null;
    const lines = [];
    for (let i = 0; i < parent.products.length; i++) {
        const p = parent.products[i];
        let amount = Number(p.amount), unit = p.unit;
        if (!(amount > 0)) {
            const pv = parseQueueVolume(p.volume);
            if (!pv || !(pv.amount > 0)) return null;
            amount = pv.amount; unit = pv.unit;
        }
        const allocated = Number(p.allocated) || 0;
        lines.push({ index: i, product: p.product, productionDate: p.productionDate, productTemperature: p.productTemperature, amount, unit: unit || "", allocated, remaining: r2(amount - allocated) });
    }
    return lines;
}
function blastOptionsHTML() {
    return ["Blast 1", "Blast 2", "Blast 3", "Blast 4"].map(b => `<option value="${b}">${b}</option>`).join("");
}
function renderAllocPanel(truck) {
    const lines = getAllocLines(truck);
    if (!lines) {
        return `<select id="blastSelect_${truck.id}" aria-label="Select blast for ${escapeHTML(truck.queue)}" style="max-width:115px; padding:7px;">${blastOptionsHTML()}</select> <button class="btn-primary" onclick="addToBlastQueue(${truck.id}, 'blastSelect_${truck.id}')">Add to Queue</button>`;
    }
    const open = lines.filter(l => l.remaining > 0);
    if (!open.length) return "";
    return `<div style="width:100%;min-width:240px;padding:8px;border:1px dashed #94a3b8;border-radius:8px;background:#f8fafc;margin:4px 0">` +
        `<div style="font-size:12px;font-weight:800;color:#334155;margin-bottom:6px">VOLUME TO PUT IN BLAST</div>` +
        open.map(l => `<div style="margin-bottom:6px"><label style="display:block;font-size:12px;font-weight:700">${escapeHTML(l.product)} <span style="color:#64748b;font-weight:600">\u00b7 remaining ${fmtVol(l.remaining)} ${escapeHTML(l.unit)}</span></label><div style="display:flex;gap:4px;align-items:center"><input type="number" id="alloc_${truck.id}_${l.index}" min="0" max="${l.remaining}" step="any" value="${l.remaining}" style="width:110px;padding:6px"> <span>${escapeHTML(l.unit)}</span></div></div>`).join("") +
        `<div style="display:flex;gap:6px;flex-wrap:wrap;align-items:center"><select id="blastSelect_${truck.id}" aria-label="Select blast for ${escapeHTML(truck.queue)}" style="max-width:115px;padding:7px">${blastOptionsHTML()}</select><button class="btn-primary" onclick="allocateToBlast(${truck.id})">Add to Blast</button></div></div>`;
}
function volumeCellHTML(truck) {
    const base = escapeHTML(truck.volume || truck.reference || "-");
    const lines = truck.status === "Waiting" ? getAllocLines(truck) : null;
    if (lines && lines.some(l => l.allocated > 0)) {
        return base + `<br><small style="color:#b45309;font-weight:700">Remaining: ${lines.map(l => escapeHTML(l.product) + " " + fmtVol(l.remaining) + " " + escapeHTML(l.unit)).join("; ")}</small>`;
    }
    return base;
}
function allocateToBlast(id) {
    const parent = trucks.find(t => t.id === id);
    if (!parent) return;
    if (parent.status !== "Waiting") { alert("This queue is no longer waiting for blast allocation."); return; }
    const sel = document.getElementById("blastSelect_" + id);
    const blast = sel ? sel.value : "Blast 1";
    const lines = getAllocLines(parent);
    if (!lines) { assignToBlast(parent, blast); return; }
    const picks = [];
    for (const ln of lines) {
        if (ln.remaining <= 0) continue;
        const inp = document.getElementById("alloc_" + id + "_" + ln.index);
        const raw = inp ? String(inp.value).replace(/,/g, "").trim() : "";
        const v = raw === "" ? 0 : Number(raw);
        if (!Number.isFinite(v) || v < 0) { alert("Please enter a valid volume for " + ln.product + "."); return; }
        if (v > ln.remaining + 0.0001) { alert("The volume for " + ln.product + " is more than the remaining " + fmtVol(ln.remaining) + " " + ln.unit + "."); return; }
        if (v > 0) picks.push({ ln, v: r2(v) });
    }
    if (!picks.length) { alert("Enter the volume to put in " + blast + " first."); return; }
    const now = new Date();
    parent.splitCount = (parent.splitCount || 0) + 1;
    const coversAll = parent.splitCount === 1 && lines.filter(l => l.remaining > 0).length === picks.length && picks.every(x => Math.abs(x.ln.remaining - x.v) < 0.01);
    const label = coversAll ? parent.queue : parent.queue + "-" + parent.splitCount;
    const childProducts = picks.map(({ ln, v }) => ({ product: ln.product, volume: fmtVol(v) + (ln.unit ? " " + ln.unit : ""), productTemperature: ln.productTemperature, productionDate: ln.productionDate, amount: v, unit: ln.unit, allocated: v }));
    const names = childProducts.map(p => p.product);
    const child = {
        id: Date.now() + Math.floor(Math.random() * 100000),
        queue: label, parentQueue: parent.queue, parentId: parent.id,
        date: parent.date, queueDate: parent.queueDate, queueShift: parent.queueShift, dateShift: parent.dateShift,
        products: childProducts,
        product: names.join(", "),
        volume: childProducts.map(p => p.product + ": " + p.volume).join("; "),
        productTemperature: childProducts.map(p => p.product + ": " + p.productTemperature + "\u00b0C").join("; "),
        productionDate: childProducts.map(p => p.product + ": " + p.productionDate).join("; "),
        recorderChecker: parent.recorderChecker, priority: parent.priority, isForLayer: parent.isForLayer,
        arrival: parent.arrival, arrivalTimestamp: parent.arrivalTimestamp,
        status: "Called", queueStarted: true, queueStartedAt: parent.queueStartedAt || now.toISOString(),
        assignedBlast: blast, blastQueueTime: now.toISOString(),
        // The new blast batch keeps whatever activities were already recorded for the registered lot (e.g. Layering).
        blastActivities: JSON.parse(JSON.stringify(getBlastActivities(parent))),
        truckNumber: names.join(", "), driverName: parent.recorderChecker, company: parent.dateShift, contact: "",
        loadType: names.join(", "), destination: childProducts.map(p => p.productionDate).join(", "), reference: childProducts.map(p => p.volume).join(", ")
    };
    picks.forEach(({ ln, v }) => { parent.products[ln.index].allocated = r2((Number(parent.products[ln.index].allocated) || 0) + v); });
    const after = getAllocLines(parent);
    const fullyAllocated = after && after.every(l => l.remaining <= 0.009);
    if (fullyAllocated) { parent.status = "Allocated"; parent.allocatedAt = now.toISOString(); }
    trucks.push(child);
    saveData(); renderQueue(); updateStats(); displayCurrentTruck();
    if (typeof renderLiveBlastBoard === "function") renderLiveBlastBoard();
    alert("ADDED TO " + blast.toUpperCase() + "\n\nQueue: " + child.queue + "\nVolume: " + child.volume +
        (fullyAllocated ? "\n\nAll registered volume of " + parent.queue + " is now in blast queues." : "\n\nThe rest of " + parent.queue + " is still in For Blast Inventory."));
}
function renderForBlastInventory() {
    const body = document.getElementById("forBlastInventoryRows");
    if (!body) return;
    const today = todayString();
    const parents = trucks.filter(t => t.date === today && !t.parentId && t.status !== "Cancelled" && Array.isArray(t.products));
    const rows = [], totals = {};
    parents.forEach(t => {
        const lines = getAllocLines(t);
        if (!lines) return;
        lines.forEach(l => {
            const state = l.remaining <= 0 ? "All in blast" : (l.allocated > 0 ? "Partly in blast" : "Waiting for blast");
            const color = l.remaining <= 0 ? "#15803d" : (l.allocated > 0 ? "#b45309" : "#1d4ed8");
            if (l.remaining > 0) totals[l.unit] = (totals[l.unit] || 0) + l.remaining;
            rows.push(`<tr><td><strong>${escapeHTML(t.queue)}</strong></td><td>${escapeHTML(l.product)}</td><td>${escapeHTML(l.productionDate || "-")}</td><td>${fmtVol(l.amount)} ${escapeHTML(l.unit)}</td><td>${fmtVol(l.allocated)} ${escapeHTML(l.unit)}</td><td><strong>${fmtVol(Math.max(0, l.remaining))} ${escapeHTML(l.unit)}</strong></td><td style="font-weight:700;color:${color}">${state}</td></tr>`);
        });
    });
    body.innerHTML = rows.length ? rows.join("") : `<tr><td colspan="7" style="text-align:center;padding:20px;color:#64748b">No products registered for blast today.</td></tr>`;
    const sum = document.getElementById("forBlastSummary");
    if (sum) {
        const entries = Object.entries(totals);
        sum.innerHTML = entries.length ? entries.map(([unit, total]) => `<div style="background:#eff6ff;padding:10px 14px;border-radius:8px"><strong>${fmtVol(total)} ${escapeHTML(unit)}</strong><br><span style="font-size:12px">Remaining For Blast</span></div>`).join("") : `<div style="background:#f0fdf4;padding:10px 14px;border-radius:8px"><span style="font-size:13px;font-weight:700">No volume waiting for blast</span></div>`;
    }
}

function callSpecificTruck(id) {

    const truck =
        trucks.find(
            t => t.id === id
        );


    if (!truck) return;


    // Allow up to 8 trucks (one per loading door) to be called or loading.
    const activeTrucks =
        todaysTrucks().filter(
            t => t.status === "Called" || t.status === "Loading"
        );

    if (truck.status !== "Waiting") {
        alert("This truck is not in Waiting status.");
        return;
    }

    if (activeTrucks.length >= LOADING_DOCK_CAPACITY) {
        alert(
            "All 8 loading doors are occupied.\n\n" +
            "Complete or depart a truck before calling another."
        );
        return;
    }


    truck.status =
        "Called";


    saveData();


    renderQueue();

    updateStats();

    displayCurrentTruck();


    alert(
        "Calling " +
        truck.queue +
        " - " +
        truck.truckNumber
    );

}


/* ======================================================
   CURRENT TRUCK
====================================================== */

/* ======================================================
   PRODUCT TEMPERATURE WHILE FREEZING
   (replaces the old "Waiting for blast" panel; the Live TV shows the latest reading)
====================================================== */

function freezingProducts() {
    return todaysTrucks().filter(t => t.assignedBlast
        && !["Completed", "Harvested", "Cancelled"].includes(t.status)
        && (t.status === "Loading" || !!t.blastStartTimestamp));
}

function latestTempReading(t) {
    const list = Array.isArray(t && t.tempReadings) ? t.tempReadings : [];
    return list.length ? list[list.length - 1] : null;
}

function tempDecisionClass(d) { return d === "For Harvest" ? "harvest" : "extend"; }

// Called from many places (Start Queue, Complete, etc.), so the old name is kept.
function displayCurrentTruck() { renderTempPanel(); }

function renderTempPanel() {
    const sel = document.getElementById("tempTruckSelect");
    if (!sel) return;
    const list = freezingProducts();
    const sig = list.map(t => t.id + ":" + t.assignedBlast + ":" + t.queue + ":" + (t.product || t.loadType || "")).join("|");
    if (sel.dataset.sig !== sig) {
        const keep = String(window.tempSelectedId || sel.value || "");
        sel.innerHTML = list.length
            ? list.map(t => `<option value="${t.id}">${escapeHTML(t.assignedBlast)} \u00b7 ${escapeHTML(t.queue || "---")} \u00b7 ${escapeHTML(t.product || t.loadType || "Product")}</option>`).join("")
            : `<option value="">No product in blast freezing</option>`;
        if (list.some(t => String(t.id) === keep)) sel.value = keep;
        sel.dataset.sig = sig;
    }
    window.tempSelectedId = sel.value;
    const has = list.length > 0;
    ["tempValue", "tempBy", "tempDecision", "tempSaveBtn"].forEach(id => { const el = document.getElementById(id); if (el) el.disabled = !has; });
    const t = list.find(x => String(x.id) === String(sel.value));
    const readings = t && Array.isArray(t.tempReadings) ? t.tempReadings : [];
    const box = document.getElementById("tempHistory");
    if (!box) return;
    box.innerHTML = !t
        ? `<div class="temp-empty">No product is in blast freezing yet. Click Start Queue on a product first.</div>`
        : readings.length
            ? readings.slice(-5).reverse().map(r => `<div class="temp-reading ${tempDecisionClass(r.decision)}"><div><strong>${escapeHTML(String(r.temp))}&deg;C</strong> &middot; ${escapeHTML(r.decision)}</div><small>${escapeHTML(new Date(r.time).toLocaleString())} &middot; by ${escapeHTML(r.by)}</small><button type="button" class="btn-secondary" onclick="deleteFreezingTemperature(${t.id}, ${readings.indexOf(r)})">Delete</button></div>`).join("")
            : `<div class="temp-empty">No temperature recorded yet for this product.</div>`;
}

function saveFreezingTemperature() {
    const sel = document.getElementById("tempTruckSelect");
    const t = trucks.find(x => String(x.id) === String(sel.value));
    if (!t) { alert("Select the product in blast freezing first."); return; }
    const raw = document.getElementById("tempValue").value.trim();
    const temp = Number(raw);
    const by = document.getElementById("tempBy").value.trim();
    const decision = document.getElementById("tempDecision").value;
    if (raw === "" || !Number.isFinite(temp)) { alert("Enter the product temperature (\u00b0C)."); return; }
    if (!by) { alert("Enter the name of the person who took the temperature."); return; }
    if (!decision) { alert("Select the decision: For Extend or For Harvest."); return; }
    if (!Array.isArray(t.tempReadings)) t.tempReadings = [];
    t.tempReadings.push({ time: new Date().toISOString(), temp: Math.round(temp * 100) / 100, by: by, decision: decision });
    saveData();
    document.getElementById("tempValue").value = "";
    document.getElementById("tempDecision").value = "";
    renderTempPanel();
    renderLiveBlastBoard();
}

function deleteFreezingTemperature(id, index) {
    const t = trucks.find(x => String(x.id) === String(id));
    if (!t || !Array.isArray(t.tempReadings) || !t.tempReadings[index]) return;
    if (!confirm("Delete this temperature reading?")) return;
    t.tempReadings.splice(index, 1);
    saveData();
    renderTempPanel();
    renderLiveBlastBoard();
}


/* ======================================================
   STATISTICS
====================================================== */

function updateStats() {

    const list =
        todaysTrucks();


    const waiting =
        list.filter(
            t =>
                t.status ===
                "Waiting"
        ).length;


    const called =
        list.filter(
            t =>
                t.status ===
                "Called"
        ).length;


    const loading =
        list.filter(
            t =>
                t.status ===
                "Loading"
        ).length;


    const completed =
        list.filter(
            t =>
                t.status ===
                "Completed"

                ||

                t.status ===
                "Harvested"
        ).length;


    document
        .getElementById(
            "waitingCount"
        )
        .textContent =
            waiting;


    document
        .getElementById(
            "calledCount"
        )
        .textContent =
            called;


    document
        .getElementById(
            "loadingCount"
        )
        .textContent =
            loading;


    document
        .getElementById(
            "completedCount"
        )
        .textContent =
            completed;


    document
        .getElementById(
            "totalCount"
        )
        .textContent =
            list.length;

}


/* ======================================================
   PRINT LAST TICKET
====================================================== */

function printLastTicket() {

    if (
        !window.lastRegisteredTruck
    ) {

        alert(
            "No recent registration found."
        );

        return;

    }


    printTicketData(
        window.lastRegisteredTruck
    );

}


/* ======================================================
   PRINT CURRENT TICKET
====================================================== */

function printCurrentTicket() {

    const current =
        todaysTrucks()
            .find(
                truck =>

                    truck.status ===
                        "Called"

                    ||

                    truck.status ===
                        "Loading"
            );


    if (!current) {

        alert(
            "There is no truck currently being processed."
        );

        return;

    }


    printTicketData(
        current
    );

}


/* ======================================================
   PRINT TICKET BY ID
====================================================== */

function printTicket(id) {

    const truck =
        trucks.find(
            t => t.id === id
        );


    if (!truck) return;


    printTicketData(
        truck
    );

}


/* ======================================================
   PREPARE PRINT
====================================================== */

function printTicketData(truck) {

    document
        .getElementById(
            "printPlantName"
        )
        .textContent =
            "MAY HARVEST CORPORATION";


    document
        .getElementById(
            "printQueue"
        )
        .textContent =
            truck.queue;


    document
        .getElementById(
            "printDetails"
        )
        .innerHTML =
            "<strong>Date:</strong> " + escapeHTML(truck.queueDate || (truck.dateShift || truck.company || "-").split(" / ")[0]) +
            "<br><strong>Shift:</strong> " + escapeHTML(truck.queueShift || ((truck.dateShift || truck.company || "").split(" / ")[1]) || "-") +
            "<br><strong>Product:</strong> " + escapeHTML(truck.product || truck.loadType || "-") +
            "<br><strong>Volume:</strong> " + escapeHTML(truck.volume || truck.reference || "-") +
            "<br><strong>Product Temperature:</strong> " + (truck.productTemperature !== undefined && truck.productTemperature !== "" ? escapeHTML(truck.productTemperature) + " \u00b0C" : "-") +
            "<br><strong>Production Date:</strong> " + escapeHTML(truck.productionDate || truck.destination || "-") +
            "<br><strong>Blast Receiver/Recorder:</strong> " + escapeHTML(truck.recorderChecker || truck.driverName || "-") +
            "<br><strong>Prioritization:</strong> " + escapeHTML(truck.priority || "-") +
            "<br><strong>Blast Freezer:</strong> " + escapeHTML(truck.assignedBlast || "Not assigned") +
            "<br><strong>Registered:</strong> " + escapeHTML(truck.arrival || "-");


    


    document
        .getElementById(
            "printTicket"
        )
        .style.display =
            "block";


    window.print();


    setTimeout(
        function() {

            document
                .getElementById(
                    "printTicket"
                )
                .style.display =
                    "none";

        },
        1000
    );

}


/* ======================================================
   CSV EXPORT
====================================================== */

function exportCSV() {

    const list =
        todaysTrucks();


    if (
        list.length === 0
    ) {

        alert(
            "There is no product queuing data to export."
        );

        return;

    }


    let csv =

        "Queue,Registration Date,Queue Date,Shift,Product,Volume,Product Temperature (\u00b0C),Production Date,Blast Receiver/Recorder,Blast Freezer,Prioritization,Arrival,Status,Loading Time,Completed Time,Harvested Time\n";


    list.forEach(
        truck => {

            csv +=

                csvValue(
                    truck.queue
                ) + "," +

                csvValue(
                    truck.date
                ) + "," +

                csvValue(truck.queueDate || (truck.dateShift || "").split(" / ")[0]) + "," +
                csvValue(truck.queueShift || ((truck.dateShift || "").split(" / ")[1]) || "") + "," +
                csvValue(truck.product) + "," +
                csvValue(truck.volume) + "," +
                csvValue(truck.productTemperature) + "," +
                csvValue(truck.productionDate) + "," +
                csvValue(truck.recorderChecker) + "," +
                csvValue(truck.assignedBlast || "") + "," +

                csvValue(
                    truck.priority
                ) + "," +

                csvValue(
                    truck.arrival
                ) + "," +

                csvValue(
                    truck.status
                ) + "," +

                csvValue(
                    truck.loadingTime
                ) + "," +

                csvValue(
                    truck.completedTime
                ) + "," +

                csvValue(
                    truck.departedTime
                ) +

                "\n";

        }
    );


    downloadFile(
        csv,
        "MHC_product_queuing_" +
        todayString() +
        ".csv",
        "text/csv"
    );

}


/* ======================================================
   CSV VALUE
====================================================== */

function csvValue(value) {

    if (
        value === undefined ||
        value === null
    ) {

        return "\"\"";

    }


    return (
        "\"" +
        String(value)
            .replace(
                /"/g,
                "\"\""
            ) +
        "\""
    );

}


/* ======================================================
   BACKUP JSON
====================================================== */

function backupJSON() {

    const backup = {

        company:
            "May Harvest Corporation",

        system:
            "Product Queuing System",

        backupDate:
            new Date()
                .toISOString(),

        queueNumber:
            queueNumber,

        trucks:
            trucks

    };


    const data =
        JSON.stringify(
            backup,
            null,
            2
        );


    downloadFile(
        data,
        "MHC_product_queuing_backup_" +
        todayString() +
        ".json",
        "application/json"
    );

}


/* ======================================================
   DOWNLOAD FILE
====================================================== */

function downloadFile(
    data,
    filename,
    type
) {

    const blob =
        new Blob(
            [data],
            {
                type:
                    type
            }
        );


    const url =
        URL.createObjectURL(
            blob
        );


    const link =
        document.createElement(
            "a"
        );


    link.href =
        url;


    link.download =
        filename;


    document
        .body
        .appendChild(
            link
        );


    link.click();


    document
        .body
        .removeChild(
            link
        );


    URL.revokeObjectURL(
        url
    );

}


/* ======================================================
   REPORT
====================================================== */

function updateReport() {

    const list =
        todaysTrucks();


    const waiting =
        list.filter(
            t =>
                t.status ===
                "Waiting"
        ).length;


    const processing =
        list.filter(
            t =>
                t.status ===
                "Loading"

                ||

                t.status ===
                "Called"
        ).length;


    const completed =
        list.filter(
            t =>
                t.status ===
                "Completed"

                ||

                t.status ===
                "Harvested"
        ).length;


    const cancelled =
        list.filter(
            t =>
                t.status ===
                "Cancelled"
        ).length;


    document
        .getElementById(
            "reportSummary"
        )
        .innerHTML =

            "<strong>Company:</strong> " +
            "May Harvest Corporation" +

            "<br>" +

            "<strong>System:</strong> " +
            "Product Queuing System" +

            "<br>" +

            "<strong>Date:</strong> " +
            todayString() +

            "<br>" +

            "<strong>Total Registered:</strong> " +
            list.length +

            "<br>" +

            "<strong>Waiting:</strong> " +
            waiting +

            "<br>" +

            "<strong>Currently Processing:</strong> " +
            processing +

            "<br>" +

            "<strong>Completed / Harvested:</strong> " +
            completed +

            "<br>" +

            "<strong>Cancelled:</strong> " +
            cancelled;

}


/* ======================================================
   RESET DAY
====================================================== */

function resetDay() {

    const confirmed =
        confirm(

            "WARNING\n\n" +

            "This will remove ALL saved product queuing data " +
            "from this browser.\n\n" +

            "Make sure you have exported or backed up " +
            "your data first.\n\n" +

            "Continue?"

        );


    if (!confirmed) {

        return;

    }


    const confirmedAgain =
        confirm(
            "Are you absolutely sure?"
        );


    if (!confirmedAgain) {

        return;

    }


    trucks = [];

    queueNumber = 1;


    localStorage.setItem(
        STORAGE_KEY,
        JSON.stringify([])
    );


    localStorage.setItem(
        QUEUE_KEY,
        1
    );


    localStorage.setItem(
        DATE_KEY,
        todayString()
    );


    renderQueue();

    updateStats();

    displayCurrentTruck();

    updateReport();


    alert(
        "May Harvest Corporation queue has been reset."
    );

}


/* ======================================================
   CLOCK
====================================================== */

function updateClock() {

    const now =
        new Date();


    document
        .getElementById(
            "clock"
        )
        .textContent =
            now.toLocaleString();

}


setInterval(
    updateClock,
    1000
);


/* ======================================================
   ESCAPE HTML
====================================================== */

function escapeHTML(value) {

    if (
        value === undefined ||
        value === null
    ) {

        return "";

    }


    return String(value)

        .replace(
            /&/g,
            "&amp;"
        )

        .replace(
            /</g,
            "&lt;"
        )

        .replace(
            />/g,
            "&gt;"
        )

        .replace(
            /"/g,
            "&quot;"
        )

        .replace(
            /'/g,
            "&#039;"
        );

}


/* ======================================================
   ACTIVITY MONITORING
====================================================== */
const ACTIVITY_MONITORING_KEY = "mhc_activity_monitoring_v1";
const ACTIVITY_NAMES = [
  "Barcode Scanning (Fresh Input)",
  "Layering",
  "Transfer to Blast Freezing Room",
  "Blast Freezing",
  "Harvesting",
  "Barcoding / Weighing (Frozen Output)"
];
function getActivityRows() {
  let rows = [];
  try { rows = JSON.parse(localStorage.getItem(ACTIVITY_MONITORING_KEY) || "[]"); } catch(e) {}
  return ACTIVITY_NAMES.map((name, i) => Object.assign({
    activity:name, start:"", end:"", shift:"", manning:"", recorder:"", teamLeader:"", supervisor:"", remarks:""
  }, rows[i] || {}, {activity:name}));
}
function saveActivityRows(rows) { localStorage.setItem(ACTIVITY_MONITORING_KEY, JSON.stringify(rows)); }
function activityEscape(v) { return String(v == null ? "" : v).replace(/&/g,"&amp;").replace(/</g,"&lt;").replace(/>/g,"&gt;").replace(/"/g,"&quot;").replace(/'/g,"&#39;"); }
function activityDuration(start, end) {
  if (!start || !end) return "\u2014";
  const ms = new Date(end).getTime() - new Date(start).getTime();
  if (!Number.isFinite(ms) || ms < 0) return "\u2014";
  const mins = Math.floor(ms / 60000);
  return Math.floor(mins/60) + "h " + (mins%60) + "m";
}
function renderActivityMonitoring() {
  const body = document.getElementById("activityMonitoringBody");
  if (!body) return;
  const rows = getActivityRows();
  body.innerHTML = rows.map((r,i) => {
    const started = !!r.start, ended = !!r.end;
    const status = ended ? "Ended" : started ? "In progress" : "Not started";
    const input = (key, value, placeholder="") => `<input aria-label="${activityEscape(r.activity)} ${key}" value="${activityEscape(value)}" placeholder="${placeholder}" oninput="updateActivityField(${i},'${key}',this.value)" style="width:100%;min-width:75px;box-sizing:border-box;padding:7px;border:1px solid #bfd0e2;border-radius:4px;">`;
    return `<tr>
      <td style="padding:10px;border:1px solid #d1deeb;font-weight:600;min-width:180px;">${activityEscape(r.activity)}</td>
      <td style="padding:8px;border:1px solid #d1deeb;min-width:180px;"><input type="datetime-local" value="${activityEscape(r.start)}" ${started?"disabled":""} onchange="updateActivityField(${i},'start',this.value)" style="padding:7px;width:100%;box-sizing:border-box;"></td>
      <td style="padding:8px;border:1px solid #d1deeb;min-width:180px;"><input type="datetime-local" value="${activityEscape(r.end)}" ${ended?"disabled":""} onchange="updateActivityField(${i},'end',this.value)" style="padding:7px;width:100%;box-sizing:border-box;"></td>
      <td style="padding:8px;border:1px solid #d1deeb;white-space:nowrap;">${activityDuration(r.start,r.end)}</td>
      <td style="padding:8px;border:1px solid #d1deeb;">\u2014</td>
      <td style="padding:8px;border:1px solid #d1deeb;min-width:85px;"><select onchange="updateActivityField(${i},'shift',this.value)" style="padding:7px;width:100%;"><option value="">Select</option>${["Day","Night","A","B","C","D"].map(v=>`<option ${r.shift===v?"selected":""}>${v}</option>`).join("")}</select></td>
      <td style="padding:8px;border:1px solid #d1deeb;min-width:70px;">${input("manning",r.manning)}</td>
      <td style="padding:8px;border:1px solid #d1deeb;min-width:130px;">${input("recorder",r.recorder)}</td>
      <td style="padding:8px;border:1px solid #d1deeb;min-width:130px;">${input("teamLeader",r.teamLeader)}</td>
      <td style="padding:8px;border:1px solid #d1deeb;min-width:130px;">${input("supervisor",r.supervisor)}</td>
      <td style="padding:8px;border:1px solid #d1deeb;min-width:130px;">${input("remarks",r.remarks)}</td>
      <td style="padding:8px;border:1px solid #d1deeb;min-width:100px;"><div style="margin-bottom:5px;">${status}</div><button type="button" onclick="stampActivity(${i},'start')" ${started?"disabled":""} style="display:block;margin-bottom:4px;padding:4px 8px;background:#316b96;color:#fff;border:0;border-radius:4px;">Start</button><button type="button" onclick="stampActivity(${i},'end')" ${ended?"disabled":""} style="display:block;padding:4px 8px;background:#526579;color:#fff;border:0;border-radius:4px;" ${started?"":"disabled"}>End</button></td>
    </tr>`;
  }).join("");
}
function updateActivityField(index, key, value) {
  const rows=getActivityRows();
  if ((key === "start" && rows[index].start) || (key === "end" && rows[index].end)) return;
  rows[index][key]=value; saveActivityRows(rows);
}
function stampActivity(index, key) {
  const rows=getActivityRows();
  if (key === "start" && rows[index].start) return;
  if (key === "end" && (!rows[index].start || rows[index].end)) return;
  const now = new Date();
  const local = new Date(now.getTime() - now.getTimezoneOffset()*60000).toISOString().slice(0,16);
  rows[index][key]=local; saveActivityRows(rows); renderActivityMonitoring();
}
function exportActivityMonitoring() {
  const rows=getActivityRows();
  const headers=["Activity","Start (date/time)","End (date/time)","Duration","Shift","Manning","Recorder","Team Leader","Supervisor","Remarks","Status"];
  const csv=[headers,...rows.map(r=>[r.activity,r.start,r.end,activityDuration(r.start,r.end),r.shift,r.manning,r.recorder,r.teamLeader,r.supervisor,r.remarks,r.end?"Ended":r.start?"In progress":"Not started"])].map(row=>row.map(v=>'"'+String(v==null?"":v).replace(/"/g,'""')+'"').join(",")).join("\r\n");
  const blob=new Blob(["\ufeff"+csv],{type:"text/csv;charset=utf-8;"}); const url=URL.createObjectURL(blob); const a=document.createElement("a"); a.href=url; a.download="MHC_Activity_Monitoring.csv"; a.click(); URL.revokeObjectURL(url);
}
function resetActivityMonitoring() {
  if (!confirm("Reset all Activity Monitoring entries? This cannot be undone.")) return;
  localStorage.removeItem(ACTIVITY_MONITORING_KEY); renderActivityMonitoring();
}

/* ======================================================
   INITIALIZE
====================================================== */

localStorage.setItem(
    PLANT_NAME_KEY,
    "MAY HARVEST CORPORATION"
);


updateClock();

renderQueue();

updateStats();

displayCurrentTruck();

updateReport();


/* Blast product log and inventory */
// One-time clean test reset: clear only Blast Product Log & Inventory data and its movement history.
// This runs once for this reset build, so later inventory entries will remain on refresh.
const BLAST_TEST_RESET_FLAG = "mhcBlastInventoryCleanTestReset_20261029_v2";
if (!localStorage.getItem(BLAST_TEST_RESET_FLAG)) {
  localStorage.removeItem("mhcBlastProductInventory_v1");
  localStorage.removeItem("mhcBlastInventoryHistory_v1");
  localStorage.setItem(BLAST_TEST_RESET_FLAG, "done");
}

const BLAST_INVENTORY_KEY = "mhcBlastProductInventory_v1";
// FIFO (First In, First Out): the oldest Production Date is always first. Same date -> registered earlier comes first.
// Entries without a valid Production Date go last.
function fifoDateKey(v) { const k = normDateStr(v); return /^\d{4}-\d{2}-\d{2}$/.test(k) ? k : "9999-99-99"; }
function fifoSortInventory(rows) {
  return rows.map((r, i) => ({ r, i })).sort((a, b) => {
    const da = fifoDateKey(a.r.productionDate || a.r.date || ""), db = fifoDateKey(b.r.productionDate || b.r.date || "");
    if (da !== db) return da < db ? -1 : 1;
    const ca = String(a.r.createdAt || ""), cb = String(b.r.createdAt || "");
    if (ca !== cb) return ca < cb ? -1 : 1;
    return a.i - b.i;
  }).map(x => x.r);
}
function getBlastInventory() { try { return fifoSortInventory(JSON.parse(localStorage.getItem(BLAST_INVENTORY_KEY) || "[]")); } catch (e) { return []; } }
function saveBlastInventory(rows) { localStorage.setItem(BLAST_INVENTORY_KEY, JSON.stringify(rows)); }
const BLAST_HISTORY_KEY = "mhcBlastInventoryHistory_v1";
function getBlastHistory() { try { return JSON.parse(localStorage.getItem(BLAST_HISTORY_KEY) || "[]"); } catch (e) { return []; } }
function addBlastHistory(entry) { const history = getBlastHistory(); history.unshift({ timestamp: new Date().toISOString(), ...entry }); localStorage.setItem(BLAST_HISTORY_KEY, JSON.stringify(history)); }
function formatBlastTimestamp(value) { if (!value) return "\u2014"; const d = new Date(value); return Number.isNaN(d.getTime()) ? value : d.toLocaleString(); }
function renderBlastHistory() {
  const history = getBlastHistory();
  const tbody = document.getElementById("blastInventoryHistoryRows");
  const empty = document.getElementById("blastInventoryHistoryEmpty");
  if (!tbody || !empty) return;
  tbody.innerHTML = history.map(h => `<tr style="border-bottom:1px solid #e2e8f0"><td style="padding:10px;white-space:nowrap">${escapeBlastHtml(formatBlastTimestamp(h.timestamp))}</td><td style="padding:10px;font-weight:700;color:${h.type === "DEDUCTION" ? "#b45309" : "#15803d"}">${escapeBlastHtml(h.type === "DEDUCTION" ? "Stock Deducted" : "Stock Registered")}</td><td style="padding:10px">${escapeBlastHtml(h.product)}</td><td style="padding:10px">${h.type === "DEDUCTION" ? "\u2212" : "+"}${Number(h.volume || 0).toLocaleString()} ${escapeBlastHtml(h.unit)}</td><td style="padding:10px">${Number(h.remaining ?? 0).toLocaleString()} ${escapeBlastHtml(h.unit)}</td><td style="padding:10px">${escapeBlastHtml(h.shift || h.queue || "\u2014")}</td><td style="padding:10px">${escapeBlastHtml(h.details || "\u2014")}</td></tr>`).join("");
  empty.style.display = history.length ? "none" : "block";
}
function renderBlastInventory() {
  const rows = getBlastInventory();
  const tbody = document.getElementById("blastInventoryRows");
  const empty = document.getElementById("blastInventoryEmpty");
  if (!tbody) return;
  tbody.innerHTML = rows.map((r, i) => `<tr style="border-bottom:1px solid #e2e8f0"><td style="padding:10px">${escapeBlastHtml(r.productionDate || r.date || "\u2014")}</td><td style="padding:10px;white-space:nowrap">${escapeBlastHtml(formatBlastTimestamp(r.createdAt))}</td><td style="padding:10px;font-weight:700">${escapeBlastHtml(r.product)}</td><td style="padding:10px">${Number(r.volume).toLocaleString()} ${escapeBlastHtml(r.unit)}</td><td style="padding:10px">${escapeBlastHtml(r.category || r.notes || "\u2014")}</td><td style="padding:10px"><button type="button" class="btn-secondary" onclick="deleteBlastInventory(${i})">Delete</button></td></tr>`).join("");
  empty.style.display = rows.length ? "none" : "block";
  const totals = {}; rows.forEach(r => { const key = r.unit; totals[key] = (totals[key] || 0) + Number(r.volume || 0); });
  document.getElementById("blastInventorySummary").innerHTML = `<div style="background:#eff6ff;padding:12px 16px;border-radius:8px"><strong>${rows.length}</strong><br><span style="font-size:12px">Inventory entries</span></div>` + Object.entries(totals).map(([unit,total]) => `<div style="background:#f0fdf4;padding:12px 16px;border-radius:8px"><strong>${total.toLocaleString(undefined,{maximumFractionDigits:2})} ${escapeBlastHtml(unit)}</strong><br><span style="font-size:12px">Total by unit</span></div>`).join("");
  // Side board: group registered remaining stock under its selected category.
  const categoryGroups = {};
  rows.forEach(r => {
    const rawCategory = String(r.category || r.notes || "Uncategorized").trim() || "Uncategorized";
    const category = rawCategory.toLowerCase() === "debone" ? "Deboned" : rawCategory; // old saved entries
    const product = String(r.product || "Unnamed Product").trim();
    const unit = String(r.unit || "");
    const productionDate = String(r.productionDate || r.date || "").trim() || "\u2014";
    const key = product.toLowerCase() + "||" + unit.toLowerCase() + "||" + productionDate.toLowerCase();
    if (!categoryGroups[category]) categoryGroups[category] = {};
    if (!categoryGroups[category][key]) categoryGroups[category][key] = { product, unit, volume: 0, productionDate };
    categoryGroups[category][key].volume += Number(r.volume || 0);
  });
  const categoryBoard = document.getElementById("blastCategoryInventoryBoard");
  const categoryEmpty = document.getElementById("blastCategoryInventoryEmpty");
  const categoryOrder = ["Marinated", "Timplados", "Branded", "Deboned", "Whole Chicken", "Giblets"];
  const categoryNames = Object.keys(categoryGroups).sort((a,b) => {
    const ai = categoryOrder.findIndex(name => name.toLowerCase() === a.toLowerCase());
    const bi = categoryOrder.findIndex(name => name.toLowerCase() === b.toLowerCase());
    if (ai !== -1 || bi !== -1) return (ai === -1 ? categoryOrder.length : ai) - (bi === -1 ? categoryOrder.length : bi);
    return a.localeCompare(b);
  });
  if (categoryBoard) categoryBoard.innerHTML = categoryNames.map(category => {
    const items = Object.values(categoryGroups[category]).sort((a,b) => { const da = fifoDateKey(a.productionDate), db = fifoDateKey(b.productionDate); if (da !== db) return da < db ? -1 : 1; return a.product.localeCompare(b.product) || a.unit.localeCompare(b.unit); });
    const categoryTotals = {};
    items.forEach(item => { categoryTotals[item.unit] = (categoryTotals[item.unit] || 0) + item.volume; });
    const totalsText = Object.entries(categoryTotals).map(([unit,total]) => `${total.toLocaleString(undefined,{maximumFractionDigits:2})} ${escapeBlastHtml(unit)}`).join(" \u00b7 ") || "0";
    return `<div style="background:#fff;border:1px solid #fed7aa;border-radius:8px;padding:11px 12px"><div style="font-size:13px;font-weight:900;letter-spacing:.4px;color:#c2410c;margin-bottom:8px">${escapeBlastHtml(category).toUpperCase()}</div><div style="display:grid;grid-template-columns:minmax(0,1.2fr) minmax(90px,.8fr) minmax(120px,1fr);gap:8px;padding:6px 0;font-size:11px;font-weight:800;color:#9a3412;border-bottom:1px solid #fed7aa"><span>Product</span><span>Volume</span><span>Production Date</span></div>${items.map(item => `<div style="display:grid;grid-template-columns:minmax(0,1.2fr) minmax(90px,.8fr) minmax(120px,1fr);gap:8px;padding:7px 0;border-bottom:1px solid #ffedd5;font-size:13px;align-items:start"><span style="font-weight:700;overflow-wrap:anywhere">${escapeBlastHtml(item.product)}</span><span style="font-weight:600;overflow-wrap:anywhere">${item.volume.toLocaleString(undefined,{maximumFractionDigits:2})} ${escapeBlastHtml(item.unit)}</span><span style="color:#64748b;overflow-wrap:anywhere">${escapeBlastHtml(item.productionDate)}</span></div>`).join("")}<div style="font-size:13px;font-weight:800;color:#7c2d12;background:#ffedd5;border-radius:6px;padding:7px 8px;margin-top:8px">Total Available Inventory: ${totalsText}</div></div>`;
  }).join("");
  if (categoryEmpty) categoryEmpty.style.display = categoryNames.length ? "none" : "block";
  renderBlastHistory();
}
function parseQueueVolume(raw) {
  const text = String(raw ?? "").trim().replace(/,/g, "");
  const match = text.match(/^([0-9]+(?:\.[0-9]+)?)\s*([a-zA-Z]+)?$/);
  if (!match) return null;
  let unit = (match[2] || "").trim();
  if (unit) {
    const normalized = unit.toLowerCase();
    if (["kgs", "kilogram", "kilograms"].includes(normalized)) unit = "kg";
    else if (["mts", "ton", "tons", "tonne", "tonnes", "metricton", "metrictons"].includes(normalized)) unit = "MT";
    else if (normalized === "box") unit = "boxes";
    else if (normalized === "case") unit = "cases";
  }
  return { amount: Number(match[1]), unit };
}
function applyBlastInventoryDeductions(deductions) {
  const rows = getBlastInventory();
  deductions.forEach(d => {
    let remaining = d.amount;
    // Deduct across matching inventory entries until the requested volume is covered.
    for (const row of rows) {
      if (remaining <= 0) break;
      if (!stockMatches(row, d.product, d.productionDate)) continue;
      if (String(row.unit || "").trim().toLowerCase() !== String(d.unit || "").trim().toLowerCase()) continue;
      const stock = Math.max(0, stockQty(row));
      const take = Math.min(stock, remaining);
      row.volume = Math.round((stock - take + Number.EPSILON) * 100) / 100;
      remaining = Math.round((remaining - take + Number.EPSILON) * 100) / 100;
    }
    const remainingStock = rows.filter(r => stockMatches(r, d.product, d.productionDate) && String(r.unit || "").trim().toLowerCase() === String(d.unit || "").trim().toLowerCase()).reduce((sum,r)=>sum+stockQty(r),0);
    addBlastHistory({type:"DEDUCTION",product:d.product,volume:d.amount,unit:d.unit,remaining:remainingStock,queue:(window.lastRegisteredTruck && window.lastRegisteredTruck.queue) || "New queue",shift:(window.lastRegisteredTruck && window.lastRegisteredTruck.queueShift) || "",details:"Deducted when product was added to Product Queuing for Blast"});
  });
  // Keep zero-stock rows visible so users can see the original registered products.
  saveBlastInventory(rows);
}
function escapeBlastHtml(value) { return String(value ?? "").replace(/[&<>"']/g, c => ({"&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;","'":"&#39;"}[c])); }
document.getElementById("blastInventoryForm").addEventListener("submit", function(e) {
  e.preventDefault(); const rows = getBlastInventory();
  const entry = {date:document.getElementById("blastLogDate").value,productionDate:document.getElementById("blastLogProductionDate").value.trim(),product:document.getElementById("blastLogProduct").value.trim(),volume:Number(document.getElementById("blastLogVolume").value),unit:document.getElementById("blastLogUnit").value,category:document.getElementById("blastLogCategory").value,createdAt:new Date().toISOString()};
  rows.unshift(entry); addBlastHistory({type:"REGISTER",product:entry.product,volume:entry.volume,unit:entry.unit,remaining:rows.filter(r=>String(r.product).toLowerCase()===entry.product.toLowerCase()&&r.unit===entry.unit).reduce((sum,r)=>sum+Number(r.volume||0),0),details:"Category: " + entry.category});
  saveBlastInventory(rows); this.reset(); document.getElementById("blastLogDate").value = new Date().toISOString().slice(0,10); renderBlastInventory();
});
function deleteBlastInventory(index) { if (!confirm("Delete this inventory entry?")) return; const rows = getBlastInventory(); const removed = rows[index]; rows.splice(index,1); saveBlastInventory(rows); if (removed) addBlastHistory({type:"DEDUCTION",product:removed.product,volume:removed.volume,unit:removed.unit,remaining:rows.filter(r=>String(r.product).toLowerCase()===String(removed.product).toLowerCase()&&r.unit===removed.unit).reduce((sum,r)=>sum+Number(r.volume||0),0),shift:removed.shift,details:"Inventory entry deleted manually"}); renderBlastInventory(); }
function resetBlastInventory() { if (!confirm("Reset ALL Blast Product Log & Inventory entries and clear inventory movement history? This cannot be undone. This will not delete existing queue records.")) return; localStorage.removeItem(BLAST_INVENTORY_KEY); localStorage.removeItem(BLAST_HISTORY_KEY); renderBlastInventory(); alert("Blast Product Log & Inventory has been reset. You can register products again."); }
function exportBlastInventory() { const rows = getBlastInventory(); const headers = ["Production Date","Registered At","Product","Available Volume","Unit","Category"]; const csv = [headers,...rows.map(r=>[r.productionDate || r.date,formatBlastTimestamp(r.createdAt),r.product,r.volume,r.unit,r.category || r.notes || ""]) ].map(row=>row.map(v=>'"'+String(v ?? "").replace(/"/g,'""')+'"').join(",")).join("\r\n"); const blob = new Blob(["\ufeff"+csv],{type:"text/csv;charset=utf-8;"}); const url = URL.createObjectURL(blob); const a = document.createElement("a"); a.href=url; a.download="Blast_Product_Inventory.csv"; a.click(); URL.revokeObjectURL(url); }
function exportBlastHistory() { const rows = getBlastHistory(); const headers = ["Date & Time","Activity","Product","Volume Change","Unit","Remaining Stock","Shift","Queue","Details"]; const csv = [headers,...rows.map(h=>[formatBlastTimestamp(h.timestamp),h.type,h.product,(h.type === "DEDUCTION" ? "-" : "+") + Number(h.volume||0),h.unit,h.remaining,h.shift,h.queue,h.details])].map(row=>row.map(v=>'"'+String(v ?? "").replace(/"/g,'""')+'"').join(",")).join("\r\n"); const blob = new Blob(["\ufeff"+csv],{type:"text/csv;charset=utf-8;"}); const url = URL.createObjectURL(blob); const a = document.createElement("a"); a.href=url; a.download="Blast_Inventory_History.csv"; a.click(); URL.revokeObjectURL(url); }
document.getElementById("blastLogDate").value = new Date().toISOString().slice(0,10);
renderBlastInventory();




const BLAST_ACTIVITY_NAMES = ["Barcode Scanning (Fresh Input)", "Layering", "Transfer to Blast Freezing Room", "Blast Freezing", "Harvesting", "Barcoding Weighing (Frozen Output)"];
let activeBlastActivityId = null;
function getBlastActivities(truck) { if (!truck.blastActivities || !Array.isArray(truck.blastActivities)) truck.blastActivities = BLAST_ACTIVITY_NAMES.map(name => ({name,start:"",end:"",remarks:"",manning:"",recorder:"",blastSupervisor:""})); return truck.blastActivities; }
function renderBlastActivityControls(truck) {
 const acts = getBlastActivities(truck);
 const specs = [
  {i:0,label:"Barcode Scanning End",endOnly:true},
  {i:1,label:"Layering"},
  {i:2,label:"Transfer to Blast"},
  {i:4,label:"Harvesting"},
  {i:5,label:"Barcode Weighing"}
 ];
 let html = '<div style="display:flex;flex-wrap:wrap;gap:5px;min-width:240px;margin:5px 0">';
 for (const spec of specs) {
  const a = acts[spec.i] || {start:"",end:""};
  // Blast Freezing End is recorded automatically by the dashboard's Complete button,
  // so do not render a separate manual end button for this activity.
  if (spec.i === 3) {
   // No separate Blast Freezing Start/End activity button: start is recorded by
   // the dashboard's Start Blast Freezing action and end by Complete.
   if (a.start && !a.end) html += `<span style="display:inline-flex;align-items:center;padding:8px 10px;border-radius:6px;background:#eff6ff;color:#1d4ed8;font-size:12px;font-weight:700">Blast Freezing In Progress</span>`;
   else if (a.end) html += `<span style="display:inline-flex;align-items:center;padding:8px 10px;border-radius:6px;background:#dcfce7;color:#166534;font-size:12px;font-weight:700">Blast Freezing Completed</span>`;
  } else if (spec.i === 1) {
   // Layering is manually controlled: always show Start until clicked, then swap to End.
   if (!a.start) html += `<button type="button" class="btn-secondary" onclick="event.preventDefault();event.stopPropagation();stampBlastActivity('${String(truck.id)}',1,'start')">Layering Start</button>`;
   else if (!a.end) html += `<button type="button" class="btn-success" onclick="event.preventDefault();event.stopPropagation();stampBlastActivity('${String(truck.id)}',1,'end')">Layering End</button>`;
   else html += `<button type="button" class="btn-dark" disabled>Layering Ended</button>`;
  } else if (spec.i === 4) {
   // No manual Start here: Harvesting starts from the "Harvest Start" button after Blast Freezing is completed.
   if (a.start && !a.end) {
    html += `<div style="width:100%;display:flex;flex-direction:column;gap:4px;margin-top:4px"><button type="button" class="btn-warning" onclick="event.preventDefault();event.stopPropagation();stampBlastActivity('${String(truck.id)}',4,'end')">\u23f9 Harvest End</button><small class="harvest-live" data-start="${escapeHTML(a.start)}" style="font-weight:700;color:#b45309">Harvesting\u2026 ${blastActivityElapsed(a.start)}</small></div>`;
   } else if (a.end) {
    html += `<div style="width:100%;display:flex;flex-direction:column;gap:4px;margin-top:4px"><button type="button" class="btn-dark" disabled>Harvest Ended</button><small style="font-weight:700;color:#166534">Harvest Duration: ${blastActivityDuration(a.start,a.end)}</small></div>`;
   }
  } else if (spec.endOnly) {
   if (a.start && !a.end) html += `<button type="button" class="btn-secondary" onclick="event.preventDefault();event.stopPropagation();stampBlastActivity('${String(truck.id)}',${spec.i},'end')">${spec.label}</button>`;
   else if (!a.start) html += `<button type="button" class="btn-secondary" disabled title="Barcode Scanning is recorded automatically when Layering Start is clicked">Barcode Scanning</button>`;
  } else if (!a.start) {
   html += `<button type="button" class="btn-secondary" onclick="event.preventDefault();event.stopPropagation();stampBlastActivity('${String(truck.id)}',${spec.i},'start')">${spec.label} Start</button>`;
  } else if (!a.end) {
   const endLabel = spec.i === 5 ? 'Barcode Weighing End' : `${spec.label} End`;
   html += `<button type="button" class="btn-success" onclick="event.preventDefault();event.stopPropagation();stampBlastActivity('${String(truck.id)}',${spec.i},'end')">${endLabel}</button>`;
  } else {
   html += `<button type="button" class="btn-dark" disabled>${spec.i === 5 ? 'Barcode Weighing Ended' : spec.label + ' Ended'}</button>`;
  }
 }
 return html + '</div>';
}
function blastActivityElapsed(start){const ms=Date.now()-new Date(start).getTime();if(!Number.isFinite(ms)||ms<0)return "0h 0m";const m=Math.floor(ms/60000);return Math.floor(m/60)+"h "+(m%60)+"m";}
setInterval(function(){document.querySelectorAll(".harvest-live").forEach(function(el){el.textContent="Harvesting\u2026 "+blastActivityElapsed(el.getAttribute("data-start"));});},15000);
function stampBlastActivity(truckId, activityIndex, side) {
 const truck = trucks.find(t => String(t.id) === String(truckId)); if (!truck) { alert("Could not find this queue. Please refresh the dashboard and try again."); return; }
 const acts = getBlastActivities(truck); const a = acts[activityIndex]; if (!a) return;
 const now = new Date(); const localNow = new Date(now.getTime() - now.getTimezoneOffset() * 60000).toISOString().slice(0,16);
 if (side === 'start') {
  if (a.start) { alert(`${a.name} has already started.`); return; }
  a.start = localNow;
  // Layering Start also records the Barcode Scanning time (same timestamp).
  if (activityIndex === 1 && acts[0] && !acts[0].start) acts[0].start = localNow;
 } else {
  if (!a.start) { alert(`Please start ${a.name} first.`); return; }
  if (a.end) { alert(`${a.name} has already ended.`); return; }
  a.end = localNow;
  if (activityIndex === 4) { truck.harvestEndTimestamp = now.toISOString(); truck.harvestEndTime = now.toLocaleTimeString(); }
 }
 saveData(); renderQueue(); updateStats(); displayCurrentTruck();
 if (typeof renderLiveBlastBoard === 'function') renderLiveBlastBoard();
}
function openBlastActivity(id) {
 const truck = trucks.find(t => t.id === id); if (!truck) return; activeBlastActivityId = id;
 document.getElementById("blastActivityQueueLabel").textContent = `Queue ${truck.queue || "-"} \u00b7 ${truck.product || truck.loadType || "Product"} \u00b7 ${truck.assignedBlast || "Not assigned"}`;
 const activities = getBlastActivities(truck);
 document.getElementById("blastActivityRows").innerHTML = activities.map((a,i)=>`<tr><td style="min-width:160px;font-weight:700">${escapeHTML(a.name || BLAST_ACTIVITY_NAMES[i])}</td><td><input type="datetime-local" id="blastActStart_${i}" value="${escapeHTML(a.start||"")}" style="min-width:180px" disabled title="Timestamp is recorded automatically and cannot be edited"></td><td><input type="datetime-local" id="blastActEnd_${i}" value="${escapeHTML(a.end||"")}" style="min-width:180px" disabled title="Timestamp is recorded automatically and cannot be edited"></td><td id="blastActDuration_${i}" style="min-width:75px">${blastActivityDuration(a.start,a.end)}</td><td><input id="blastActRemarks_${i}" value="${escapeHTML(a.remarks||"")}" style="min-width:120px"></td><td><input id="blastActManning_${i}" value="${escapeHTML(a.manning||"")}" style="min-width:100px"></td><td><input id="blastActRecorder_${i}" value="${escapeHTML(a.recorder||"")}" style="min-width:140px"></td><td><input id="blastActSupervisor_${i}" value="${escapeHTML(a.blastSupervisor||"")}" style="min-width:140px" placeholder="Blast Supervisor"></td></tr>`).join("");
 BLAST_ACTIVITY_NAMES.forEach((_,i)=>["Start","End"].forEach(side=>document.getElementById(`blastAct${side}_${i}`).addEventListener("change",()=>{document.getElementById(`blastActDuration_${i}`).textContent=blastActivityDuration(document.getElementById(`blastActStart_${i}`).value,document.getElementById(`blastActEnd_${i}`).value);} )));
 document.getElementById("blastActivityModal").style.display="block";
}
function closeBlastActivity(){document.getElementById("blastActivityModal").style.display="none";activeBlastActivityId=null;}
function blastActivityDuration(start,end){if(!start||!end)return "-";const ms=new Date(end)-new Date(start);if(ms<0)return "Check time";const mins=Math.floor(ms/60000);return `${Math.floor(mins/60)}h ${mins%60}m`;}
/* ---------- Activity Duration Report (CSV) ---------- */
function blastActivityMinutes(start,end){if(!start||!end)return null;const ms=new Date(end)-new Date(start);if(!Number.isFinite(ms)||ms<0)return null;return Math.floor(ms/60000);}
function fmtActMins(m){return m===null?"":Math.floor(m/60)+"h "+(m%60)+"m";}
function fmtActStamp(v){if(!v)return "";const d=new Date(v);return Number.isNaN(d.getTime())?v:d.toLocaleString();}
function blastActivityReportRows(truck){
 const acts=getBlastActivities(truck);
 const rows=[];let total=0;
 BLAST_ACTIVITY_NAMES.forEach((name,i)=>{
  const a=acts[i]||{};const mins=blastActivityMinutes(a.start,a.end);
  if(mins!==null)total+=mins;
  const status=a.end?"Ended":a.start?"In progress":"Not started";
  rows.push([truck.queue||"",truck.product||truck.loadType||"",truck.volume||"",truck.assignedBlast||"",truck.queueDate||truck.date||"",truck.queueShift||"",
   name,fmtActStamp(a.start),fmtActStamp(a.end),fmtActMins(mins),mins===null?"":mins,status,a.manning||"",a.recorder||"",a.blastSupervisor||"",a.remarks||""]);
 });
 return {rows,total};
}
const BLAST_ACT_REPORT_HEADERS=["Queue","Product","Volume","Blast Freezer","Queue Date","Shift","Activity","Start Date & Time","End Date & Time","Duration","Duration (minutes)","Status","Manning","Recorder / Team Leader","Blast Supervisor","Remarks"];
function blastActCsv(rows){return "\ufeff"+rows.map(r=>r.map(v=>'"'+String(v==null?"":v).replace(/"/g,'""')+'"').join(",")).join("\r\n");}
function downloadBlastActivityReport(){
 const truck=trucks.find(t=>t.id===activeBlastActivityId);
 if(!truck){alert("Could not find this queue.");return;}
 const {rows,total}=blastActivityReportRows(truck);
 const blank=new Array(BLAST_ACT_REPORT_HEADERS.length).fill("");
 const totalRow=blank.slice();totalRow[6]="TOTAL ACTIVITY DURATION";totalRow[9]=fmtActMins(total);totalRow[10]=total;
 const csv=blastActCsv([BLAST_ACT_REPORT_HEADERS,...rows,totalRow]);
 downloadFile(csv,"MHC_Activity_Report_"+(truck.queue||"queue")+"_"+todayString()+".csv","text/csv;charset=utf-8;");
}
function exportAllBlastActivityReport(){
 const list=todaysTrucks();
 if(!list.length){alert("There is no queue data to export for today.");return;}
 const all=[BLAST_ACT_REPORT_HEADERS];const blank=new Array(BLAST_ACT_REPORT_HEADERS.length).fill("");
 list.forEach(truck=>{
  const {rows,total}=blastActivityReportRows(truck);
  all.push(...rows);
  const t=blank.slice();t[0]=truck.queue||"";t[6]="TOTAL ACTIVITY DURATION";t[9]=fmtActMins(total);t[10]=total;all.push(t);
  all.push(blank.slice());
 });
 downloadFile(blastActCsv(all),"MHC_Activity_Duration_Report_"+todayString()+".csv","text/csv;charset=utf-8;");
}
function saveBlastActivity(){const truck=trucks.find(t=>t.id===activeBlastActivityId);if(!truck)return;const existing=getBlastActivities(truck);truck.blastActivities=BLAST_ACTIVITY_NAMES.map((name,i)=>({name,start:existing[i]?.start||"",end:existing[i]?.end||"",remarks:document.getElementById(`blastActRemarks_${i}`).value.trim(),manning:document.getElementById(`blastActManning_${i}`).value.trim(),recorder:document.getElementById(`blastActRecorder_${i}`).value.trim(),blastSupervisor:document.getElementById(`blastActSupervisor_${i}`).value.trim()}));saveData();renderQueue();renderLiveBlastBoard();closeBlastActivity();alert("Blast activity log saved. Start/end timestamps are locked and cannot be edited.");}
function renderTVActivitySummary(truck){const acts=Array.isArray(truck.blastActivities)?truck.blastActivities:[];const filled=acts.filter(a=>a.start||a.end||a.remarks||a.manning||a.recorder||a.blastSupervisor);if(!filled.length)return "";return `<div style="margin-top:8px;padding:8px;background:#172554;border-radius:8px"><strong style="color:#bfdbfe">ACTIVITY LOG</strong>${filled.map(a=>`<small style="display:block;color:#e2e8f0;margin-top:4px">${escapeHTML(a.name)} \u00b7 Start: ${escapeHTML(a.start ? new Date(a.start).toLocaleString() : "-")} \u00b7 End: ${escapeHTML(a.end ? new Date(a.end).toLocaleString() : "-")} \u00b7 Duration: ${escapeHTML(blastActivityDuration(a.start,a.end))}${a.remarks ? " \u00b7 Remarks: "+escapeHTML(a.remarks):""}${a.manning ? " \u00b7 Manning: "+escapeHTML(a.manning):""}${a.recorder ? " \u00b7 Recorder: "+escapeHTML(a.recorder):""}${a.blastSupervisor ? " \u00b7 Blast Supervisor: "+escapeHTML(a.blastSupervisor):""}</small>`).join("")}</div>`;}
