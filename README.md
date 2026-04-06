
[![Deploy to GitHub Pages](https://github.com/Willie-Conway/Little-Lemon-Restaurant-Reservation-System/actions/workflows/deploy.yml/badge.svg)](https://github.com/Willie-Conway/Little-Lemon-Restaurant-Reservation-System/actions/workflows/deploy.yml)

# Little Lemon — Mediterranean Restaurant Reservation System

![Little Lemon](https://img.shields.io/badge/Little_Lemon-Mediterranean_Restaurant-495E57?style=for-the-badge&logo=restaurant&logoColor=white)
![React](https://img.shields.io/badge/React-18-61DAFB?style=for-the-badge&logo=react&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![Responsive](https://img.shields.io/badge/Responsive-Mobile_Friendly-EE9972?style=for-the-badge&logo=googlechrome&logoColor=white)

<p align="center">
  <img src="https://img.shields.io/badge/STATUS-LIVE-495E57?style=for-the-badge&labelColor=2C2C2C" />
  <img src="https://img.shields.io/badge/RESERVATION_SYSTEM-Interactive-F4CE14?style=for-the-badge&labelColor=2C2C2C" />
  <img src="https://img.shields.io/badge/TIMESLOTS-Dynamic_Caching-EE9972?style=for-the-badge&labelColor=2C2C2C" />
  <img src="https://img.shields.io/badge/PAGES-5_Full-FBDABB?style=for-the-badge&labelColor=2C2C2C" />
</p>

---

### **About** 🍋

**Little Lemon** is a modern, fully responsive restaurant website for a fictional Mediterranean restaurant in Chicago. Built with React, this project features a beautiful multi-page layout with a hero section, weekly specials cards, full menu catalog with category filtering, about section, guest testimonials, and a fully functional table reservation system with dynamic timeslot generation. The design is warm, earthy, and inviting — reflecting the Mediterranean culinary experience. Perfect for restaurateurs, hospitality businesses, and developers looking for a polished front-end showcase. 🍽️

---

## ✨ Key Features

### 🏠 **5 Full Pages**

| Page                   | Purpose            | Key Features                                                  |
| ---------------------- | ------------------ | ------------------------------------------------------------- |
| **Home**         | Restaurant landing | Hero, specials cards, about section, testimonials, CTA banner |
| **Menu**         | Food catalog       | Filterable grid (7 categories), 14+ dishes, add-to-cart simulation |
| **About**        | Restaurant story   | Full history, chef background, guest testimonials             |
| **Booking**      | Table reservation  | Dynamic form with date picker, timeslot selector, guest count |
| **Confirmation** | Booking success    | Confirmation details with customer info, animated checkmark   |

### 🎨 **Design Highlights**

| Element            | Color        | Hex         | Usage                                    |
| ------------------ | ------------ | ----------- | ---------------------------------------- |
| **Olive**    | 🫒 Green     | `#495E57` | Primary brand color, navigation, buttons |
| **Lemon**    | 🍋 Yellow    | `#F4CE14` | Accent, highlights, call-to-action       |
| **Salmon**   | 🐟 Peach     | `#EE9972` | Secondary accent, prices, badges         |
| **Peach**    | 🍑 Light     | `#FBDABB` | Subtle backgrounds, hover states         |
| **Cream**    | 🥛 Off-white | `#FEFAE0` | Page background, cards                   |
| **Charcoal** | ⚫ Dark      | `#2C2C2C` | Text, footer                             |

---

## 🏠 **Home Page Components**

### **Hero Section** 🌟

- **Split layout**: Text content on left, image on right
- **Animated rotating badge** with restaurant establishment year
- **Call-to-action buttons**: "Reserve a Table" and "Explore Menu"
- **Key statistics**: 12+ years, 4.9★ rating, 40k guests

### **Weekly Specials** 🍽️

- **3 featured recipes** with images, badges, prices
- **Hover effects**: Card lifts, image scales, CTA arrow animates
- **Recipe details**:
  - **Greek Salad** — Vegetarian, $12.99
  - **Bruschetta** — Chef's Pick, $7.99
  - **Grilled Fish** — Signature, $20.99
- **"View Full Menu"** button navigates to Menu page

### **About Section** 📖

- **Split layout**: Two overlapping images on left, story text on right
- **Restaurant origin story** — family-owned since 2012
- **Local sourcing** commitment to Chicago farmers

### **Testimonials** ⭐

- **3 guest reviews** with star ratings
- **Quotes** from satisfied customers
- **Author attribution** with names

### **CTA Banner** 📞

- **Call to action**: "Ready for an unforgettable dining experience?"
- **Dark button** with hover effect

### **Footer** 🔗

- **4-column layout**: Brand, navigation, contact, hours
- **Address**: 12 S Michigan Ave, Chicago, IL 60603
- **Phone**: +1 312-456-7891
- **Email**: hello@littlelemon.com

---

## 📋 **Menu Page**

### **Category Filters** 🔍

| Category | Items |
|----------|-------|
| **All** | 14 dishes |
| **Appetizers** | Bruschetta, Mozzarella Sticks, Chicken Wings |
| **Salads** | Greek Salad, Caesar Salad |
| **Pasta** | Fettuccine Alfredo, Marinara Pasta |
| **Pizza** | Cheese Pizza, Pepperoni Pizza |
| **Burgers** | Mushroom Swiss Burger, Veggie Burger |
| **Seafood** | Grilled Fish, Fish Tacos |
| **Desserts** | Lemon Dessert |

### **Menu Features** 🍽️

- **Filterable grid layout** with category chips
- **14 menu items** with images, descriptions, prices
- **"Add" button** with toast notification simulation
- **Responsive grid** adapts to screen size

---

## 📅 **Booking System**

### **Form Fields** 📝

| Field                      | Type        | Validation          | Purpose                           |
| -------------------------- | ----------- | ------------------- | --------------------------------- |
| **Full Name**        | Text        | Required            | Customer identification           |
| **Email**            | Email       | Required            | Confirmation delivery             |
| **Date**             | Date picker | Required, min=today | Select reservation date           |
| **Time**             | Dropdown    | Required, dynamic   | Available timeslots               |
| **Guests**           | Number      | 1-20, required      | Party size                        |
| **Occasion**         | Select      | Optional            | None, Birthday, Anniversary, etc. |
| **Special Requests** | Text        | Optional            | Allergies, seating preferences    |

### **Timeslot Logic** ⏰

- **Dynamic generation** based on selected date
- **Seed random algorithm** for consistent but varied slots
- **Hours**: 5:00 PM – 11:30 PM
- **Slots**: On the hour and half-hour, filtered by availability
- **Caching**: Times for same date remain consistent

```javascript
const fetchTimes = (date) => {
  const r = seedRandom(new Date(date).getDate() || new Date().getDate());
  const slots = [];
  for (let h = 17; h <= 23; h++) {
    if (r() < 0.5) slots.push(`${h}:00`);
    if (r() > 0.5) slots.push(`${h}:30`);
  }
  return slots.length ? slots : ["18:00", "19:00", "20:00"];
};
```

### **Form Validation** ✅

- All required fields must be filled
- Date must be today or future
- Guests between 1-20
- Email format validation via HTML5

### **useReducer for Timeslots** 🔄

```javascript
const [times, dispatch] = useReducer(reducer, fetchTimes(today));
const reducer = (_, date) => fetchTimes(date);
```

---

## ✅ **Confirmation Page**

### **Success Animation** ✨

- **Pulsing checkmark icon** with scale animation
- **Pop animation** on page load

### **Booking Details** 📋

- **4-column grid** showing:
  - Date
  - Time
  - Guests
  - Occasion
- **Personalized greeting** with customer name

### **Return Navigation** 🔙

- **"Back to Home"** button with smooth transition

---

## 📱 **Responsive Design**

### **Mobile Breakpoints** 📲

| Breakpoint        | Layout Changes                                         |
| ----------------- | ------------------------------------------------------ |
| **< 768px** | Hero becomes single column, right image hidden         |
| **< 900px** | Cards grid becomes 1 column                            |
| **< 768px** | About section becomes single column                    |
| **< 500px** | Footer becomes single column, form grid becomes single |

---

## 🎨 **Design System**

### **Typography** ✍️

- **Cormorant Garamond** — Serif for headings, numbers, elegant touches
- **DM Sans** — Sans-serif for body text, navigation, buttons

### **Navigation** 🧭

- **Sticky navbar** that changes background on scroll
- **Logo** with lemon-colored "Lemon" text
- **Desktop links** with animated underline hover
- **Reserve button** with olive background

### **Buttons** 🔘

| Type              | Background          | Hover Effect                     |
| ----------------- | ------------------- | -------------------------------- |
| **Primary** | Lemon (`#F4CE14`) | Darker yellow, lift, shadow      |
| **Ghost**   | Transparent         | Border lightens, background tint |
| **Outline** | Transparent         | Olive fill on hover              |
| **Dark**    | Charcoal            | Olive fill on hover              |

### **Cards** 🃏

- **White background** with slight shadow
- **Hover lift** of -6px translateY
- **Image zoom** on hover (scale 1.06)
- **Price** in salmon color

### **Animations** ✨

| Element           | Animation  | Duration          |
| ----------------- | ---------- | ----------------- |
| Hero badge        | Slow spin  | 20s linear        |
| Cards             | Hover lift | 0.3s              |
| Page transitions  | Fade up    | 0.5s ease         |
| Confirmation icon | Pop        | 0.6s cubic-bezier |

---

## 🛠️ **Technical Implementation**

### **Tech Stack** 🥞

- **React 18** — Functional components with hooks
- **Pure CSS** — No frameworks, custom design system
- **Responsive design** — Media queries for all breakpoints

### **React Hooks Used** 🎣

| Hook           | Purpose                                              |
| -------------- | ---------------------------------------------------- |
| `useState`   | Page state, form fields, scrolled state, toast      |
| `useEffect`  | Scroll listener for navbar                           |
| `useReducer` | Timeslot generation based on date                    |

### **Component Structure** 🏗️

```
App
├── Navbar
├── HomePage
│   ├── Hero
│   ├── Specials
│   ├── About
│   ├── Testimonials
│   ├── CTABanner
│   └── Footer
├── MenuPage
├── AboutPage
├── BookingPage
└── ConfirmPage
```

### **Data Flow** 🔄

- **Page state** lifted to App (`useState`)
- **Booking data** passed to ConfirmPage via navigation
- **Timeslots** generated via `useReducer` with seed random

---

## 🎥 **Video Demo Script** (45-60 seconds)

| Time | Scene        | Action                                                         |
| ---- | ------------ | -------------------------------------------------------------- |
| 0:00 | Hero         | Show Little Lemon logo, rotating badge, call-to-action buttons |
| 0:05 | Specials     | Scroll through 3 cards: Greek Salad, Bruschetta, Grilled Fish  |
| 0:10 | Card Hover   | Hover over Bruschetta → card lifts, image scales              |
| 0:15 | Menu Page    | Click "Explore Menu" → navigate to Menu page                  |
| 0:20 | Menu Filters | Click "Pizza" filter → shows only pizza items                  |
| 0:25 | Add Item     | Click "Add" on Pepperoni Pizza → toast appears                |
| 0:30 | About Page   | Navigate to About page → show restaurant story                |
| 0:35 | Booking      | Click "Reserve a Table" → navigate to booking page            |
| 0:40 | Booking Form | Fill out name, email, select date → timeslots update          |
| 0:45 | Submit       | Click "Confirm Reservation" → validation, then navigate       |
| 0:50 | Confirmation | Animated checkmark appears, booking details shown              |
| 0:55 | Back Home    | Click "Back to Home" → return to hero                         |

---

## 🚦 **Performance**

- **Load Time**: < 1.5 seconds
- **Memory Usage**: < 20 MB
- **Network**: Images from ImgBB and Unsplash CDNs

### **Optimizations** ⚡

- **Lazy loading** images with browser native
- **Efficient re-renders** via React hooks
- **CSS animations** instead of JavaScript for performance

---

## 🛡️ **Security Notes**

Little Lemon is a **safe** front-end demo application:

- ✅ No backend server
- ✅ No data storage (form submission simulated)
- ✅ No tracking or analytics
- ✅ No external dependencies beyond React

---

## 📝 **License**

MIT License — see LICENSE file for details.

---

## 🙏 **Acknowledgments**

- **Little Lemon** — Fictional restaurant from Meta Front-End Developer Certificate
- **Unsplash** — Restaurant interior and food photography
- **ImgBB** — Image hosting for specials and hero

---

## 📧 **Contact**

- **GitHub Issues**: [Create an issue](https://github.com/Willie-Conway/Little-Lemon-Restaurant-Reservation-System/issues)
- **Website**: https://willie-conway.github.io/Little-Lemon-Restaurant-Reservation-System/

---

## 🏁 **Future Enhancements**

- [ ] Add online ordering system
- [ ] Integrate with real reservation API
- [ ] Add table map visualization
- [ ] Include photo gallery
- [ ] Add menu categories (appetizers, mains, desserts)
- [ ] Implement multi-language support (Spanish, Polish, Italian)
- [ ] Add loyalty program signup
- [ ] Include Google Maps integration
- [ ] Add event calendar for special dinners
- [ ] Implement gift card purchase flow

---

<p align="center">
  <strong>🍋 Little Lemon — Mediterranean Restaurant Website 🍋</strong>
</p>

---

*Last updated: April 2026*
```