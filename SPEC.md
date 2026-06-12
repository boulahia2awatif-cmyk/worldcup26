# تطبيق نتائج المباريات الرياضية - World Cup 2026 Live

## 1. Concept & Vision

تطبيق رياضي عصري لعرض نتائج مباريات كرة القدم مباشرة بتصميم أنيق يحاكي تطبيقات البطولات الكبرى. يعتمد على الوضع الليلي بألوان زرقاء داكنة ويوفر تجربة سلسة وسريعة لمتابعة المباريات الحية والجداول والترتيب.

## 2. Design Language

### Aesthetic Direction
- Dark Mode مع تدرجات زرقاء وبنفسجية
- تصميم بطاقات (Cards) مع زوايا مستديرة و ظلال خفيفة
- أيقونات أعلام الدول بتصميم flat
- تجربة مستخدم رياضية ديناميكية

### Color Palette
```
Primary:      #1E3A5F (أزرق داكن)
Secondary:    #2563EB (أزرق فاتح)
Accent:       #10B981 (أخضر للحالة الحية)
Background:   #0F172A (خلفية رئيسية)
Surface:      #1E293B (سطح البطاقات)
Text Primary: #F8FAFC (نص رئيسي)
Text Secondary: #94A3B8 (نص ثانوي)
Live Red:     #EF4444 (مباريات حية)
Warning:      #F59E0B (تحذيرات)
```

### Typography
- **Primary Font**: Noto Sans Arabic (للعربية)
- **Secondary Font**: Inter (للإنجليزية والأرقام)
- **Headings**: Bold, 18-24px
- **Body**: Regular, 14-16px
- **Scores**: Bold, 32-48px

### Spatial System
- Padding: 16px (mobile standard)
- Card Border Radius: 16px
- Gap between cards: 12px
- Safe area: 20px top/bottom

### Motion Philosophy
- Smooth transitions: 300ms ease
- Live pulse animation للعناصر الحية
- Card hover/tap feedback
- Countdown timer animation

## 3. Layout & Structure

### Navigation
- Bottom navigation bar مع 4 tabs:
  1. النتائج الحية (Live)
  2. المباريات (Matches)
  3. الترتيب (Standings)
  4. المزيد (More)

### Pages Structure
1. **الصفحة الرئيسية (Live)**
   - Header مع اسم البطولة والتاريخ
   - قسم المباريات الحية (مع رسالة مناسبة عند عدم وجود مباريات)
   - قسم المباريات القادمة (يظهر دائماً)
   - قسم الترتيب (يظهر دائماً)

2. **صفحة المباريات**
   - تبويبات: اليوم / الغد / الأمس
   - قائمة المباريات مع التوقيت

3. **صفحة الترتيب**
   - قوائم المجموعات (A-L)
   - جدول النقاط والأهداف

## 4. Features & Interactions

### Core Features
1. **عرض المباريات الحية**
   - نتيجة مباشرة محدثة
   - الدقيقة الحالية للمباراة
   - إحصائيات سريعة (تسديدات، ركلات ركنية)
   - حالة المباراة (الشوط الأول، الثاني، استراحة)
   - رسالة مناسبة عند عدم وجود مباريات حية

2. **جدول المباريات**
   - مباريات اليوم والغد
   - عد تنازلي لبداية المباراة
   - معلومات الملعب والمنظم
   - عرض المباريات القادمة حتى بدون مباريات حية

3. **ترتيب المجموعات**
   - نقاط الفرق
   - فارق الأهداف
   - عدد الانتصارات والتعادلات والهزائم
   - يظهر دائماً بغض النظر عن وجود مباريات حية

4. **تحديث تلقائي**
   - تحديث النتائج كل 30 ثانية
   - إشعارات للمباريات المهمة

### Interactions
- Tap على بطاقة المباراة → تفاصيل أكثر
- Swipe للتنقل بين الأيام
- Pull to refresh للتحديث اليدوي
- Animation للنتائج المحدثة

## 5. Component Inventory

### Match Card
- **States**: Live (red glow), Finished, Upcoming (countdown)
- **Content**: Team flags, Score, Time/Minute, Stadium
- **Animation**: Pulse for live, Score update animation

### Standings Table
- **Header**: Group name
- **Rows**: Position, Flag, Team, P, W, D, L, GD, Pts
- **Highlight**: Top 2 teams (qualified) in green

### Navigation Tab
- **States**: Active (accent color), Inactive (gray)
- **Icon + Label**: SVG icon + text

### Live Indicator
- Pulsing red dot مع "LIVE" label
- Animation: Scale 1→1.2→1, 1s infinite

### No Live Matches State
- Icon (⚽) + Title + Subtitle
- Gradient background with accent color
- Message directing to upcoming matches and standings
- Always shows when there are no live matches

## 6. Technical Approach

### Stack
- HTML5 + CSS3 + Vanilla JavaScript
- PWA-ready structure
- LocalStorage for preferences

### Data
- Static JSON data للنتائج والجداول
- Simulated live updates

### Responsive
- Mobile-first (375px base)
- Touch-optimized interactions
- Safe areas for notch devices