<!DOCTYPE html>
<html lang="ar">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>شركة SSC</title>
  <style>
    body {
      margin: 0;
      font-family: "Cairo", sans-serif;
      display: flex;
      background: #f4f6f9;
    }

    /* الشريط الجانبي */
    .sidebar {
      width: 220px;
      background: #1e293b;
      color: white;
      min-height: 100vh;
      padding: 20px 10px;
      box-shadow: 2px 0 5px rgba(0,0,0,0.2);
      position: fixed;
    }

    .sidebar h2 {
      text-align: center;
      margin-bottom: 30px;
    }

    .sidebar a {
      display: block;
      color: #cbd5e1;
      padding: 12px;
      text-decoration: none;
      border-radius: 8px;
      margin: 5px 0;
      transition: background 0.3s;
    }

    .sidebar a:hover,
    .sidebar a.active {
      background: #3b82f6;
      color: #fff;
    }

    /* المحتوى */
    .content {
      margin-left: 240px;
      padding: 30px;
      flex: 1;
    }

    section {
      display: none;
      animation: fade 0.5s ease-in-out;
    }

    section.active {
      display: block;
    }

    @keyframes fade {
      from {opacity: 0;}
      to {opacity: 1;}
    }

    h1 {
      color: #1e293b;
    }
  </style>
</head>
<body>
  <!-- الشريط الجانبي -->
  <div class="sidebar">
    <h2>SSC</h2>
    <a href="#" class="menu-link active" data-target="home">🏠 الرئيسية</a>
    <a href="#" class="menu-link" data-target="clients">👥 العملاء</a>
    <a href="#" class="menu-link" data-target="employees">👨‍💼 الموظفين</a>
    <a href="#" class="menu-link" data-target="accounting">💰 المحاسبة</a>
    <a href="#" class="menu-link" data-target="about">ℹ️ عن الشركة</a>
  </div>

  <!-- المحتوى -->
  <div class="content">
    <section id="home" class="active">
      <h1>مرحباً بك في شركة SSC</h1>
      <p>نحن شركة رائدة في تقديم الحلول والخدمات المتكاملة.</p>
    </section>

    <section id="clients">
      <h1>عملاؤنا</h1>
      <ul>
        <li>شركة A</li>
        <li>شركة B</li>
        <li>مؤسسة C</li>
      </ul>
    </section>

    <section id="employees">
      <h1>الموظفون</h1>
      <ul>
        <li>محمد - مدير المشاريع</li>
        <li>سارة - قسم التسويق</li>
        <li>علي - قسم المحاسبة</li>
      </ul>
    </section>

    <section id="accounting">
      <h1>قسم المحاسبة</h1>
      <p>إدارة الأموال والمعاملات المالية بدقة واحترافية.</p>
    </section>

    <section id="about">
      <h1>من نحن</h1>
      <p>شركة SSC تأسست لتقديم حلول مبتكرة وشاملة في مختلف المجالات.</p>
    </section>
  </div>

  <script>
    // التنقل بين الأقسام
    const links = document.querySelectorAll(".menu-link");
    const sections = document.querySelectorAll("section");

    links.forEach(link => {
      link.addEventListener("click", e => {
        e.preventDefault();

        // إزالة التفعيل من الروابط
        links.forEach(l => l.classList.remove("active"));
        link.classList.add("active");

        // إخفاء جميع الأقسام
        sections.forEach(sec => sec.classList.remove("active"));

        // عرض القسم المطلوب
        const target = document.getElementById(link.dataset.target);
        target.classList.add("active");
      });
    });
  </script>
</body>
</html>
