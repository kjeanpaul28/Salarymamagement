# 🚀 MAYE System - Family Wealth Management Suite

## 📋 Overview

**MAYE System** ni sisitemu ya kijyambere yo gucunga amafaranga mu rugo, ikorerwa mu buryo bwa **Single Page Application (SPA)** ikoresheje **Vanilla JavaScript**, **Tailwind CSS**, na **Firebase** nk'ikigo cy'ibikoresho. Sisitemu itanga ibikorwa byinshi birimo gucunga amafaranga yinjira (Income), ibyo ugura (Procurement), raporo z'ikoranabuhanga, n'ibindi.

---

## 🎯 Features nyamukuru

### 1. 🔐 **Authentication System** (`auth.html`)
- Kwiyandikisha (Register) n'amakuru y'ibanze
- Kwinjira (Login) n'ijambo ryibanga
- Reset Password binyuze kuri email
- Kwinjira ukoresheje Google / GitHub
- Igenzura rya email verification
- Remember me functionality
- Password strength meter
- Dark/Light mode toggle

### 2. 📊 **Dashboard** (`dashboard.html`)
- KPI Cards: Total Income, Expenses, Net Balance, Savings Rate
- Charts: Bar chart (Income vs Expenses), Line chart (Monthly trend), Doughnut (Category distribution)
- Today's Summary
- Financial Health Meter
- AI Insights Panel (ibitekerezo bikurikije amakuru)
- Recent Activity Feed
- Quick Actions (Add Income, Export, View All)

### 3. 💰 **Income Management** (`income.html`)
- Kwongera, guhindura, gusiba income
- Filters: Category (Salary, Bonus, Freelance, Investment, Gift, Other)
- Sort by date/amount
- Date range filter (This month, Last month, This year, Last 3 months)
- Search functionality
- Tags system
- Export (CSV, JSON)
- Real-time updates
- Pagination

### 4. 🛒 **Procurement Management** (`procurement.html`)
#### Requisitions
- Gushyiraho requisition (item, quantity, unit price, category, supplier)
- Edit requisition
- Status management (Pending, Approved, Rejected, Ordered, Received)
- Priority levels (Low, Medium, High, Urgent)

#### Purchase Orders
- Auto-register purchase iyo requisition ihinduriwe "approved"
- Gushyiraho purchase order
- Edit/Delete purchase
- Status tracking

#### Suppliers
- Gushyiramo, guhindura, gusiba abatanga ibikoresho
- Contact information management

#### Reports
- Spending by category chart
- Monthly spending trend
- Export (CSV)

### 5. 📈 **Reports & Analytics** (`reports.html`)
- Report Builder (Date range, category, chart type)
- Executive summary
- KPI metrics (Total Income, Transactions, Average, Highest)
- Multiple chart types (Bar, Line, Pie, Doughnut)
- Transaction data table
- Export (PDF, Excel, CSV, Print)
- Save/load reports
- AI Insights

### 6. ⚙️ **Settings** (`settings.html`)
- **Profile Management**: Name, Username, Bio, Profile picture upload (file/URL)
- **Currency Settings**: USD, EUR, AED (D), RWF
- **Appearance**: Dark/Light mode, Primary color, Card style
- **Security**: Change password, Active sessions, Login history
- **Notifications**: Email alerts, In-app notifications, Budget alerts
- **System Preferences**: Language (English/Kinyarwanda), Timezone, Date format, Time format
- **Danger Zone**: Clear all data, Deactivate account, Delete account permanently

---

## 🏗️ Architecture Technique

### Frontend Stack
- **HTML5** - Structure
- **Tailwind CSS** - Styling (glassmorphism, responsive design)
- **Vanilla JavaScript (ES6+)** - Logic yose
- **Chart.js** - Visualisations
- **Font Awesome 6** - Ikon

### Backend & Database
- **Firebase Authentication** - Kwinjira no kurengera umutekano
- **Firestore Database** - Kubika amakuru (NoSQL)
- **Firebase Storage** - Kubika amafoto

### External Libraries
- **html2pdf.js** - Kuramo raporo nka PDF
- **SheetJS (XLSX)** - Kuramo Excel
- **QRCode.js** - Kurema QR codes

---

## 📁 Structure ya Database (Firestore)

### Collections:

#### `users`
```json
{
  "fullName": "string",
  "email": "string",
  "profilePicture": "string (URL)",
  "username": "string",
  "bio": "string",
  "settings": {
    "currency": "string (USD/EUR/AED/RWF)",
    "theme": "string (dark/light)",
    "language": "string (en/rw)",
    "dateFormat": "string",
    "timeFormat": "string (12h/24h)",
    "primaryColor": "string (hex)",
    "cardStyle": "string (glass/solid/minimal)",
    "emailNotifications": "boolean",
    "inAppNotifications": "boolean",
    "budgetAlerts": "boolean"
  },
  "createdAt": "timestamp",
  "lastLogin": "timestamp"
}