# صيانة جدة VIP - دليل التشغيل والرفع على GitHub والنشر على Vercel

موقع رسمي وتفاعلي بالكامل لخدمات **صيانة جدة (Siana Jeddah VIP)**، المركز المتخصص والمعتمد في صيانة الغسالات الأوتوماتيكية والثلاجات والفريزرات في جميع أحياء جدة.

---

## 📁 هيكلية المشروع (Project Structure)

```text
├── index.html               # الصفحة الرئيسية ونموذج الحجز
├── washing-machines.html    # صفحة صيانة الغسالات الأوتوماتيكية
├── refrigerators.html       # صفحة صيانة الثلاجات والفريزرات
├── contact.html             # صفحة الاتصال والمساعد الذكي AI
├── 404.html                 # صفحة الخطأ المخصصة 404
├── vercel.json              # إعدادات Vercel للتوجيه النظيف والتخزين المؤقت
├── package.json             # تعريف المشروع وأوامر التشغيل والبناء
├── server.js                # خادم محلي خفيف للتجربة والتطوير
├── upload_to_github.js      # أداة برمجية لرفع الملفات إلى GitHub تلقائياً
├── robots.txt               # إعدادات محركات البحث
├── sitemap.xml              # خريطة الموقع
└── assets/
    └── images/              # جميع الصور والشعارات والأيقونات
```

---

## 🚀 الطريقة الأولى: النشر المباشر على Vercel عبر GitHub (الموصى بها)

### 1. رفع المشروع إلى GitHub:
يمكنك استخدام أي من الطرق التالية:

#### خيار أ: عبر واجهة موقع GitHub (الأسهل بدون أوامر):
1. افتح [GitHub.com](https://github.com) وأنشئ مستودعاً جديداً (New Repository)، سمّه مثلاً `siana-jeddah`.
2. اضغط على **"uploading an existing file"**.
3. اسحب جميع ملفات هذا المجلد وأفلتها في المتصفح، ثم اضغط **Commit changes**.

#### خيار ب: عبر أوامر Git:
```bash
git init
git add .
git commit -m "Deploy Siana Jeddah VIP Website"
git branch -M main
git remote add origin https://github.com/<YOUR_USERNAME>/siana-jeddah.git
git push -u origin main
```

#### خيار ج: عبر أداة `upload_to_github.js`:
```bash
node upload_to_github.js <GITHUB_TOKEN> <REPO_NAME> <GITHUB_USERNAME>
```

---

### 2. الربط والنشر على Vercel:
1. اذهب إلى [Vercel Dashboard](https://vercel.com/dashboard).
2. اضغط على **Add New...** -> **Project**.
3. اختر مستودع GitHub الخاص بك واضغط **Import**.
4. الإعدادات الافتراضية:
   - **Framework Preset:** `Other`
   - **Build Command:** اتركه فارغاً أو سيعمل تلقائياً من `package.json`.
   - **Output Directory:** اتركه فارغاً (الجذر `.`).
5. اضغط على زر **Deploy**.
6. مبروك! موقعك الآن يعمل مباشرة وبدون أي أخطاء، مع روابط نظيفة (Clean URLs) وشهادة SSL مجانية وتخزين مؤقت عالي السرعة.

---

## 💻 التشغيل المحلي والتجربة (Local Development)

إذا كنت ترغب في تشغيل الموقع على جهازك محلياً:

```bash
# تشغيل الخادم المحلي
npm start
# أو مباشرة عبر Node:
node server.js
```
ثم افتح متصفحك على: `http://localhost:3000`

---

## 🛠️ أبرز الإصلاحات والتحسينات المنجزة:
1. **إصلاح خطأ `vercel.json`:** تم حذف خاصية `routes` المتضاربة وتفعيل التوجيه الحديث عبر `cleanUrls: true` وتعيين `headers` للتخزين المؤقت للأصول وفق معايير Vercel الرسمية.
2. **إضافة ملف `package.json`:** لضمان توافق منصات الاستضافة مع معايير البناء وتوفير سكربت `npm start` و `npm run build`.
3. **تصميم صفحة `404.html` مخصصة:** متوافقة مع نظام التصميم بالنمط الفاتح ومزودة بروابط سريعة وأزرار اتصال وواتساب.
4. **تحديث سكربت `upload_to_github.js`:** معالجة معرّف المستودع الناقص والتحقق من صلاحية الحساب قبل الرفع.
5. **إضافة ملفات `.gitignore` و `.gitattributes` و `robots.txt` و `sitemap.xml`:** لتأمين رفع ملفات نظيفة وتوافق أطراف الأسطر وتحسين محركات البحث.
