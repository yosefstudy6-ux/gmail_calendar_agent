# L06 Gmail Calendar Agent

פרויקט מטלה לשיעור 6 בקורס AI Agents.

## מה המערכת עושה
המערכת קוראת מיילים מ-Gmail לפי query, מזהה האם המייל הוא הזמנה לפגישה, מחלצת תאריך, שעה, משתתפים ומקום, בודקת זמינות ב-Google Calendar, ויוצרת אירוע או שולחת מייל דחייה.

## מבנה הפרויקט
- `main.py` — קובץ ההרצה הראשי
- `src/config.py` — הגדרות קבועות ונתיבי קבצים
- `src/gmail_service.py` — פעולות Gmail
- `src/calendar_service.py` — פעולות Google Calendar
- `src/meeting_parser.py` — ניתוח מיילים בעזרת LLM עם fallback
- `docs/PRD.md`
- `docs/PLAN.md`
- `docs/TODO.md`

## דרישות
- Python 3.10+
- uv
- Gmail API enabled
- Google Calendar API enabled
- OAuth Desktop Client
- `credentials.json` בתוך `C:\study\private_google`

## התקנה
```powershell
cd C:\study\l06_agent
uv sync
```

## משתנה סביבה ל-LLM
ב-PowerShell:
```powershell
$env:LLM_API_KEY="PUT_YOUR_KEY_HERE"
```

אפשר גם:
```powershell
$env:LLM_MODEL="gpt-4o-mini"
```

## הרצה
```powershell
cd C:\study\l06_agent
uv run main.py
```

## בדיקות
1. מייל פגישה בזמן פנוי — אמור ליצור אירוע.
2. מייל פגישה בזמן תפוס — אמור לשלוח מייל דחייה.
3. מייל רגיל — אמור להיות מסווג כלא-פגישה.
4. מייל פגישה בלי תאריך/שעה — אמור להיעצר בלי יצירת אירוע.

## הערת אבטחה
לא מעלים ל-GitHub את `credentials.json`, `token.json` או מפתחות API.