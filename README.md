# AutoRoy Scalable Chat 🚀

[🌐 Live UI](https://autoroy-chat-ui.onrender.com/)
[🟢 Chat Service Health](https://autoroy-chat-service.onrender.com/)
[🟢 Auth Service Health](https://autoroy-auth-service.onrender.com/)

פרויקט דמו בתחום **DevOps / Cloud / Fullstack** שמדגים איך לבנות צ׳אט סקיילבילי בסגנון Slack/Discord, עם הפרדה בין Frontend ל-Microservices, דיפלוי ל-Render, והכנה ל־CI/CD.

---

## 🧩 מה הפרויקט עושה?

- מסך התחברות עם **אימות בסיסי** דרך שירות Auth נפרד.
- בחירת שם תצוגה (Display Name) לפני כניסה לצ׳אט.
- צ׳אט חי בזמן־אמת בעזרת **Socket.IO**.
- תמיכה בשליחת **קישורי תמונות** (URL) והצגתן בתור בועה בצ׳אט.
- הודעות מערכת בסגנון “מישהו הצטרף לצ׳אט”.
- חלוקה לשירותים:
- שירות Auth (כניסה).
- שירות Chat (Socket.IO).
- UI סטטי שמדבר עם שניהם.

---

## 🏗 ארכיטקטורה

![Architecture](./architecture-diagram.png)

**תרשים גבוה (High Level):**

- **Client (UI)** – אתר סטטי שמתארח ב-Render, מדבר עם:
- `autoroy-auth-service` עבור `/login`
- `autoroy-chat-service` עבור WebSocket (Socket.IO)
- **Auth Service** – שירות Node/Express קטן שנותן token דמה.
- **Chat Service** – שירות Node/Socket.IO שמנהל את חדר הצ׳אט.
- תקשורת HTTP + WebSocket מעל HTTPS (Render).

---

## 🛠 טכנולוגיות

**Frontend**

- HTML, CSS, JavaScript (Vanilla)
- עיצוב מודרני (Dark Mode), RTL, אנימציות קלות
- Socket.IO Client

**Backend**

- Node.js + Express
- Socket.IO
- CORS
- דיפלוי כשני שירותים נפרדים ב-Render

**DevOps / Cloud**

- דיפלוי אוטומטי מ-GitHub ל-Render (Auto Deploy on push)
- הפרדה בין UI ל-Backend
- Health checks לכל שירות

---

## 🚀 איך מריצים לוקלית

### 1. קלאיינט (UI)

```bash
git clone https://github.com/autoroybiz-cpu/scalable-chat.git
cd scalable-chat
# פותחים index.html בדפדפן בצורה סטטית
# (אפשר עם Live Server ב-VSCode, או פשוט פתיחה ידנית)
