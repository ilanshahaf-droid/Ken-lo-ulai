# כן · לא · אולי – PWA (GitHub Pages, נתיבים יחסיים)

## למה גרסה נפרדת ל-GitHub
GitHub Pages של פרויקט (לא user page) מגיש את האתר מתת-נתיב, למשל:
`https://ilanshahaf-droid.github.io/Ken-lo-ulai/`

נתיבים מוחלטים שמתחילים ב-`/` (כמו `/icon-192.png`) היו מצביעים בטעות ל-
`https://ilanshahaf-droid.github.io/icon-192.png` (שורש הדומיין, לא תוך התיקייה של הפרויקט) — ולכן בגרסה הזו כל הנתיבים ב-manifest.json, ב-index.html וב-sw.js הם **יחסיים** (בלי `/` בהתחלה), כדי שיעבדו נכון בתת-הנתיב.

## מה יש בזיפ (הכל בשורש הריפו, בלי תיקיות)
```
index.html
manifest.json
sw.js
icon-192.png
icon-512.png
icon-maskable-512.png
welcome.png
play.png
README.md
```

## איך מעלים ל-GitHub
**דרך האתר (הכי פשוט):**
1. גשו לריפו: https://github.com/ilanshahaf-droid/Ken-lo-ulai
2. לחצו "Add file" → "Upload files"
3. גררו את **כל** הקבצים מתוך הזיפ (חוץ מ-README.md זה לא חובה) ישירות לשם — לא לתוך תיקייה, אלא לשורש הריפו
4. אם יש כבר קבצים באותם שמות (למשל `manifest.json` ישן) — GitHub יציע להחליף אותם, אשרו
5. לחצו Commit changes

**חשוב:** ודאו שב-Settings → Pages של הריפו, המקור (Source) מוגדר ל-branch הנכון (בדרך כלל `main`) ולתיקייה `/ (root)`.

## בדיקה
אחרי כמה דקות (GitHub Pages לוקח זמן לפרסם) פתחו:
- https://ilanshahaf-droid.github.io/Ken-lo-ulai/manifest.json — ודאו שרואים את ה-JSON הנכון (עם "כן · לא · אולי", לא "תזונה וכושר")
- https://ilanshahaf-droid.github.io/Ken-lo-ulai/icon-192.png — ודאו שרואים את אייקון הלב

ואז רעננו את הבדיקה ב-PWABuilder על אותה כתובת.

## עדכון בעתיד
כל שינוי ב-index.html דורש Commit חדש לריפו. אם משנים משהו משמעותי, כדאי לעדכן את `CACHE_NAME` בתוך `sw.js` (למשל מ-`v4` ל-`v5`) כדי שמכשירים שכבר ביקרו יקבלו את הגרסה החדשה ולא את הישנה מהמטמון.
