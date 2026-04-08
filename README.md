<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Oman Drone Taxi | احجز رحلتك المستقبلية</title>
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;700&display=swap" rel="stylesheet">
    <style>
        :root { --main-red: #ce1126; --main-green: #009639; --dark-grey: #2d2d2d; }
        body { font-family: 'Cairo', sans-serif; margin: 0; line-height: 1.6; color: #333; background: #f4f7f6; scroll-behavior: smooth; }
        
        header { background: white; padding: 15px 5%; display: flex; justify-content: space-between; align-items: center; box-shadow: 0 2px 5px rgba(0,0,0,0.1); position: sticky; top: 0; z-index: 1000; }
        .logo { font-weight: bold; color: var(--main-red); font-size: 24px; text-decoration: none; }
        
        .hero { background: linear-gradient(45deg, rgba(0,150,57,0.7), rgba(206,17,38,0.7)), url('https://images.unsplash.com/photo-1473960104505-49bd6fc15854?auto=format&fit=crop&q=80'); 
                height: 550px; background-size: cover; background-position: center; color: white; text-align: center; display: flex; flex-direction: column; justify-content: center; padding: 0 20px; }
        .hero h1 { font-size: 3rem; margin-bottom: 10px; text-shadow: 2px 2px 4px rgba(0,0,0,0.3); }

        .booking-form { background: white; max-width: 500px; margin: -80px auto 50px; padding: 35px; border-radius: 20px; box-shadow: 0 15px 35px rgba(0,0,0,0.15); position: relative; z-index: 10; border-bottom: 8px solid var(--main-green); }
        .booking-form h3 { color: var(--dark-grey); margin-top: 0; }
        
        input, select, button { width: 100%; padding: 14px; margin: 12px 0; border: 2px solid #eee; border-radius: 12px; box-sizing: border-box; font-family: 'Cairo'; outline: none; transition: 0.3s; }
        input:focus { border-color: var(--main-green); }
        
        button { background: var(--main-red); color: white; border: none; cursor: pointer; font-size: 18px; font-weight: bold; box-shadow: 0 4px 15px rgba(206,17,38,0.3); }
        button:hover { background: #a50d1e; transform: translateY(-2px); }
        button:active { transform: translateY(0); }

        .steps-container { padding: 80px 10%; display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 30px; }
        .step { background: white; padding: 40px 20px; border-radius: 20px; text-align: center; transition: 0.4s; border: 1px solid #eee; }
        .step:hover { transform: translateY(-10px); border-color: var(--main-green); box-shadow: 0 10px 25px rgba(0,0,0,0.05); }
        .step-number { background: var(--main-green); color: white; width: 50px; height: 50px; border-radius: 50%; display: flex; align-items: center; justify-content: center; margin: 0 auto 20px; font-weight: bold; font-size: 20px; }

        #confirmation { display: none; background: #e7f5ed; color: #155724; padding: 20px; border-radius: 12px; margin-top: 20px; text-align: center; border: 1px solid #c3e6cb; }

        footer { background: var(--dark-grey); color: white; text-align: center; padding: 40px; margin-top: 50px; }
    </style>
</head>
<body>

<header>
    <a href="#" class="logo">Oman Drone Taxi 🚁</a>
    <nav>الرئيسية | الوجهات | المساعدة</nav>
</header>

<section class="hero">
    <h1>مستقبل التنقل في عُمان</h1>
    <p>احجز رحلتك بالدرون بلمسة زر واحدة</p>
</section>

<div class="booking-form">
    <h3 style="text-align: center;">ابدأ رحلتك الآن</h3>
    <input type="text" id="startPoint" placeholder="نقطة الانطلاق (مثلاً: مطار مسقط)">
    <input type="text" id="endPoint" placeholder="وجهة الوصول (مثلاً: صلالة)">
    <select id="taxiType">
        <option value="الدرون السريع">نوع الطائرة: شخص واحد (اقتصادية)</option>
        <option value="الدرون العائلي">نوع الطائرة: عائلية (4 أشخاص)</option>
        <option value="الدرون الفاخر">نوع الطائرة: VIP (إطلالة بانورامية)</option>
    </select>
    <button onclick="confirmBooking()">تأكيد وتحديد الموعد</button>
    
    <div id="confirmation">
        <strong>تم استلام طلبك بنجاح! ✅</strong><br>
        <span id="confirmText"></span>
        <br><small>ستصلك طائرة <b id="droneName"></b> خلال 5 دقائق.</small>
    </div>
</div>

<section class="steps-container">
    <div class="step">
        <div class="step-number">1</div>
        <h3>اطلب</h3>
        <p>اختر موقعك ووجهتك عبر الخريطة التفاعلية.</p>
    </div>
    <div class="step">
        <div class="step-number">2</div>
        <h3>انطلق</h3>
        <p>توجه إلى أقرب "فيرتيبورت" (منصة إقلاع).</p>
    </div>
    <div class="step">
        <div class="step-number">3</div>
        <h3>استمتع</h3>
        <p>استرخِ وشاهد جمال عُمان من الأعلى.</p>
    </div>
    <div class="step">
        <div class="step-number">4</div>
        <h3>وصلت!</h3>
        <p>هبوط دقيق في النقطة المحددة دون زحام.</p>
    </div>
</section>

<footer>
    <p>© 2026 تاكسي عُمان الطائر - نحو رؤية عُمان 2040</p>
</footer>

<script>
    function confirmBooking() {
        const start = document.getElementById('startPoint').value;
        const end = document.getElementById('endPoint').value;
        const type = document.getElementById('taxiType').value;
        const confirmBox = document.getElementById('confirmation');

        if (start === "" || end === "") {
            alert("يرجى إدخال نقطة الانطلاق والوصول أولاً!");
            return;
        }

        document.getElementById('confirmText').innerText = `من ${start} إلى ${end}`;
        document.getElementById('droneName').innerText = type;
        
        confirmBox.style.display = "block";
        window.scrollTo({ top: 300, behavior: 'smooth' });
    }
</script>

</body>
</html>
