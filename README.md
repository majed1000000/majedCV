<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ماجد مسعد العمراني - مصمم جرافيك</title>
    
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@400;500;700;800&display=swap" rel="stylesheet">

    <style>
        /* الإعدادات الأساسية */
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            background-color: #1e2833; /* لون الخلفية الكحلي/الرمادي الداكن */
            color: #ffffff;
            font-family: 'Tajawal', sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            line-height: 1.6;
        }

        /* الحاوية الرئيسية للتصميم */
        .portfolio-container {
            max-width: 950px;
            width: 100%;
            padding: 40px 20px;
        }

        /* التاج العلوي (أعلى اليسار) */
        .top-badge-container {
            display: flex;
            justify-content: flex-end; /* يدفعه لليسار في اتجاه RTL */
            margin-bottom: 30px;
        }

        .badge {
            border: 1px solid #3c4b5e;
            border-radius: 50px;
            padding: 6px 24px;
            font-size: 15px;
            color: #d1d8e0;
            font-weight: 500;
        }

        /* العناوين والنصوص */
        h1 {
            font-size: 70px;
            font-weight: 800;
            margin-bottom: 10px;
            letter-spacing: -1px;
        }

        h2 {
            font-size: 26px;
            font-weight: 700;
            margin-bottom: 30px;
            color: #f1f5f9;
        }

        .description {
            font-size: 18px;
            color: #94a3b8;
            margin-bottom: 15px;
            width: 85%;
        }

        .availability {
            font-size: 18px;
            color: #94a3b8;
            margin-bottom: 40px;
        }

        /* قسم المهارات (الأزرار السفلية لليسار) */
        .skills-container {
            display: flex;
            justify-content: flex-end; /* المحاذاة لليسار */
            gap: 15px;
            margin-bottom: 50px;
            flex-wrap: wrap;
        }

        .skill-tag {
            border: 1px solid #3c4b5e;
            border-radius: 50px;
            padding: 8px 24px;
            font-size: 15px;
            color: #d1d8e0;
            font-weight: 500;
        }

        /* قسم بطاقات التواصل */
        .contact-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
        }

        .contact-card {
            border: 1px solid #3c4b5e;
            border-radius: 12px;
            padding: 25px;
            display: flex;
            flex-direction: column;
            min-height: 140px;
            background-color: transparent;
        }

        .contact-label {
            font-size: 15px;
            color: #94a3b8;
            margin-bottom: auto; /* يدفع القيمة للأسفل */
        }

        .contact-value {
            font-size: 22px;
            font-weight: 700;
            color: #ffffff;
        }

        /* تعديل اتجاه ومكان رقم الجوال ليكون في أسفل اليسار LTR */
        .phone-value {
            align-self: flex-end; /* لليسار في RTL */
            direction: ltr; /* لضبط تنسيق الرقم بمفتاح الدولة */
        }

        /* التصميم المتجاوب للجوال */
        @media (max-width: 768px) {
            h1 { font-size: 45px; }
            h2 { font-size: 20px; }
            .description { width: 100%; }
            .contact-grid { grid-template-columns: 1fr; }
            .skills-container, .top-badge-container { justify-content: flex-start; }
            .phone-value { align-self: flex-start; }
        }
    </style>
</head>
<body>

    <div class="portfolio-container">
        
        <div class="top-badge-container">
            <span class="badge">مصمم جرافيك | هويات بصرية ومنتجات</span>
        </div>

        <h1>ماجد مسعد العمراني</h1>
        <h2>أصنع حلولاً بصرية ترفع قيمة العلامة وتترك انطباعاً احترافياً.</h2>

        <p class="description">
            أقدم خدمات تصميم متخصصة في الهويات البصرية، المطبوعات، الهدايا الدعائية، وتصميم المنتجات — من الفكرة إلى تنفيذ بصري متقن يخدم أهداف العمل والتسويق.
        </p>
        
        <p class="availability">
            متاح للتعاون مع الشركات والأفراد في جدة وداخل المملكة.
        </p>

        <div class="skills-container">
            <span class="skill-tag">هوية بصرية</span>
            <span class="skill-tag">مطبوعات</span>
            <span class="skill-tag">هدايا دعائية</span>
            <span class="skill-tag">تصميم منتجات</span>
        </div>

        <div class="contact-grid">
            <div class="contact-card">
                <span class="contact-label">الموقع</span>
                <span class="contact-value">جدة، المملكة العربية السعودية</span>
            </div>
            
            <div class="contact-card">
                <span class="contact-label">الجوال</span>
                <span class="contact-value phone-value">+966 57 246 9285</span>
            </div>
        </div>

    </div>

</body>
</html>
