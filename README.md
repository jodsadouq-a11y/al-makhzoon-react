# 💎 منصة مخزوني الذكية (Al-Makhzoon Boutique & Cash Flow Platform)
> منصة سحابية وتفاعلية متكاملة لإدارة مخزون البوتيك ومتاجر الإكسسوارات والشنط والمكياج، مدمجة مع نظام التدفق النقدي (الكاش فلو) والذكاء الاصطناعي البصري (Google Gemini 3.8 Flash).

مبنية بأحدث تقنيات الويب: **React (Vite) + Tailwind CSS + Supabase Database + Vercel Deployment**.

---

## ✨ المميزات الرئيسية

1. **العملة الرسمية بالشيكل (₪):** جميع الحسابات، التكاليف، أسعار البيع، والأرباح بالـ (شيكل ₪).
2. **تصميم متجاوب 100% (Responsive):**
   - يدعم الهواتف الذكية (iOS & Android)، أجهزة التابلت والآيباد، وشاشات الحواسيب المكتبية.
   - شريط تنقل سفلي للهواتف يسهل الاستخدام بالإبهام.
   - زر التبديل الفوري بين عرض الجدول وعرض البطاقات (الكروت).
3. **الوضع الليلي (Dark Mode):** ثيم نهاري/ليلي سلس مع حفظ التفضيل تلقائياً.
4. **لوحة التدفق النقدي (Cash Flow Dashboard):**
   - متابعة الإيرادات والمبيعات (وارد 🟢) والمصاريف والمشتريات (صادر 🔴).
   - احتساب صافي النقد المتاح بالصندوق وهامش الأرباح التشغيلية %.
   - رسوم بيانية تفاعلية (Chart.js) لمقارنة الإيرادات بالمصاريف وتوزيع بنود المصاريف.
   - دفتر حركة النقدية (Cash Ledger) مع فلاتر زمنية وتصدير فوري إلى Excel CSV وطباعة كشوفات.
5. **كاميرا المسح البصري الذكي (AI Vision - Gemini 3.8 Flash):**
   - تصوير القطعة بالكاميرا واستخراج الاسم، القسم، المواصفات والأسعار التقديرية تلقائياً.
6. **أمر تجديد البضاعة للمورد:** حصر آلي للنواقص مع زر نسخ مباشر لرسالة واتساب احترافية.
7. **نظام هجين ذكي للبيانات (Hybrid Database):**
   - يدعم الاتصال المباشر بقاعدة بيانات **Supabase** (محلياً أو سحابياً).
   - يعمل تلقائياً بـ `LocalStorage` عند عدم توفر اتصال بالإنترنت أو قبل إدخال المفاتيح دون أي توقف.

---

## 🚀 البدء والتشغيل المحلي (Local Development)

### 1. تثبيت الحزم وتشغيل خادم التطوير:
```bash
# الانتقال إلى المجلد
cd al-makhzoon-react

# تثبيت التبعيات
npm install

# تشغيل خادم التطوير
npm run dev
```

افتح المتصفح على الرابط الموضح: `http://localhost:5173`.

---

## 🗄️ إعداد قاعدة بيانات Supabase المحلية (Local Supabase)

إذا كنت ترغب بتشغيل Supabase محلياً على جهازك:

1. **تشغيل Supabase محلياً باستخدام CLI:**
   ```bash
   npx supabase init
   npx supabase start
   ```
2. **تطبيق مخطط الجداول:**
   - افتح لوحة تحكم Supabase المحلية (`http://localhost:54323`).
   - توجه إلى **SQL Editor**.
   - انسخ محتوى الملف `supabase/schema.sql` والصقه ثم اضغط **Run**.
3. **ربط المتغيرات في ملف `.env`:**
   ```env
   VITE_SUPABASE_URL=http://127.0.0.1:54321
   VITE_SUPABASE_ANON_KEY=مفتاح_anon_الخاص_بك
   VITE_GEMINI_API_KEY=مفتاح_gemini_اختياري
   ```

*(ملاحظة: إذا كنت تستخدم Supabase Cloud المجاني، يمكنك نسخ نفس الـ `schema.sql` إلى مشروعك على [supabase.com](https://supabase.com) واستخدام عنوان المشروع ومفتاح anon).*

---

## 🌐 النشر على Vercel (Vercel Deployment)

المشروع مهيأ وجاهز للنشر المباشر على Vercel:

### الطريقة الأولى: عبر GitHub و Vercel Dashboard (مستحسنة)
1. قم برفع مجلد المشروع إلى مستودع جديد على GitHub:
   ```bash
   git init
   git add .
   git commit -m "Initial commit of Al-Makhzoon React platform"
   git branch -M main
   git remote add origin https://github.com/your-username/al-makhzoon.git
   git push -u origin main
   ```
2. ادخل إلى حسابك على [Vercel](https://vercel.com) واضغط **"Add New Project"**.
3. اختر المستودع من GitHub.
4. في خانة **Environment Variables** أضف المتغيرات:
   - `VITE_SUPABASE_URL`: رابط مشروع Supabase (سحابي أو سيرفرك).
   - `VITE_SUPABASE_ANON_KEY`: المفتاح العام للمشروع.
   - `VITE_GEMINI_API_KEY`: مفتاح Google Gemini (اختياري، يمكن أيضاً للمستخدم إدخاله من واجهة التطبيق).
5. اضغط **Deploy**. ستقوم Vercel ببناء المشروع ونشره خلال ثوانٍ وتزويدك برابط مباشر وسريع ومحمي بـ SSL.

### الطريقة الثانية: عبر سطر أوامر Vercel CLI
```bash
npm i -g vercel
vercel
```

---

## 📁 هيكلية مجلدات المشروع (Architecture)

```text
al-makhzoon-react/
├── .env.example              # نموذج متغيرات البيئة
├── vercel.json               # إعدادات التوجيه السحابي لـ Vercel
├── tailwind.config.js        # إعدادات التصميم والوضع الليلي
├── supabase/
│   └── schema.sql            # المخطط الكامل لقاعدة بيانات Supabase
├── src/
│   ├── main.jsx              # نقطة الانطلاق ومزودي السياق
│   ├── App.jsx               # المكون الرئيسي الجامع للواجهات
│   ├── index.css             # التنسيقات العامة والخط العربي
│   ├── lib/
│   │   ├── supabase.js       # عميل Supabase ونظام التخزين الهجين
│   │   └── inventoryUtils.js # معادلات المخزون والصلاحية
│   ├── context/
│   │   ├── ThemeContext.jsx  # إدارة الوضع الليلي
│   │   └── StoreContext.jsx  # إدارة الحالة المركزية والمؤشرات المالية
│   ├── services/
│   │   ├── geminiService.js  # خدمة الذكاء الاصطناعي البصري
│   │   └── exportService.js  # خدمات التصدير (Excel & JSON)
│   └── components/
│       ├── Header.jsx
│       ├── KPICards.jsx
│       ├── TabNavigation.jsx
│       ├── FilterBar.jsx
│       ├── ProductTable.jsx
│       ├── ProductCardGrid.jsx
│       ├── CashflowDashboard.jsx
│       ├── CashflowTable.jsx
│       ├── AnalyticsView.jsx
│       ├── LogsView.jsx
│       ├── MobileBottomNav.jsx
│       ├── modals/           # النوافذ المنبثقة
│       └── ui/Toast.jsx      # التنبيهات المنبثقة
```

---

## 🔒 حماية وخصوصية البيانات
جميع البيانات والعمليات المالية مشفرة ومحفوظة وفق معايير Row Level Security (RLS) ومطابقة للمعايير السحابية.
