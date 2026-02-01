# IR Playbook Manager - Product Requirements Document

## 1. Product Overview

### Problem Statement
אנשי Incident Response וצוותי אבטחה מתקשים לעקוב אחרי כל השלבים הנדרשים בתקרית סייבר. זה מוביל לפיספוס שלבים קריטיים, אובדן ראיות, עמידה לא עקבית בזמני תגובה, ותיעוד לא מלא של התקרית.

### Solution Statement
אפליקציה אינטראקטיבית לניהול תקריות IR עם playbooks מובנים, צ'קליסטים דינמיים, ומעקב זמנים - הכל בממשק אחד נקי וידידותי למשתמש.

### Target Audience
- אנשי Incident Response
- SOC Analysts
- DFIR Investigators
- Security Managers
- מומחי סייבר ב-SMBs

## 2. Core Features

### 2.1 Incident Creation & Classification
- **טופס יצירת תקרית חדש** עם שדות חובה: סוג תקרית, רמת חומרה, תיאור ראשוני
- **סוגי תקריות מוגדרים מראש**: Malware, Data Breach, Phishing, DDoS, Insider Threat, etc.
- **מערכת דירוג חומרה**: Critical, High, Medium, Low עם צבעים ויזואליים
- **הקצאה אוטומטית של playbook** בהתאם לסוג התקרית

### 2.2 Interactive IR Playbooks
- **playbooks מובנים** לכל סוג תקרית עם שלבים מפורטים
- **צ'קליסטים אינטראקטיביים** - משתמש יכול לסמן שלבים כמושלמים
- **שלבים עם זמנים מומלצים** (SLA) וטיימר וויזואלי
- **ערעור לשלב הבא** אוטומטי כשמסיימים שלב נוכחי
- **התאמה אישית** - אפשרות להוסיף/לערוך שלבים

### 2.3 Evidence & Timeline Tracking
- **מעקב ראיות**: רשימה של קבצים, screenshots, logs שנאספו
- **ציר זמן של התקרית**: מתי מה קרה, מי עשה מה
- **הערות ותיעוד**: שדה טקסט חופשי לכל שלב
- **סטטוס התקרית**: Open, In Progress, Contained, Resolved

### 2.4 Time Management & SLA Tracking
- **מונה זמן כולל** מרגע פתיחת התקרית
- **מעקב SLA** לכל רמת חומרה עם אזהרות צבעוניות
- **זמן תגובה ראשוני** (Time to Acknowledge)
- **זמן לכלתם** (Time to Contain)
- **זמן לפתרון** (Time to Resolve)

### 2.5 Reporting & Export
- **דוח תקרית אוטומטי** עם כל הפרטים, זמנים, ושלבים שבוצעו
- **ייצוא ל-JSON** למערכות SIEM/SOAR
- **הדפסה ל-PDF** לתיעוד חיצוני
- **סטטיסטיקות בסיסיות**: זמני תגובה ממוצעים, סוגי תקריות נפוצות

### 2.6 Dashboard & Active Incidents
- **לוח בקרה** עם כל התקריות הפתוחות
- **פילטר לפי סטטוס/חומרה/אחראי**
- **התראות ויזואליות** לתקריות שעוברות SLA
- **מעקב workload** - כמה תקריות פתוחות לכל אדם

## 3. Technical Requirements

### 3.1 Technology Stack
- **Frontend Only**: Single-page HTML application
- **Storage**: localStorage למידע מקומי (no backend required)
- **UI Framework**: Vanilla JavaScript + CSS
- **Icons**: Font Awesome
- **Fonts**: Professional web fonts (Roboto/Inter)
- **Theme**: Dark theme as primary

### 3.2 Browser Compatibility
- Modern browsers (Chrome 90+, Firefox 88+, Safari 14+, Edge 90+)
- Progressive Web App capabilities
- Responsive design for mobile/tablet

### 3.3 Data Persistence
- All data stored in localStorage
- Import/Export functionality for data backup
- No server-side dependencies

## 4. User Interface Design

### 4.1 Design Principles
- **Dark theme by default** - easier on eyes during long incident response sessions
- **Clean, professional interface** - minimal distractions during high-stress situations
- **Color-coded priorities** - immediate visual understanding of urgency
- **Accessibility friendly** - keyboard shortcuts, good contrast ratios
- **Mobile responsive** - usable on tablets/phones for on-the-go management

### 4.2 Key UI Components
- **Navigation header** with active incident counter and quick actions
- **Dashboard grid view** showing all incidents with status cards
- **Incident detail modal** with tabbed interface (Details, Playbook, Timeline, Evidence)
- **Progress indicators** for playbook completion and SLA status
- **Quick action buttons** for common tasks
- **Toast notifications** for successful actions

### 4.3 Color Scheme
- **Background**: Dark greys (#1a1a1a, #2d2d30)
- **Text**: Light grey (#e4e4e4)
- **Accents**: Blue (#0078d4) for primary actions
- **Critical**: Red (#ff4444) for critical incidents and SLA breaches
- **Warning**: Orange (#ff9900) for medium priority and warnings
- **Success**: Green (#00aa44) for completed tasks and resolved incidents

## 5. MVP Features for Initial Release

### Phase 1 (MVP)
1. Incident creation with basic classification
2. Pre-built playbooks for 5 common incident types
3. Interactive checklist with progress tracking
4. Basic timer and SLA tracking
5. Simple incident dashboard
6. Export incident report to text

### Phase 2 (Future Enhancements)
1. Custom playbook editor
2. Team collaboration features
3. Advanced reporting and analytics
4. Integration hooks for external tools
5. Notification system
6. Incident templates and automation

## 6. Success Metrics
- **Time to implement initial response** reduced by 30%
- **Incident documentation completeness** improved to 95%+
- **SLA compliance** improved by 25%
- **User adoption** by IR professionals

## 7. Constraints & Assumptions
- No backend/server infrastructure available
- Must work offline after initial load
- Single-user application (no multi-user collaboration in MVP)
- Data stored locally only (user responsible for backups)

---

*This PRD defines a practical, single-page application for managing incident response processes efficiently and effectively.*