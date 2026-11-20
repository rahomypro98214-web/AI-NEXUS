# AI NEXUS — Android starter project

نسخة أولية عربية من AI NEXUS تعمل داخل Android WebView.

## ما الذي يعمل الآن؟
- واجهة Glassmorphism متجاوبة للهاتف.
- تنقل بين المحادثة، استوديو الصور، مختبر الأكواد، صانع المشاريع، وتحليل الملفات.
- محادثة محلية تجريبية (ردود ثابتة/قواعد بسيطة، وليست نموذجاً لغوياً حقيقياً).
- تجهيز وصف الصور، دون توليد صورة فعلي.
- محرر HTML/CSS/JavaScript/Python، تنزيل الكود ومعاينة HTML.
- إنشاء مخطط مشروع لعبة/موقع وتنزيله.
- اختيار ملف من Android وتحليل النص محلياً (عدد الأحرف والكلمات والأسطر ومعاينة).
- لا يتم رفع الملفات إلى الإنترنت.

## ما الذي لا يعمل بعد؟
ميزات الذكاء الاصطناعي السحابي وتوليد الصور الفعلي تحتاج مزود نموذج وخادماً وسيطاً. لا تضع مفاتيح API داخل JavaScript أو APK؛ يمكن استخراجها من التطبيق. أنشئ Backend يحتفظ بالمفاتيح ويطبق حدود الاستخدام والحماية، ثم اربط الواجهة بنقاط API الخاصة به.

ملفات PDF الثنائية لا تُحلل في هذه النسخة؛ يدعم محلل الملفات حالياً النصوص مثل TXT وMD وJSON وHTML وCSS وJS وCSV وXML.

## بناء APK
المتطلبات:
- Android Studio حديث
- JDK 17
- Android SDK Platform 35
- Gradle 8.9 مثبت محلياً أو إعداد Gradle من Android Studio

الخطوات:
1. فك ضغط المشروع.
2. افتح مجلد `AI_NEXUS_Android` في Android Studio.
3. انتظر Gradle Sync.
4. اختر Build > Build Bundle(s) / APK(s) > Build APK(s).
5. سيظهر APK عادةً في `app/build/outputs/apk/debug/app-debug.apk`.

يمكن أيضاً من الطرفية بعد تثبيت Gradle 8.9 وضبط Android SDK:
```bash
gradle assembleDebug
```
ملاحظة: حزمة المصدر لا تتضمن ملف Gradle Wrapper التنفيذي أو ملف wrapper JAR؛ استخدم Gradle المثبت محلياً أو أنشئ Wrapper من Android Studio.

## هيكل المشروع
```text
AI_NEXUS_Android/
  app/
    build.gradle
    src/main/
      AndroidManifest.xml
      java/com/ainexus/app/MainActivity.java
      assets/
        index.html
        style.css
        app.js
  build.gradle
  settings.gradle
  gradle.properties
  gradle/wrapper/gradle-wrapper.properties
```

## الأمان والخصوصية
- استخدم HTTPS فقط للخدمات البعيدة.
- لا تخزن مفاتيح API في التطبيق.
- لا ترفع ملفات المستخدم إلا بعد توضيح ذلك وطلب موافقته.
- راجع أذونات التطبيق قبل نشره.
