<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>الملف الشخصي</title>
  <meta name="description" content="ملف شخصي عربي بتصميم بصري سينمائي وحركة سلسة." />
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;500;600;700;800&display=swap" rel="stylesheet" />
  <style>
    :root {
      --خلفية: #090c14;
      --لوحة: #0f1524;
      --سطح: #131d31;
      --نص: #f3f6ff;
      --نص-هادئ: #a9b4d1;
      --حدود: rgba(205, 219, 255, 0.14);
      --توهج: #7ba7ff;
      --توهج-ثان: #7cf0d2;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      font-family: "Cairo", "Segoe UI", Tahoma, sans-serif;
      color: var(--نص);
      background:
        radial-gradient(circle at 20% -10%, rgba(124, 240, 210, 0.18), transparent 45%),
        radial-gradient(circle at 80% 0%, rgba(123, 167, 255, 0.2), transparent 40%),
        var(--خلفية);
      min-height: 100vh;
      line-height: 1.75;
      overflow-x: hidden;
    }

    .وهج-خلفي {
      position: fixed;
      inset: -20% auto auto -10%;
      width: 540px;
      height: 540px;
      background: radial-gradient(circle, rgba(123, 167, 255, 0.22), transparent 65%);
      filter: blur(6px);
      pointer-events: none;
      animation: تنفس 8s ease-in-out infinite;
      z-index: -1;
    }

    .حاوية {
      width: min(1100px, 92%);
      margin: 0 auto;
    }

    .شريط {
      position: sticky;
      top: 1rem;
      z-index: 20;
      padding: 0 1rem;
      display: flex;
      justify-content: center;
      background: transparent;
      border: none;
    }

    .شريط-داخلي {
      width: fit-content;
      max-width: min(100%, 920px);
      min-height: 56px;
      margin: 0 auto;
      padding: 0.45rem 0.7rem;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 0.35rem;
      border: 1px solid var(--حدود);
      border-radius: 999px;
      background: rgba(9, 12, 20, 0.78);
      backdrop-filter: blur(14px);
      box-shadow: 0 10px 34px rgba(0, 0, 0, 0.28);
    }

    .روابط {
      display: flex;
      flex-wrap: nowrap;
      align-items: center;
      justify-content: center;
      gap: 0.25rem;
      overflow-x: auto;
      scrollbar-width: none;
    }

    .روابط::-webkit-scrollbar {
      display: none;
    }

    .رابط {
      color: var(--نص-هادئ);
      text-decoration: none;
      border: 1px solid transparent;
      border-radius: 999px;
      padding: 0.45rem 0.9rem;
      transition: 0.25s ease;
    }

    .رابط:hover {
      color: var(--نص);
      border-color: var(--حدود);
      background: rgba(255, 255, 255, 0.04);
    }

    .بطل {
      padding: 5.2rem 0 2.2rem;
      display: grid;
      gap: 1rem;
      max-width: 820px;
    }

    .شارة {
      justify-self: start;
      font-size: 0.82rem;
      font-weight: 600;
      color: #d7e3ff;
      border: 1px solid var(--حدود);
      background: rgba(255, 255, 255, 0.04);
      border-radius: 999px;
      padding: 0.4rem 0.75rem;
      letter-spacing: 0.2px;
    }

    h1 {
      font-size: clamp(2rem, 6vw, 3.6rem);
      line-height: 1.2;
      max-width: 900px;
      text-wrap: balance;
      font-weight: 800;
      margin-top: 0.1rem;
    }

    .عنوان-فرعي {
      color: #dce6ff;
      font-size: clamp(1.05rem, 2vw, 1.28rem);
      font-weight: 600;
      line-height: 1.6;
      max-width: 700px;
    }

    .وصف-بطل {
      color: var(--نص-هادئ);
      max-width: 700px;
      font-size: clamp(0.98rem, 1.2vw, 1.08rem);
      line-height: 1.85;
    }

    .نص-مساعد {
      color: #9facc9;
      font-size: 0.9rem;
      max-width: 700px;
      line-height: 1.7;
    }

    .تخصصات-بطل {
      display: flex;
      flex-wrap: wrap;
      gap: 0.45rem;
      margin-top: 0.15rem;
    }

    .تخصصات-بطل span {
      font-size: 0.82rem;
      color: #d2dcf8;
      border: 1px solid var(--حدود);
      border-radius: 999px;
      padding: 0.32rem 0.7rem;
      background: rgba(255, 255, 255, 0.03);
    }

    .بيانات-تواصل {
      display: grid;
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: 0.75rem;
      max-width: 760px;
      width: 100%;
      margin-top: 0.35rem;
    }

    .عنصر-تواصل {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: stretch;
      min-height: 78px;
      border: 1px solid var(--حدود);
      border-radius: 12px;
      padding: 0.8rem 1rem;
      background: rgba(255, 255, 255, 0.03);
    }

    .تسمية-تواصل {
      display: block;
      font-size: 0.78rem;
      color: var(--نص-هادئ);
      margin-bottom: 0.35rem;
      letter-spacing: 0.2px;
      line-height: 1.3;
    }

    .قيمة-تواصل {
      display: block;
      width: 100%;
      color: #e8efff;
      font-weight: 600;
      font-size: 0.96rem;
      line-height: 1.45;
      text-align: start;
    }

    .رابط-تواصل {
      text-decoration: none;
      transition: color 0.2s ease;
      direction: ltr;
      unicode-bidi: isolate;
      font-variant-numeric: tabular-nums;
      letter-spacing: 0.4px;
    }

    .رابط-تواصل:hover {
      color: var(--توهج-ثان);
    }

    .أزرار {
      display: flex;
      flex-wrap: wrap;
      gap: 0.7rem;
      margin-top: 0.6rem;
    }

    .زر {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      min-height: 44px;
      padding: 0.7rem 1.1rem;
      border-radius: 12px;
      text-decoration: none;
      font-weight: 600;
      border: 1px solid transparent;
      transition: transform 0.25s ease, box-shadow 0.25s ease, background 0.25s ease;
    }

    .زر-أساسي {
      background: linear-gradient(135deg, var(--توهج), var(--توهج-ثان));
      color: #08101f;
      box-shadow: 0 6px 30px rgba(124, 240, 210, 0.25);
    }

    .زر-أساسي:hover {
      transform: translateY(-2px);
      box-shadow: 0 10px 36px rgba(124, 240, 210, 0.33);
    }

    .زر-ثانوي {
      color: var(--نص);
      border-color: var(--حدود);
      background: rgba(255, 255, 255, 0.03);
    }

    .زر-ثانوي:hover {
      transform: translateY(-2px);
      background: rgba(255, 255, 255, 0.08);
    }

    .زر-واتساب {
      background: linear-gradient(135deg, #25d366, #1ebe5b);
      color: #ffffff;
      border-color: rgba(255, 255, 255, 0.18);
      box-shadow: 0 10px 26px rgba(37, 211, 102, 0.3);
      min-width: 220px;
    }

    .زر-واتساب:hover {
      transform: translateY(-2px);
      box-shadow: 0 14px 30px rgba(37, 211, 102, 0.38);
      filter: saturate(1.05);
    }

    .واتساب-عائم {
      position: fixed;
      left: 1.25rem;
      bottom: 1.25rem;
      z-index: 50;
      width: 58px;
      height: 58px;
      border-radius: 50%;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      background: linear-gradient(135deg, #25d366, #1ebe5b);
      color: #ffffff;
      box-shadow: 0 10px 28px rgba(37, 211, 102, 0.38);
      transition: transform 0.25s ease, box-shadow 0.25s ease;
      text-decoration: none;
    }

    .واتساب-عائم svg {
      width: 30px;
      height: 30px;
    }

    .واتساب-عائم:hover {
      transform: translateY(-3px) scale(1.05);
      box-shadow: 0 14px 34px rgba(37, 211, 102, 0.48);
    }

    #التواصل .رأس-قسم {
      flex-direction: column;
      align-items: center;
      text-align: center;
      width: 100%;
      margin-bottom: 1.25rem;
    }

    .لوحة-تواصل {
      display: flex;
      flex-direction: column;
      gap: 0.75rem;
      max-width: 520px;
      margin: 0 auto;
      padding: 1.15rem;
      border: 1px solid var(--حدود);
      border-radius: 18px;
      background: linear-gradient(165deg, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0.015));
      box-shadow: 0 12px 32px rgba(0, 0, 0, 0.18);
    }

    .صف-تواصل {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 1rem;
      padding: 0.9rem 1rem;
      border: 1px solid var(--حدود);
      border-radius: 12px;
      background: rgba(255, 255, 255, 0.03);
    }

    .صف-تواصل .تسمية-تواصل {
      margin-bottom: 0;
      flex-shrink: 0;
      min-width: 4.5rem;
    }

    .صف-تواصل .قيمة-تواصل {
      text-align: end;
      width: auto;
    }

    .قسم {
      margin: 1rem 0;
      border: 1px solid var(--حدود);
      border-radius: 20px;
      padding: 1.4rem;
      background: linear-gradient(160deg, rgba(255, 255, 255, 0.045), rgba(255, 255, 255, 0.018));
    }

    .رأس-قسم {
      display: flex;
      justify-content: space-between;
      align-items: end;
      gap: 1rem;
      margin-bottom: 1rem;
    }

    h2 {
      font-size: clamp(1.3rem, 2vw, 1.75rem);
    }

    .محتوى-من-أنا {
      display: grid;
      gap: 1.1rem;
    }

    .نص-من-أنا {
      color: var(--نص-هادئ);
      line-height: 1.9;
      font-size: clamp(0.98rem, 1.1vw, 1.05rem);
      max-width: 780px;
    }

    .نقاط-من-أنا {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(210px, 1fr));
      gap: 0.75rem;
    }

    .نقطة-من-أنا {
      border: 1px solid var(--حدود);
      border-radius: 14px;
      padding: 0.9rem 1rem;
      background: rgba(255, 255, 255, 0.02);
    }

    .نقطة-من-أنا strong {
      display: block;
      color: #e8efff;
      margin-bottom: 0.35rem;
      font-size: 0.95rem;
      font-weight: 700;
    }

    .نقطة-من-أنا span {
      color: var(--نص-هادئ);
      font-size: 0.9rem;
      line-height: 1.75;
    }

    .نص-هادئ {
      color: var(--نص-هادئ);
    }

    .شبكة {
      display: grid;
      gap: 1rem;
      grid-template-columns: repeat(auto-fit, minmax(230px, 1fr));
    }

    .بطاقة {
      border: 1px solid var(--حدود);
      border-radius: 16px;
      overflow: hidden;
      background: var(--لوحة);
      transition: transform 0.35s ease, border-color 0.35s ease, box-shadow 0.35s ease;
    }

    .بطاقة:hover {
      transform: translateY(-4px);
      border-color: rgba(124, 240, 210, 0.4);
      box-shadow: 0 14px 35px rgba(10, 16, 30, 0.38);
    }

    .صورة-رمزية {
      height: 160px;
      background-size: cover;
      background-position: center;
      position: relative;
      overflow: hidden;
    }

    .صورة-رمزية::after {
      content: "";
      position: absolute;
      inset: 0;
      background: linear-gradient(180deg, transparent 30%, rgba(9, 12, 20, 0.72) 100%);
    }

    .محتوى-بطاقة {
      padding: 1rem;
    }

    .محتوى-بطاقة h3 {
      margin-bottom: 0.4rem;
      font-size: 1.08rem;
    }

    .إحصاءات {
      display: grid;
      gap: 1rem;
      grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
      margin-top: 1rem;
    }

    .رقم {
      border: 1px solid var(--حدود);
      border-radius: 14px;
      padding: 1rem;
      background: var(--سطح);
      text-align: center;
    }

    .رقم strong {
      display: block;
      font-size: 1.6rem;
      line-height: 1.2;
      margin-bottom: 0.2rem;
      color: #dff7ff;
    }

    .سؤال {
      border-top: 1px solid var(--حدود);
      padding: 0.95rem 0;
    }

    .سؤال:first-of-type {
      border-top: none;
    }

    .سؤال h3 {
      margin-bottom: 0.35rem;
      font-size: 1.03rem;
      color: #e8efff;
    }

    .معرض-صور {
      display: flex;
      flex-wrap: wrap;
      gap: 0.8rem;
      justify-content: center;
    }

    .معرض-صور a {
      width: min(32%, 220px);
      min-width: 180px;
      border: 1px solid var(--حدود);
      border-radius: 10px;
      overflow: hidden;
      transition: transform 0.25s ease, box-shadow 0.25s ease;
    }

    .معرض-صور a:hover {
      transform: translateY(-3px);
      box-shadow: 0 12px 24px rgba(0, 0, 0, 0.28);
    }

    .معرض-صور img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      display: block;
    }

    .شبكة-فيديو {
      display: grid;
      gap: 1rem;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    }

    .بطاقة-فيديو {
      border: 1px solid var(--حدود);
      border-radius: 18px;
      overflow: hidden;
      background: linear-gradient(160deg, rgba(255, 255, 255, 0.04), rgba(255, 255, 255, 0.015));
      box-shadow: 0 18px 40px rgba(3, 8, 20, 0.35);
    }

    .بطاقة-فيديو video {
      width: 100%;
      aspect-ratio: 16 / 9;
      display: block;
      background: #000;
      border-bottom: 1px solid var(--حدود);
    }

    .عنوان-فيديو {
      padding: 0.85rem 1rem;
      color: #d7e3ff;
      font-size: 0.95rem;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 0.8rem;
    }

    .شارة-فيديو {
      font-size: 0.8rem;
      color: #d7e3ff;
      border: 1px solid var(--حدود);
      border-radius: 999px;
      padding: 0.18rem 0.55rem;
      background: rgba(255, 255, 255, 0.04);
    }

    .تبويبات {
      display: flex;
      flex-wrap: wrap;
      gap: 0.6rem;
      margin-bottom: 0.9rem;
    }

    .زر-تبويب {
      background: rgba(255, 255, 255, 0.03);
      color: var(--نص-هادئ);
      border: 1px solid var(--حدود);
      border-radius: 10px;
      padding: 0.55rem 0.9rem;
      cursor: pointer;
      transition: 0.2s ease;
      font: inherit;
    }

    .زر-تبويب:hover {
      color: var(--نص);
      background: rgba(255, 255, 255, 0.08);
    }

    .زر-تبويب.نشط {
      color: #071021;
      border-color: transparent;
      background: linear-gradient(135deg, var(--توهج), var(--توهج-ثان));
      font-weight: 700;
    }

    .لوحات-تبويب {
      border: 1px solid var(--حدود);
      border-radius: 14px;
      overflow: hidden;
      background: rgba(255, 255, 255, 0.02);
    }

    .لوحة-تبويب {
      display: none;
    }

    .لوحة-تبويب.نشط {
      display: block;
    }

    .لوحة-تبويب a {
      display: block;
    }

    .لوحة-تبويب img {
      width: 100%;
      display: block;
      max-height: 620px;
      object-fit: cover;
    }

    footer {
      text-align: center;
      padding: 1.5rem 0 2.4rem;
      color: var(--نص-هادئ);
      font-size: 0.95rem;
    }

    .إظهار {
      opacity: 0;
      transform: translateY(18px);
      transition: opacity 0.7s ease, transform 0.7s ease;
    }

    .إظهار.ظهر {
      opacity: 1;
      transform: translateY(0);
    }

    @keyframes تنفس {
      0%, 100% { transform: scale(1) translateY(0); }
      50% { transform: scale(1.08) translateY(12px); }
    }

    @media (max-width: 700px) {
      .شريط-داخلي {
        min-height: 52px;
        padding: 0.4rem 0.55rem;
      }

      .رابط {
        padding: 0.4rem 0.7rem;
        font-size: 0.9rem;
        white-space: nowrap;
      }

      .بطل {
        padding-top: 3.6rem;
      }

      .قسم {
        padding: 1.1rem;
      }

      .بيانات-تواصل {
        grid-template-columns: 1fr;
      }

      .لوحة-تواصل {
        max-width: 100%;
        padding: 1rem;
      }

      .صف-تواصل {
        flex-direction: column;
        align-items: flex-start;
        gap: 0.35rem;
      }

      .صف-تواصل .قيمة-تواصل {
        text-align: start;
        width: 100%;
      }

      .واتساب-عائم {
        left: 1rem;
        bottom: 1rem;
        width: 54px;
        height: 54px;
      }

      .واتساب-عائم svg {
        width: 28px;
        height: 28px;
      }
    }
  </style>
</head>
<body>
  <div class="وهج-خلفي"></div>

  <header class="شريط">
    <div class="شريط-داخلي">
      <nav class="روابط">
        <a class="رابط" href="#من-أنا">من أنا</a>
        <a class="رابط" href="#معرض-الصور">معرض الصور</a>
        <a class="رابط" href="#معرض-الفيديو">معرض الفيديو</a>
        <a class="رابط" href="#إعلانات-المواقع">إعلانات المواقع</a>
        <a class="رابط" href="#التواصل">التواصل</a>
      </nav>
    </div>
  </header>

  <main class="حاوية">
    <section class="بطل إظهار">
      <p class="شارة">مصمم جرافيك | هويات بصرية ومنتجات</p>
      <h1>ماجد مسعد العمراني</h1>
      <p class="عنوان-فرعي">أصنع حلولاً بصرية ترفع قيمة العلامة وتترك انطباعاً احترافياً.</p>
      <p class="وصف-بطل">
        أقدّم خدمات تصميم متخصصة في الهويات البصرية، المطبوعات، الهدايا الدعائية، وتصميم المنتجات — من الفكرة إلى تنفيذ بصري متقن يخدم أهداف العمل والتسويق.
      </p>
      <p class="نص-مساعد">متاح للتعاون مع الشركات والأفراد في جدة وداخل المملكة.</p>
      <div class="تخصصات-بطل">
        <span>هوية بصرية</span>
        <span>مطبوعات</span>
        <span>هدايا دعائية</span>
        <span>تصميم منتجات</span>
      </div>
      <div class="بيانات-تواصل">
        <div class="عنصر-تواصل">
          <span class="تسمية-تواصل">الموقع</span>
          <span class="قيمة-تواصل">جدة، المملكة العربية السعودية</span>
        </div>
        <div class="عنصر-تواصل">
          <span class="تسمية-تواصل">الجوال</span>
          <a class="قيمة-تواصل رابط-تواصل" href="https://wa.me/966572469285" target="_blank" rel="noreferrer">+966 57 246 9285</a>
        </div>
      </div>
      <div class="أزرار">
        <a class="زر زر-أساسي" href="#معرض-الصور">استعرض الملف</a>
        <a class="زر زر-ثانوي" _blank href="https://wa.me/966572469285">اطلب خدمتك الآن</a>
      </div>
    </section>

    <section id="من-أنا" class="قسم إظهار">
      <div class="رأس-قسم">
        <h2>من أنا</h2>
        <p class="نص-هادئ">شغف بالتصميم، وخبرة تقود كل تفصيلة</p>
      </div>
      <div class="محتوى-من-أنا">
        <p class="نص-من-أنا">
          مصمم جرافيك ومنتجات، أمتلك رؤية إبداعية وخبرة فنية تمتد من التصميم ثنائي الأبعاد إلى عوالم التصميم ثلاثي الأبعاد. أعمل على تحويل الأفكار إلى مخرجات بصرية دقيقة تخدم العلامة التجارية وتدعم أهداف التسويق والعرض.
        </p>
        <p class="نص-من-أنا">
          أواكب أحدث تقنيات الذكاء الاصطناعي في ابتكار وتطوير المحتوى البصري، مع التركيز على الجودة، الوضوح، والاتساق في كل مشروع.
        </p>
        <div class="نقاط-من-أنا">
          <article class="نقطة-من-أنا">
            <strong>تخصصاتي</strong>
            <span>هويات بصرية، مطبوعات، هدايا دعائية، وتصميم منتجات.</span>
          </article>
          <article class="نقطة-من-أنا">
            <strong>أسلوب العمل</strong>
            <span>فهم احتياج العميل أولاً، ثم تنفيذ بصري متقن يلائم هوية المشروع.</span>
          </article>
          <article class="نقطة-من-أنا">
            <strong>قيمة التعاون</strong>
            <span>حلول عملية قابلة للتطبيق، بجودة عالية ونتائج واضحة.</span>
          </article>
        </div>
      </div>
    </section>


    <section id="معرض-الصور" class="قسم إظهار">
      <div class="رأس-قسم">
        <h2>معرض الصور</h2>
        
      </div>
      <div class="معرض-صور">
        <a target="_blank" rel="noopener noreferrer" href="https://private-user-images.githubusercontent.com/299589126/616941531-2ce3a7e4-e59e-4add-82b3-cc33b11008e2.jpg?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3ODM1NDM1NjgsIm5iZiI6MTc4MzU0MzI2OCwicGF0aCI6Ii8yOTk1ODkxMjYvNjE2OTQxNTMxLTJjZTNhN2U0LWU1OWUtNGFkZC04MmIzLWNjMzNiMTEwMDhlMi5qcGc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjYwNzA4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI2MDcwOFQyMDQxMDhaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT0xNzUzNWViMDhhNTZjYjJkMDQ5MDlkODUxZGZhZmE4NjVlODFlZmI3OWNiYTY0YjYzYzljYzRiZGZlMGViM2JiJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZyZXNwb25zZS1jb250ZW50LXR5cGU9aW1hZ2UlMkZqcGVnIn0.aWYK9XW3iZbsJp1VGCVoYLmEq0J7PMQzy-jLyrG5aIo"><img alt="" src="https://private-user-images.githubusercontent.com/299589126/616941531-2ce3a7e4-e59e-4add-82b3-cc33b11008e2.jpg?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3ODM1NDM1NjgsIm5iZiI6MTc4MzU0MzI2OCwicGF0aCI6Ii8yOTk1ODkxMjYvNjE2OTQxNTMxLTJjZTNhN2U0LWU1OWUtNGFkZC04MmIzLWNjMzNiMTEwMDhlMi5qcGc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjYwNzA4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI2MDcwOFQyMDQxMDhaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT0xNzUzNWViMDhhNTZjYjJkMDQ5MDlkODUxZGZhZmE4NjVlODFlZmI3OWNiYTY0YjYzYzljYzRiZGZlMGViM2JiJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZyZXNwb25zZS1jb250ZW50LXR5cGU9aW1hZ2UlMkZqcGVnIn0.aWYK9XW3iZbsJp1VGCVoYLmEq0J7PMQzy-jLyrG5aIo" /></a>
        <a target="_blank" rel="noopener noreferrer" href="https://private-user-images.githubusercontent.com/299589126/616941523-9970af00-61c1-4c75-be37-0b90a2c3767d.jpg?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3ODM1NDM1NjgsIm5iZiI6MTc4MzU0MzI2OCwicGF0aCI6Ii8yOTk1ODkxMjYvNjE2OTQxNTIzLTk5NzBhZjAwLTYxYzEtNGM3NS1iZTM3LTBiOTBhMmMzNzY3ZC5qcGc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjYwNzA4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI2MDcwOFQyMDQxMDhaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1jMjRlNWI2MmZmMTg3MjdhZmI3NjFkYTMxZWQ5YjVkNGFjNDlmMDM3YzFlOTY3N2YzMjFmMDM2YTViZTg0OTkyJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZyZXNwb25zZS1jb250ZW50LXR5cGU9aW1hZ2UlMkZqcGVnIn0.9RWXNMAM5xniHo0tEuTYAzO888aLSNE4UdGrH0Q593w"><img alt="" src="https://private-user-images.githubusercontent.com/299589126/616941523-9970af00-61c1-4c75-be37-0b90a2c3767d.jpg?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3ODM1NDM1NjgsIm5iZiI6MTc4MzU0MzI2OCwicGF0aCI6Ii8yOTk1ODkxMjYvNjE2OTQxNTIzLTk5NzBhZjAwLTYxYzEtNGM3NS1iZTM3LTBiOTBhMmMzNzY3ZC5qcGc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjYwNzA4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI2MDcwOFQyMDQxMDhaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1jMjRlNWI2MmZmMTg3MjdhZmI3NjFkYTMxZWQ5YjVkNGFjNDlmMDM3YzFlOTY3N2YzMjFmMDM2YTViZTg0OTkyJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZyZXNwb25zZS1jb250ZW50LXR5cGU9aW1hZ2UlMkZqcGVnIn0.9RWXNMAM5xniHo0tEuTYAzO888aLSNE4UdGrH0Q593w" /></a>
        <a target="_blank" rel="noopener noreferrer" href="https://private-user-images.githubusercontent.com/299589126/616941516-60a11888-b911-4b28-a583-f731e86f1784.jpg?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3ODM1NDM1NjgsIm5iZiI6MTc4MzU0MzI2OCwicGF0aCI6Ii8yOTk1ODkxMjYvNjE2OTQxNTE2LTYwYTExODg4LWI5MTEtNGIyOC1hNTgzLWY3MzFlODZmMTc4NC5qcGc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjYwNzA4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI2MDcwOFQyMDQxMDhaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT0wNmJlZGZkYzIxMjdiYTVjMmJlN2U2NmZlMGQ0YjVjZDAwMDg4NjExNzcyMDE3OTQ2ZGQ3MmRmMTI3ZDU1MDZhJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZyZXNwb25zZS1jb250ZW50LXR5cGU9aW1hZ2UlMkZqcGVnIn0.7bzIVStzPFJ5RxZZ3-fm-MnotTdqQaGncQKKDLqoWao"><img alt="" src="https://private-user-images.githubusercontent.com/299589126/616941516-60a11888-b911-4b28-a583-f731e86f1784.jpg?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3ODM1NDM1NjgsIm5iZiI6MTc4MzU0MzI2OCwicGF0aCI6Ii8yOTk1ODkxMjYvNjE2OTQxNTE2LTYwYTExODg4LWI5MTEtNGIyOC1hNTgzLWY3MzFlODZmMTc4NC5qcGc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjYwNzA4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI2MDcwOFQyMDQxMDhaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT0wNmJlZGZkYzIxMjdiYTVjMmJlN2U2NmZlMGQ0YjVjZDAwMDg4NjExNzcyMDE3OTQ2ZGQ3MmRmMTI3ZDU1MDZhJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZyZXNwb25zZS1jb250ZW50LXR5cGU9aW1hZ2UlMkZqcGVnIn0.7bzIVStzPFJ5RxZZ3-fm-MnotTdqQaGncQKKDLqoWao" /></a>
        <a target="_blank" rel="noopener noreferrer" href="https://private-user-images.githubusercontent.com/299589126/616941507-c700e82d-6e32-4ac1-8490-4324b8662d0b.jpg?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3ODM1NDM1NjgsIm5iZiI6MTc4MzU0MzI2OCwicGF0aCI6Ii8yOTk1ODkxMjYvNjE2OTQxNTA3LWM3MDBlODJkLTZlMzItNGFjMS04NDkwLTQzMjRiODY2MmQwYi5qcGc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjYwNzA4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI2MDcwOFQyMDQxMDhaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT03YzI1ZjA5N2Y3MzJjNDI4NDU0MzU1YjlmZTFmZmU0Yjc4ZjkzYjc5ZDcyZGE2ZWZjNzJjZWZiMTBkZTU0MmE1JlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZyZXNwb25zZS1jb250ZW50LXR5cGU9aW1hZ2UlMkZqcGVnIn0.sGH4ndnPvAGBx70Eb4XpfecQmEgbjgQhKkF2cRnDLn0"><img alt="" src="https://private-user-images.githubusercontent.com/299589126/616941507-c700e82d-6e32-4ac1-8490-4324b8662d0b.jpg?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3ODM1NDM1NjgsIm5iZiI6MTc4MzU0MzI2OCwicGF0aCI6Ii8yOTk1ODkxMjYvNjE2OTQxNTA3LWM3MDBlODJkLTZlMzItNGFjMS04NDkwLTQzMjRiODY2MmQwYi5qcGc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjYwNzA4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI2MDcwOFQyMDQxMDhaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT03YzI1ZjA5N2Y3MzJjNDI4NDU0MzU1YjlmZTFmZmU0Yjc4ZjkzYjc5ZDcyZGE2ZWZjNzJjZWZiMTBkZTU0MmE1JlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZyZXNwb25zZS1jb250ZW50LXR5cGU9aW1hZ2UlMkZqcGVnIn0.sGH4ndnPvAGBx70Eb4XpfecQmEgbjgQhKkF2cRnDLn0" /></a>
        <a target="_blank" rel="noopener noreferrer" href="https://private-user-images.githubusercontent.com/299589126/616941498-be02574d-a530-43f3-9596-8b97a249dc37.jpg?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3ODM1NDM1NjgsIm5iZiI6MTc4MzU0MzI2OCwicGF0aCI6Ii8yOTk1ODkxMjYvNjE2OTQxNDk4LWJlMDI1NzRkLWE1MzAtNDNmMy05NTk2LThiOTdhMjQ5ZGMzNy5qcGc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjYwNzA4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI2MDcwOFQyMDQxMDhaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT02ZTc5YTVmNTdiZTA2OGFkMzA4OGQ3MGQ1NjJiOTAyODcyMjk0ZjIyMTcyMTgwYTY5YTk1YWM5ZDA2YmMxNDRiJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZyZXNwb25zZS1jb250ZW50LXR5cGU9aW1hZ2UlMkZqcGVnIn0.ZPFBauMMvQ9YOiZ16uxQIsy_cKRz0MfqbNJqbHzAco0"><img alt="" src="https://private-user-images.githubusercontent.com/299589126/616941498-be02574d-a530-43f3-9596-8b97a249dc37.jpg?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3ODM1NDM1NjgsIm5iZiI6MTc4MzU0MzI2OCwicGF0aCI6Ii8yOTk1ODkxMjYvNjE2OTQxNDk4LWJlMDI1NzRkLWE1MzAtNDNmMy05NTk2LThiOTdhMjQ5ZGMzNy5qcGc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjYwNzA4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI2MDcwOFQyMDQxMDhaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT02ZTc5YTVmNTdiZTA2OGFkMzA4OGQ3MGQ1NjJiOTAyODcyMjk0ZjIyMTcyMTgwYTY5YTk1YWM5ZDA2YmMxNDRiJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZyZXNwb25zZS1jb250ZW50LXR5cGU9aW1hZ2UlMkZqcGVnIn0.ZPFBauMMvQ9YOiZ16uxQIsy_cKRz0MfqbNJqbHzAco0" /></a>
        <a target="_blank" rel="noopener noreferrer" href="https://private-user-images.githubusercontent.com/299589126/616941493-27309919-65a0-47c3-98bd-7b056c1f2085.jpg?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3ODM1NDM1NjgsIm5iZiI6MTc4MzU0MzI2OCwicGF0aCI6Ii8yOTk1ODkxMjYvNjE2OTQxNDkzLTI3MzA5OTE5LTY1YTAtNDdjMy05OGJkLTdiMDU2YzFmMjA4NS5qcGc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjYwNzA4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI2MDcwOFQyMDQxMDhaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT0zZmE2ODc4MzJjNTZhMjk0NTc4MGUxZmI3Y2U0YWIxYTdhNmI5ZWMzNzQ2YzU0YTg4NTUxY2NjODliYzFmY2NhJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZyZXNwb25zZS1jb250ZW50LXR5cGU9aW1hZ2UlMkZqcGVnIn0.7SbTk_SFtsZ_vyMS7r638L_ySTCpKvaZnh3RN73wqs0"><img alt="" src="https://private-user-images.githubusercontent.com/299589126/616941493-27309919-65a0-47c3-98bd-7b056c1f2085.jpg?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3ODM1NDM1NjgsIm5iZiI6MTc4MzU0MzI2OCwicGF0aCI6Ii8yOTk1ODkxMjYvNjE2OTQxNDkzLTI3MzA5OTE5LTY1YTAtNDdjMy05OGJkLTdiMDU2YzFmMjA4NS5qcGc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjYwNzA4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI2MDcwOFQyMDQxMDhaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT0zZmE2ODc4MzJjNTZhMjk0NTc4MGUxZmI3Y2U0YWIxYTdhNmI5ZWMzNzQ2YzU0YTg4NTUxY2NjODliYzFmY2NhJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZyZXNwb25zZS1jb250ZW50LXR5cGU9aW1hZ2UlMkZqcGVnIn0.7SbTk_SFtsZ_vyMS7r638L_ySTCpKvaZnh3RN73wqs0" /></a>
      </div>
  
    </section>

    <section id="معرض-الفيديو" class="قسم إظهار">
      <div class="رأس-قسم">
        <h2>معرض الفيديو</h2>
        
      </div>
      <div class="شبكة-فيديو">
        <article class="بطاقة-فيديو">
          <video controls playsinline preload="metadata" controlslist="nodownload noplaybackrate">
            <source src="https://private-user-images.githubusercontent.com/299589126/616947114-c245f1df-25f2-44dd-bc40-d960bedb1e35.mp4?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3ODM1NDM1NjgsIm5iZiI6MTc4MzU0MzI2OCwicGF0aCI6Ii8yOTk1ODkxMjYvNjE2OTQ3MTE0LWMyNDVmMWRmLTI1ZjItNDRkZC1iYzQwLWQ5NjBiZWRiMWUzNS5tcDQ_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjYwNzA4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI2MDcwOFQyMDQxMDhaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT01ZWI1N2U2OWYxZTMzZjk2MmY2Y2NkYTk1MzZiYzQwN2JiMDE2Y2Q1OTQ5Y2ZmMWVmZTMzZWJjOWU2YTM0NTFhJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZyZXNwb25zZS1jb250ZW50LXR5cGU9dmlkZW8lMkZtcDQifQ.anwQOZNpqm9cgfE_YKruU8xcSTPpLOIIvBasi12OH8U" type="video/mp4" />
            متصفحك لا يدعم تشغيل الفيديو.
          </video>
          <p class="عنوان-فيديو">
            <span>عرض موشن احترافي - 0044.mp4</span>
            <span class="شارة-فيديو">HD</span>
          </p>
        </article>
      </div>
    </section>

    <section id="إعلانات-المواقع" class="قسم إظهار">
      <div class="رأس-قسم">
        <h2>إعلانات المواقع</h2>
        
      </div>
      <div class="تبويبات" role="tablist" aria-label="تبويبات إعلانات المواقع">
        <button class="زر-تبويب نشط" type="button" role="tab" aria-selected="true" data-tab-target="ad-1">إعلان ١</button>
        <button class="زر-تبويب" type="button" role="tab" aria-selected="false" data-tab-target="ad-2">إعلان ٢</button>
        <button class="زر-تبويب" type="button" role="tab" aria-selected="false" data-tab-target="ad-3">إعلان ٣</button>
      </div>
      <div class="لوحات-تبويب">
        <div class="لوحة-تبويب نشط" id="ad-1" role="tabpanel">
          <a target="_blank" rel="noopener noreferrer" href="https://private-user-images.githubusercontent.com/299589126/616950171-bbd363c9-2a91-4c68-9394-1ff42af4f93f.jpg?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3ODM1NDM1NjgsIm5iZiI6MTc4MzU0MzI2OCwicGF0aCI6Ii8yOTk1ODkxMjYvNjE2OTUwMTcxLWJiZDM2M2M5LTJhOTEtNGM2OC05Mzk0LTFmZjQyYWY0ZjkzZi5qcGc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjYwNzA4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI2MDcwOFQyMDQxMDhaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1kOGNiODc5NGE5NGM2YTdkNzU0Zjk5NDA2ODFkMWQyNjY0ZWNiYTRiMTVkMTJkOTk5M2I4NjcxMDgwOWI4MmMxJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZyZXNwb25zZS1jb250ZW50LXR5cGU9aW1hZ2UlMkZqcGVnIn0.b4Q4QcOLH7aAVZHPhG6ApmFhSsZ2l5WNKmd6Cvlqd3Q"><img alt="إعلان موقع 1" src="https://private-user-images.githubusercontent.com/299589126/616950171-bbd363c9-2a91-4c68-9394-1ff42af4f93f.jpg?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3ODM1NDM1NjgsIm5iZiI6MTc4MzU0MzI2OCwicGF0aCI6Ii8yOTk1ODkxMjYvNjE2OTUwMTcxLWJiZDM2M2M5LTJhOTEtNGM2OC05Mzk0LTFmZjQyYWY0ZjkzZi5qcGc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjYwNzA4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI2MDcwOFQyMDQxMDhaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1kOGNiODc5NGE5NGM2YTdkNzU0Zjk5NDA2ODFkMWQyNjY0ZWNiYTRiMTVkMTJkOTk5M2I4NjcxMDgwOWI4MmMxJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZyZXNwb25zZS1jb250ZW50LXR5cGU9aW1hZ2UlMkZqcGVnIn0.b4Q4QcOLH7aAVZHPhG6ApmFhSsZ2l5WNKmd6Cvlqd3Q" /></a>
        </div>
        <div class="لوحة-تبويب" id="ad-2" role="tabpanel">
          <a target="_blank" rel="noopener noreferrer" href="https://private-user-images.githubusercontent.com/299589126/616950168-0ae16154-bfec-43ce-8796-af6c59c5bb63.jpg?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3ODM1NDM1NjgsIm5iZiI6MTc4MzU0MzI2OCwicGF0aCI6Ii8yOTk1ODkxMjYvNjE2OTUwMTY4LTBhZTE2MTU0LWJmZWMtNDNjZS04Nzk2LWFmNmM1OWM1YmI2My5qcGc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjYwNzA4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI2MDcwOFQyMDQxMDhaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1iMjAwZDI5Y2E1M2ZkZmFlMWJjNWI2NTc4ZTk1NTg1NWRiZTE2MDdhMjE0M2Y1NjAzYTMyNmVhM2ZmYTQ3NmNkJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZyZXNwb25zZS1jb250ZW50LXR5cGU9aW1hZ2UlMkZqcGVnIn0.shbo8fsfiihhK0Hvw4VyO61AzBXs53NuTCwCvlD1_QU"><img alt="إعلان موقع 2" src="https://private-user-images.githubusercontent.com/299589126/616950168-0ae16154-bfec-43ce-8796-af6c59c5bb63.jpg?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3ODM1NDM1NjgsIm5iZiI6MTc4MzU0MzI2OCwicGF0aCI6Ii8yOTk1ODkxMjYvNjE2OTUwMTY4LTBhZTE2MTU0LWJmZWMtNDNjZS04Nzk2LWFmNmM1OWM1YmI2My5qcGc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjYwNzA4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI2MDcwOFQyMDQxMDhaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1iMjAwZDI5Y2E1M2ZkZmFlMWJjNWI2NTc4ZTk1NTg1NWRiZTE2MDdhMjE0M2Y1NjAzYTMyNmVhM2ZmYTQ3NmNkJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZyZXNwb25zZS1jb250ZW50LXR5cGU9aW1hZ2UlMkZqcGVnIn0.shbo8fsfiihhK0Hvw4VyO61AzBXs53NuTCwCvlD1_QU" /></a>
        </div>
        <div class="لوحة-تبويب" id="ad-3" role="tabpanel">
          <a target="_blank" rel="noopener noreferrer" href="https://private-user-images.githubusercontent.com/299589126/616950164-f432e4e0-f827-438c-9b3d-1dfaef6e8c51.jpg?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3ODM1NDM1NjgsIm5iZiI6MTc4MzU0MzI2OCwicGF0aCI6Ii8yOTk1ODkxMjYvNjE2OTUwMTY0LWY0MzJlNGUwLWY4MjctNDM4Yy05YjNkLTFkZmFlZjZlOGM1MS5qcGc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjYwNzA4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI2MDcwOFQyMDQxMDhaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1jM2E0Y2UzYTQyNzg3Y2QzNTc0ODQyYmE2ZjUxMTRlZTBkZTc4ZjY1ZjI0YzQ1ZDNjNTg1NTE4YmI0ZGY4ZmZlJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZyZXNwb25zZS1jb250ZW50LXR5cGU9aW1hZ2UlMkZqcGVnIn0.JQeYvMUEK-qMKtBI9oWhxgFIObwlqcrzvLWlvC1Uzk0"><img alt="إعلان موقع 3" src="https://private-user-images.githubusercontent.com/299589126/616950164-f432e4e0-f827-438c-9b3d-1dfaef6e8c51.jpg?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3ODM1NDM1NjgsIm5iZiI6MTc4MzU0MzI2OCwicGF0aCI6Ii8yOTk1ODkxMjYvNjE2OTUwMTY0LWY0MzJlNGUwLWY4MjctNDM4Yy05YjNkLTFkZmFlZjZlOGM1MS5qcGc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjYwNzA4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI2MDcwOFQyMDQxMDhaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1jM2E0Y2UzYTQyNzg3Y2QzNTc0ODQyYmE2ZjUxMTRlZTBkZTc4ZjY1ZjI0YzQ1ZDNjNTg1NTE4YmI0ZGY4ZmZlJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZyZXNwb25zZS1jb250ZW50LXR5cGU9aW1hZ2UlMkZqcGVnIn0.JQeYvMUEK-qMKtBI9oWhxgFIObwlqcrzvLWlvC1Uzk0" /></a>
        </div>
      </div>
    </section>


    <section id="التواصل" class="قسم إظهار">
      <div class="رأس-قسم">
        <h2>التواصل</h2>
        <p class="نص-هادئ">يسعدني تواصلك لبدء مشروعك القادم</p>
      </div>
      <div class="لوحة-تواصل">
        <div class="صف-تواصل">
          <span class="تسمية-تواصل">الموقع</span>
          <span class="قيمة-تواصل">جدة، المملكة العربية السعودية</span>
        </div>
        <div class="صف-تواصل">
          <span class="تسمية-تواصل">الجوال</span>
          <a class="قيمة-تواصل رابط-تواصل" href="https://wa.me/966572469285" target="_blank" rel="noreferrer">+966 57 246 9285</a>
        </div>
      </div>
    </section>
  </main>

  <a
    class="واتساب-عائم"
    href="https://wa.me/966572469285"
    target="_blank"
    rel="noreferrer"
    aria-label="تواصل عبر واتساب"
  >
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" aria-hidden="true">
      <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.435 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/>
    </svg>
  </a>

  <footer>
    <p>© <span id="السنة"></span> ماجد مسعد العمراني - جميع الحقوق محفوظة</p>
  </footer>

  <script>
    document.getElementById("السنة").textContent = new Date().getFullYear();

    const بدائل_الصور = [
      "https://images.unsplash.com/photo-1517048676732-d65bc937f952?auto=format&fit=crop&w=1400&q=80",
      "https://images.unsplash.com/photo-1505691938895-1758d7feb511?auto=format&fit=crop&w=1400&q=80",
      "https://images.unsplash.com/photo-1497366754035-f200968a6e72?auto=format&fit=crop&w=1400&q=80",
      "https://images.unsplash.com/photo-1494526585095-c41746248156?auto=format&fit=crop&w=1400&q=80",
      "https://images.unsplash.com/photo-1460317442991-0ec209397118?auto=format&fit=crop&w=1400&q=80"
    ];

    let مؤشر_بديل = 0;
    const صور = document.querySelectorAll('img[src*="private-user-images"]');
    صور.forEach((صورة) => {
      const رابط_بديل = بدائل_الصور[مؤشر_بديل % بدائل_الصور.length];
      مؤشر_بديل += 1;

      صورة.addEventListener("error", () => {
        صورة.src = رابط_بديل;
        const حاوية_الرابط = صورة.closest("a");
        if (حاوية_الرابط) {
          حاوية_الرابط.href = رابط_بديل;
        }
      });

      // إذا انتهت صلاحية الرابط قبل التحميل، نطبق البديل مباشرة.
      if (صورة.complete && صورة.naturalWidth === 0) {
        صورة.src = رابط_بديل;
        const حاوية_الرابط = صورة.closest("a");
        if (حاوية_الرابط) {
          حاوية_الرابط.href = رابط_بديل;
        }
      }
    });

    const فيديوهات = document.querySelectorAll('video source[src*="private-user-images"]');
    فيديوهات.forEach((مصدر) => {
      مصدر.addEventListener("error", () => {
        مصدر.src = "https://interactive-examples.mdn.mozilla.net/media/cc0-videos/flower.mp4";
        const فيديو = مصدر.closest("video");
        if (فيديو) فيديو.load();
      });
    });

    const روابط_داخلية = document.querySelectorAll('a[href^="#"]');
    روابط_داخلية.forEach((رابط) => {
      رابط.addEventListener("click", (حدث) => {
        const المعرف = رابط.getAttribute("href");
        if (!المعرف || المعرف === "#") return;

        const القسم = document.querySelector(المعرف);
        if (!القسم) return;

        حدث.preventDefault();
        const الشريط = document.querySelector(".شريط");
        const ازاحة = الشريط ? الشريط.offsetHeight + 28 : 28;
        const موضع = القسم.getBoundingClientRect().top + window.scrollY - ازاحة;

        window.scrollTo({
          top: موضع,
          behavior: "smooth"
        });
      });
    });

    const العناصر = document.querySelectorAll(".إظهار");
    const المراقب = new IntersectionObserver((entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.classList.add("ظهر");
          المراقب.unobserve(entry.target);
        }
      });
    }, { threshold: 0.2 });

    العناصر.forEach((item, index) => {
      item.style.transitionDelay = `${index * 70}ms`;
      المراقب.observe(item);
    });

    const أزرار_التبويب = document.querySelectorAll(".زر-تبويب");
    const لوحات_التبويب = document.querySelectorAll(".لوحة-تبويب");

    أزرار_التبويب.forEach((زر) => {
      زر.addEventListener("click", () => {
        const الهدف = زر.dataset.tabTarget;
        if (!الهدف) return;

        أزرار_التبويب.forEach((z) => {
          z.classList.remove("نشط");
          z.setAttribute("aria-selected", "false");
        });
        لوحات_التبويب.forEach((p) => p.classList.remove("نشط"));

        زر.classList.add("نشط");
        زر.setAttribute("aria-selected", "true");
        const لوحة = document.getElementById(الهدف);
        if (لوحة) لوحة.classList.add("نشط");
      });
    });
  </script>
</body>
</html>
