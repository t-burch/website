---
title: איתור מזהי חשבונות
slug: account-id
top_graphic: 1
date: 2016-08-10
lastmod: 2019-07-30
---

{{< lastmod >}}

בעת דיווח על תקלות יותר מועיל לספק לנו את מזהה החשבון שלך ב־Let's Encrypt. בדרך כלל, תהליך יצירת החשבון מטופל אוטומטית על ידי תכנית ה־ACME שמשמשת אותך ליצירת קשר עם Let's Encrypt וייתכן שיש לך מגוון חשבונות מוגדרים אם מותקנים אצלך לקוחות ACME על מספר שרתים שונים.

מזהה החשבון שלך הוא כתובת בצורה `https://acme-v02.api.letsencrypt.org/acme/acct/12345678`.

אם נעשה אצלך שימוש ב־Certbot, באפשרותך לאתר את מזהה החשבון בשדה „uri” שבתוך `‎/etc/letsencrypt/accounts/acme-v02.api.letsencrypt.org/directory/*/regr.json`.

אם בחרת להשתמש בלקוח ACME אחר, ההנחיות תהיינה תלויות סוג לקוח. ניתן לחפש בקובצי היומן שלך אחר כתובות שנראות כמו אלו שהוזכרו קודם לכן. אם לקוח ה־ACME שלך אינו מתעד את מזהה החשבון, ניתן לקבל אותו על ידי הגשת בקשת הרשמה חדשה עם אותו המפתח. ב[מפרט של ACME](https://tools.ietf.org/html/rfc8555#section-7.3) ניתן למצוא פירוט נוסף. ניתן גם למצוא את התצורה המספרית של המזהה שלך בכותרת Boulder-Requester שמופיעה בתגובה לכל בקשת POST שלקוח ה־ACME שלך מבצע.