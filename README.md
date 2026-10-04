# نظام حصر الأسر - Android

هذا المشروع يحول ملف HTML الموجود في `www/index.html` إلى تطبيق Android باستخدام Capacitor.

## الملفات

- `www/index.html` — التطبيق HTML الحالي.
- `capacitor.config.ts` — إعدادات Capacitor.
- `package.json` — مكتبات المشروع.
- `.github/workflows/build-android.yml` — يبني APK تلقائياً على GitHub Actions.

## بناء APK من GitHub

1. ارفع هذه الملفات إلى المستودع.
2. افتح تبويب **Actions**.
3. اختر **Build Android APK**.
4. اضغط **Run workflow** إذا لم يبدأ البناء تلقائياً.
5. بعد نجاح البناء افتح الـ workflow ثم **Artifacts**.
6. نزّل `big-ben-survey-debug-apk` وستجد داخله `app-debug.apk`.

## ملاحظة مهمة

التطبيق نفسه يعتمد على Supabase الموجود داخل ملف HTML، بما في ذلك الجداول والصلاحيات ودالة تسجيل الدخول. لذلك يجب أن تكون قاعدة Supabase والجداول وسياسات RLS ودالة `get_login_email_by_username` موجودة كما يتوقعها التطبيق.

المجلد `android/` لا يلزم رفعه يدوياً هنا؛ ملف GitHub Actions يقوم بإنشائه بواسطة `npx cap add android`.
