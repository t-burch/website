---
title: מגבלת אימות כושל
slug: failed-validation-limit
lastmod: 2022-06-30
show_lastmod: false
---


# תיאור
כל בקשות ההנפקה כפופות למגבלת *אימותים כושלים* על סך 5 כשלונות לחשבון, לשם מארח, לשעה. לקוח ה־ACME שלך אמור להציג את הודעת השגיאה הבאה בעת חריגה ממגבלת אימותים כושלים:

```
too many failed authorizations recently: see https://letsencrypt.org/docs/failed-validation-limit/
```

אותם ‚אימותים’ אליהם מתייחסת השגיאה הזאת הם תוצאה של בקשות אימות שנשלחו על ידי לקוח ה־ACME שלך כדי לתקף את השליטה בשם התחום לפני שנוכל להנפיק או לחדש אישור חדש. שגיאה זו מציינת שמספר בקשות לתיקוף נשלחו בהצלחה אך כל ניסיונות התיקוף נכשלו.

# גורמים נפוצים

מנויים שניצלו את מיכסת האימותים הכושלים שלהם בדרך כלל הגיעו לכך עקב הגדרות שגויות בסביבה שלהם.

## HTTP-01 או TLS-APLN-01

ללקוחות ACME שדורשים אימות דרך שיטות התיקוף HTTP-01 או TLS-APLN-01, הבעיה בדרך כלל נגרמת מהגדרות רשת או חומת אש שגויות שלא מאפשרים לשרתי התיקוף שלנו להגיע לשרת ממנו נשלחה הבקשה.

## DNS-01

לקוחות ACME שדורשים אימות דרך שיטת האימות DNS-01 בדרך כלל דורשים ממך ליצור רשומת CNAME באזור ה־DNS הראשי שלך מה שמאפשר ללקוח ה־ACME להגדיר את רשומות ה־DNS הנחוצות במהלך התיקוף. תיקופי DNS-01 שכשלו הם בדרך כלל תוצאה של צעדים חסרים או שגיאות הקלדה במהלך תהליך ההגדרה הראשוני הזה.

בעת ניסיון לפתור תקלות או לבדוק את הטמעת היישומים שלך עדיף לנו שלקוח ה־ACME שלך יוגדר להשתמש ב[סביבת ההכנה להקמה שלנו](/docs/staging-environment/). מגבלות הקצב לסביבת ההכנה להקמה שלנו [גבוהות בהרבה](/docs/staging-environment/#rate-limits).

# בקשת עזרה

אם לא ברור לך איך להגדיר את לקוח ה־ACME שלך להשתמש בסביבת ההכנה להקמה או שנדרשת לך עזרה בניפוי שגיאות, אנו מזמינים אותך [לבקש עזרה בפורום הקהילתי שלנו](https://community.letsencrypt.org/c/help/13).

# בקשת מעקף

**אין** מעקפים זמינים למגבלת האימותים הכושלים.