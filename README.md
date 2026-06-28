# YOHAI Barber Shop — אתר תדמית והזמנות

אתר פרודקשן מלא, בעברית עם תמיכת RTL מלאה, מותאם לכל המכשירים, מוכן להעלאה לכל שרת אחסון רגיל.

A complete, production-ready Hebrew (RTL) website for YOHAI Barber Shop. Static HTML/CSS/JS — no build step, no dependencies. Upload the folder to any standard web host and it works.

---

## 📁 מבנה הפרויקט / Project structure

```
yohai-site/
├── index.html            # כל האתר (עמוד יחיד עם עוגנים)
├── css/
│   └── styles.css        # כל העיצוב — RTL-first, טוקנים של מותג
├── js/
│   └── main.js           # ניווט, אנימציות, גלריה, מערכת הזמנות
├── images/               # תמונות (אפשר להחליף בקלות — ראו למטה)
│   ├── owner-portrait.jpg
│   ├── groom-*.jpg        # תמונות חתנים (שחור-לבן)
│   ├── cut-01..09.jpg     # גלריית עבודות
│   ├── og-image.jpg       # תמונת שיתוף לרשתות
│   └── apple-touch-icon.png
├── favicon.svg
├── favicon-32.png
├── site.webmanifest
├── robots.txt
└── sitemap.xml
```

---

## 🚀 העלאה / Deploy

פשוט העלו את **כל תיקיית `yohai-site`** לשרת (cPanel / Netlify / Vercel / GitHub Pages / כל אחסון).
אין צורך בהתקנות, בבנייה או בשרת Node — זהו אתר סטטי.

Just upload the whole folder. No build, no server-side runtime required.

---

## ✏️ החלפת פרטי העסק / Replace placeholder details

כל פרטי ההתקשרות הם **זמניים** וקל להחליף אותם. חפשו והחליפו במקומות הבאים:

### 1. מספר וואטסאפ (החשוב ביותר — משמש בטופס ההזמנות)
**`js/main.js`** → בראש הקובץ, אובייקט `CONFIG`:
```js
const CONFIG = {
  whatsapp: "972501234567",   // ← שנו למספר שלכם (פורמט בינלאומי, בלי + ובלי רווחים)
  ...
};
```
זהו גם המקום לעדכן את **שעות הפעילות** שמהן נבנות משבצות הזמן בטופס (`slotsWeekday`, `slotsFriday`, `closedDay`).

### 2. טלפון, אימייל, כתובת, וואטסאפ להצגה
**`index.html`** — חפשו והחליפו:
| Placeholder | מופיע ב |
|---|---|
| `03-1234567` | קישורי טלפון + פוטר + סקציית "צור קשר" |
| `972501234567` | קישורי וואטסאפ (כפתור צף, צור קשר, פוטר) |
| `050-0000000` | מספר וואטסאפ להצגה |
| `info@yohai-barber.co.il` | אימייל |
| `רחוב הדוגמה 7, תל אביב` | כתובת |
| `www.yohai-barber.co.il` | דומיין (תגיות SEO / Open Graph / Schema) |

### 3. מפת Google / מיקום
**`index.html`** → סקציית `contact__map` → ה‑`<iframe>` מצביע כרגע על OpenStreetMap עם קואורדינטות לדוגמה.
להחלפה במפת Google: היכנסו ל‑Google Maps → שתף → הטמע מפה → העתיקו את ה‑`<iframe>` והחליפו. עדכנו גם `latitude`/`longitude` ב‑Schema שבראש ה‑HTML.

### 4. רשתות חברתיות
**`index.html`** — קישורי `instagram.com`, `facebook.com`, `tiktok.com` (בפוטר וב‑Schema). החליפו לכתובות שלכם.

### 5. שעות פעילות להצגה
**`index.html`** → סקציית `contact__hours` (וגם בפוטר). עדכנו לפי הצורך — וזכרו לעדכן בהתאם גם את `CONFIG` ב‑JS וגם את ה‑Schema.

---

## 🖼️ החלפת תמונות / Replace images

כל תמונה היא קובץ בתיקיית `images/`. כדי להחליף — פשוט שמרו קובץ חדש **באותו שם**:

| קובץ | שימוש | יחס מומלץ |
|---|---|---|
| `owner-portrait.jpg` | תמונת ה‑Hero (הספר) | לאורך 4:5 |
| `cut-01.jpg` … `cut-09.jpg` | גלריית עבודות | לאורך (כל יחס) |
| `groom-window.jpg` | תמונת חתן ראשית (גבוהה) | לאורך 3:4 |
| `groom-cuff.jpg`, `groom-tefillin.jpg` | גלריית חתנים | לאורך 3:4 |
| `og-image.jpg` | תצוגה בשיתוף ברשתות | 1200×630 |

הפריסה בנויה כך שברגע שמחליפים את התמונות — האתר נראה מושלם מיד.
*טיפ:* כווצו תמונות לפני העלאה (למשל ב‑[squoosh.app](https://squoosh.app)) כדי לשמור על מהירות טעינה.

---

## ✅ מה כלול / What's included

- **עברית + RTL מלא** בכל רכיב: ניווט, Hero, כותרות, טפסים, גלריה, מודאלים, פוטר.
- **טיפוגרפיה פרמיום:** Frank Ruhl Libre (כותרות) + Heebo (גוף) — זוג גופנים עברי יוקרתי.
- **מערכת הזמנות מלאה:** בחירת שירות → תאריך ושעה → פרטים → מסך אישור, עם ולידציה ושליחה לוואטסאפ.
- **SEO:** תגיות Title/Description, Open Graph, Twitter Cards, נתונים מובְנים (Schema HairSalon), HTML סמנטי, היררכיית כותרות תקינה.
- **נגישות:** דילוג לתוכן, פוקוס מקלדת, alt לכל תמונה, תוויות לכל שדה, תמיכה ב‑`prefers-reduced-motion`.
- **ביצועים:** תמונות מותאמות (~1.1MB סה"כ), JS מינימלי ללא תלויות, `loading="lazy"`, התוכן נראה גם בלי JavaScript.
- **רספונסיביות:** דסקטופ / לפטופ / טאבלט / מובייל — ללא שבירות.

---

## 🎨 מערכת המותג / Brand system

| | |
|---|---|
| Obsidian Black | `#0B0B0C` |
| Pure White | `#FFFFFF` |
| Heritage Gold | `#C5A463` |
| Charcoal | `#2E2E2E` |
| Bone | `#F5F2EC` |
| Gold Deep | `#9C7C40` |

עיצוב שטוח (ללא גרדיאנטים/צללים), יחס ~95% שחור / 4% לבן / 1% זהב — בדיוק כמו ספר המותג.

---

© YOHAI Barber Shop. נבנה כחוויית פרמיום.
