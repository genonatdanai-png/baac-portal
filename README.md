<!DOCTYPE html>
<html lang="th">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>BAAC Branch Portal</title>

<style>
:root{
    --baac-green:#006837;
    --baac-light:#00a651;
    --bg:#f4f7f9;
}

*{
    box-sizing:border-box;
}

body{
    margin:0;
    background:var(--bg);
    font-family:'Segoe UI',sans-serif;
}

.header{
    background:linear-gradient(135deg,#006837,#00a651);
    color:#fff;
    padding:30px;
    border-radius:0 0 20px 20px;
    box-shadow:0 5px 20px rgba(0,0,0,.15);
}

.header h1{
    margin:0;
    font-size:32px;
}

.header p{
    margin:8px 0 0;
    opacity:.9;
}

.search-box{
    padding:25px 20px 5px;
}

.search-box input{
    width:100%;
    max-width:700px;
    display:block;
    margin:auto;
    padding:14px 18px;
    border-radius:12px;
    border:1px solid #dcdcdc;
    font-size:15px;
    box-shadow:0 4px 10px rgba(0,0,0,.08);
}

.search-box input:focus{
    outline:none;
    border-color:#00a651;
    box-shadow:0 0 0 3px rgba(0,166,81,.15);
}

.portal{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(280px,1fr));
    gap:20px;
    padding:20px;
}

.card{
    background:#fff;
    border-radius:18px;
    padding:22px;
    box-shadow:0 8px 20px rgba(0,0,0,.08);
    transition:.3s ease;
    border:1px solid #e9ecef;
    position:relative;
    overflow:hidden;
}

.card:before{
    content:"";
    position:absolute;
    top:0;
    left:0;
    width:100%;
    height:5px;
    background:linear-gradient(90deg,#006837,#00a651);
}

.card:hover{
    transform:translateY(-5px);
    box-shadow:0 15px 30px rgba(0,0,0,.15);
}

.card h3{
    margin-top:0;
    margin-bottom:15px;
    color:#006837;
}

.card select{
    width:100%;
    padding:12px;
    border-radius:10px;
    border:1px solid #dcdcdc;
}

.btn{
    width:100%;
    padding:12px;
    border:none;
    border-radius:10px;
    background:linear-gradient(135deg,#006837,#00a651);
    color:#fff;
    font-size:15px;
    font-weight:600;
    cursor:pointer;
}

.btn:hover{
    opacity:.9;
}

.footer{
    text-align:center;
    padding:20px;
    color:#888;
    font-size:12px;
}
</style>
</head>
<body>

<div class="header">
    <h1>🏦 BAAC TRANG (By Geno)</h1>
    <p>ศูนย์รวมระบบงานและลิงก์สำคัญสำหรับงานสาขา (ส่วนงานกลยุทธ์)</p>
</div>

<div class="search-box">
    <input
        type="text"
        id="quickSearch"
        placeholder="🔍 ค้นหาระบบ, เมนู, หรือชื่อบริการ..."
        onkeyup="filterCards()">
</div>

<div class="portal">

    <div class="card">
        <h3>📄 สารบรรณ</h3>
        <select onchange="openLink(this)">
            <option value="">เลือกเมนู</option>
            <option value="https://saraban.app.baac.or.th/BAAC_DOC_FLOW/system/data_basic/doc_search.php?ciUzRGhvbWUlMjZtZW51X2lkJTNEMTAwMDAzMSUyNm1lbnVfc3ViX2lkJTNEMTAxMDAzMQ==">ค้นหา</option>
            <option value="https://saraban.app.baac.or.th/BAAC_DOC_FLOW/system/receive/book_rec_dep_in.php?ciUzRGhvbWUlMjZtZW51X2lkJTNEMTAwMDAwNSUyNm1lbnVfc3ViX2lkJTNEMjAwMDAyOQ==">รับหนังสือภายใน</option>
            <option value="https://saraban.app.baac.or.th/BAAC_DOC_FLOW/system/receive/book_disp_out.php?ciUzRGhvbWUlMjZtZW51X2lkJTNEMTAyMDEwMSUyNm1lbnVfc3ViX2lkJTNEMjAwMDAzNA==">รับหนังสือภายนอก</option>
            <option value="https://saraban.app.baac.or.th/BAAC_DOC_FLOW/system/receive/book_disp_out.php?bWVudV9pZCUzRDEwMjAxMDElMjZtZW51X3N1Yl9pZCUzRDIwMDAwMzU=">รับหนังสือภายนอก ลับ</option>
            <option value="https://saraban.app.baac.or.th/BAAC_DOC_FLOW/system/create/book_form_list.php?ciUzRGhvbWUlMjZtZW51X2lkJTNEMTAwMDAyOSUyNm1lbnVfc3ViX2lkJTNENDAwMDA5OA==">ตอบหนังสือภายใน</option> 
            <option value="https://saraban.app.baac.or.th/BAAC_DOC_FLOW/system/create/book_form_list_out.php?bWVudV9pZCUzRDEwMDAwMjklMjZtZW51X3N1Yl9pZCUzRDQwMDAzMjQ=">ตอบหนังสือภายนอก</option>
            <option value="https://saraban.app.baac.or.th/BAAC_DOC_FLOW/baac_public/HandbookSearch.php">คู่มือ</option>
            <option value="https://saraban.app.baac.or.th/BAAC_DOC_FLOW/system/receive/book_sign_in.php?bWVudV9pZCUzRDEwMDAwMDUlMjZtZW51X3N1Yl9pZCUzRDgwMDAyMzI=">แก้ไขหนังสือหลังตรวจทาน</option>
            <option value="https://saraban.app.baac.or.th/BAAC_DOC_FLOW/system/receive/book_circu_in.php?ciUzRGhvbWUlMjZtZW51X2lkJTNEMTAzMDEwMSUyNm1lbnVfc3ViX2lkJTNEMTAzMDIwMQ==">บันทึกเวียน</option>
            <option value="https://saraban.app.baac.or.th/BAAC_DOC_FLOW/system/create_number/book_out_disp.php?ciUzRGhvbWUlMjZtZW51X2lkJTNEMTAwMDA5MSUyNm1lbnVfc3ViX2lkJTNEODAwMDIyNw==">ออกเลขหนังสือภายนอก</option>
            <option value="https://saraban.app.baac.or.th/BAAC_DOC_FLOW/system/send/book_disp_in.php?ciUzRGhvbWUlMjZtZW51X2lkJTNEMTAwMDAyOCUyNm1lbnVfc3ViX2lkJTNEMzAwMDAzOA==">หนังสือส่งออก</option>
        </select>
    </div>

    <div class="card">
        <h3>🏢 ระบบบริหารสาขา</h3>
        <button class="btn"
            onclick="window.open('https://iris-next.app.baac.or.th/SPS0008BT/','_blank')">
            เปิดระบบ
        </button>
    </div>

    <div class="card">
        <h3>📁 เอกสารสำคัญ</h3>
        <select onchange="openLink(this)">
            <option value="">เลือกเมนู</option>
            <option value="https://namthip.app.baac.or.th/dmscontract/index.php/Main/keepcontract">สัญญารายเล็ก</option>
            <option value="https://namthip.app.baac.or.th/dmscontract/index.php/Main/uploadcontract">อัพโหลดรายเล็ก</option>
            <option value="https://namthip.app.baac.or.th/documentCenter/index.php/Main/keepcontract">สัญญารายใหญ่</option>
            <option value="https://namthip.app.baac.or.th/documentCenter/index.php/Main/uploadcontract">อัพโหลดรายใหญ่</option>
            <option value="https://namthip.app.baac.or.th/collateral/index.php/Main/keepcollateral">หลักประกัน</option>
            <option value="https://namthip.app.baac.or.th/collateral/index.php/Main/uploadcollateral">อัพโหลดหลักประกัน</option>
            <option value="https://namthip.app.baac.or.th/document/index.php/Main/closerecheck">ตรวจนับ</option>
        </select>
    </div>

    <div class="card">
        <h3>🌐 Google Workspace</h3>
        <select onchange="openLink(this)">
            <option value="">เลือกเมนู</option>
            <option value="https://drive.google.com">Google Drive</option>
            <option value="https://mail.google.com">Gmail</option>
            <option value="https://translate.google.com">Translate</option>
            <option value="https://notebooklm.google.com">NotebookLM</option>
            <option value="https://maps.google.com">Google Maps</option>
        </select>
    </div>

    <div class="card">
        <h3>☁️ Microsoft 365</h3>
        <select onchange="openLink(this)">
            <option value="">เลือกเมนู</option>
            <option value="https://outlook.cloud.microsoft/mail/">Outlook</option>
            <option value="https://bibaac-my.sharepoint.com/">OneDrive</option>
            <option value="https://teams.cloud.microsoft/">Teams</option>
            <option value="https://forms.cloud.microsoft/">Forms</option>
            <option value="https://excel.cloud.microsoft/">Excel</option>
            <option value="https://word.cloud.microsoft/">Word</option>
            <option value="https://m365.cloud.microsoft/chat?es=SSR">Copilot AI</option>
        </select>
    </div>

    <div class="card">
        <h3>👤 ค้นหาพนักงาน</h3>
        <select onchange="openLink(this)">
            <option value="">เลือกเมนู</option>
            <option value="https://member.baac.or.th/contacts/index.php">BAAC Contacts</option>
            <option value="http://xms2/it/mail/index.php?action=check-regis">Email พนักงาน</option>
            <option value="http://hriswebp.it.baac.or.th/essweb/frmMenuGeneral.aspx">ESS</option>
        </select>
    </div>

    <div class="card">
        <h3>⭐ ระบบอื่น ๆ</h3>
        <select onchange="openLink(this)">
            <option value="">เลือกเมนู</option>
            <option value="https://baacnet.it.baac.or.th/express/">ระบบงาน</option>
            <option value="http://terminal.it.baac.or.th/branches/index.php">รับส่งข้อมูลสาขา</option>
            <option value="http://wms2/pr/wp-pr/">สื่อสารองค์กร สอ.</option>
            <option value="https://promptpay.it.baac.or.th/anyid_register/login.php">พร้อมเพย์</option>
            <option value="https://learningplus.baac.or.th/page/home/">E-Learning</option>
            <option value="http://hriswebp.it.baac.or.th/ctime/">CTIME</option>
            <option value="http://hriswebp/pmsweb/Default.aspx">ป.2</option>
            <option value="https://jewel.int.baac.or.th/branchoutlet/">OUTLET</option>
        </select>
    </div>

   <div class="card">
        <h3>♥ จำนอง</h3>
        <select onchange="openLink(this)">
            <option value="">เลือกเมนู</option>
            <option value="https://loan.baac.tech/login#/">BAAC Loan</option>
            <option value="http://barn.it.baac.or.th/loanDocs/">จำนอง เก่า</option>
        </select>
    </div>
<!-- Floating Copilot Button -->
<div id="copilot-float"
     title="เปิด Microsoft Copilot"
     onclick="window.open('https://m365.cloud.microsoft/chat','_blank')">
    🤖
</div>

<style>
#copilot-float{
    position:fixed;
    bottom:25px;
    right:25px;
    width:65px;
    height:65px;
    border-radius:50%;
    background:linear-gradient(135deg,#006837,#00a651);
    color:#fff;
    display:flex;
    justify-content:center;
    align-items:center;
    font-size:30px;
    cursor:pointer;
    box-shadow:0 6px 20px rgba(0,0,0,.25);
    z-index:9999;
    transition:all .3s ease;
}

#copilot-float:hover{
    transform:translateY(-3px) scale(1.08);
    box-shadow:0 10px 25px rgba(0,0,0,.35);
}
</style>
<div class="card">
    <h3>📅 Dashboard งานประจำวัน</h3>

    <button class="btn"
        onclick="window.open('https://tasks.office.com/','_blank')">
        เปิด Dashboard งาน
    </button>
 </div>
</div>
<div class="footer">
    BAAC Branch Portal | ธนาคารเพื่อการเกษตรและสหกรณ์การเกษตร
</div>

<script>
function openLink(select){
    if(select.value){
        window.open(select.value,'_blank');
        select.selectedIndex = 0;
    }
}

function filterCards(){
    let keyword = document
        .getElementById("quickSearch")
        .value
        .toLowerCase();

    let cards = document.querySelectorAll(".card");

    cards.forEach(card=>{
        let text = card.innerText.toLowerCase();

        if(text.includes(keyword)){
            card.style.display="";
        }else{
            card.style.display="none";
        }
    });
}
</script>

</body>
</html>
