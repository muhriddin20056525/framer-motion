# **FRAMER_MOTION**

- Framer Motion – bu React uchun kuchli animatsiya kutubxonasi.
- U oʻzgarishlar, holat oʻtishlari va gestlar (masalan, hover, drag) bilan ishlashni osonlashtiradi.
- CSS animatsiyalariga qaraganda silliqroq va optimallashtirilgan tarzda ishlaydi.
- Kod yozish oddiy: motion.div orqali har qanday elementga animatsiya qo‘shish mumkin.
- Next.js va React bilan to‘liq mos keladi va AnimatePresence orqali komponentlarni jonli o‘tishlarini boshqarish mumkin.

---

| Mundarija                                |
| ---------------------------------------- |
| [1-dars Project Setup][1-dars]           |
| [2-dars Animating Elements][2-dars]      |
| [3-dars Initial Animation State][3-dars] |
| [5-dars Hover Animations][5-dars]        |

[1-dars]: https://github.com/muhriddin20056525/framer-motion?tab=readme-ov-file#1-dars-project-setup
[2-dars]: https://github.com/muhriddin20056525/framer-motion?tab=readme-ov-file#2-dars-animating-elements
[3-dars]: https://github.com/muhriddin20056525/framer-motion?tab=readme-ov-file#3-dars-initial-animation-state
[4-dars]: https://github.com/muhriddin20056525/framer-motion?tab=readme-ov-file#4-dars-transition-options
[5-dars]: https://github.com/muhriddin20056525/framer-motion?tab=readme-ov-file#5-dars-hover-animations

---

## **1-dars Project Setup**

ushbu darsda loyiha yaratilib unga dizayn va funksionallik qo'shildi va keyingi darslarda `framer-motion` kutubxonasi orqali animatsiyalar qo'shishni o'rganib boramiz

```
npm install framer-motion
```

- `framer-motion` kutubxonasini o'rnatish

## **2-dars Animating Elements**

```jsx
import { motion } from "framer-motion";
<motion.h2 animate={{ fontSize: 50 }}>Welcome to Pizza Joint</motion.h2>;
```

- `import { motion } from "framer-motion";`

  - Bu Framer Motion kutubxonasidan `motion` komponentini import qiladi.
  - motion komponenti oddiy HTML teglarini animatsiya qilish uchun ishlatiladi.

- `<motion.h2>`

  - `h2` tegiga Framer Motion orqali animatsiya qo‘shiladi.

- `animate={{ fontSize: 50 }}`
  - `animate` xususiyati h2 elementini animatsiyalaydi.
  - `fontSize: 50` → `h2` elementining shrift o‘lchami `50px` ga o‘zgaradi.
  - Agar asosiy `h2` kichikroq o‘lchamga ega bo‘lsa, animatsiya orqali u kattalashadi.

```jsx
<motion.h2 animate={{ fontSize: 50, color: "#ff2994" }}>
  Welcome to Pizza Joint
</motion.h2>
```

- `animate={{ fontSize: 50, color: "#ff2994" }}`
  - `animate` objecti ichiga istalgancha css xossalar qo'shish mumkin

```jsx
<motion.h2 animate={{ fontSize: 50, color: "#ff2994", x: 100, y: -100 }}>
  Welcome to Pizza Joint
</motion.h2>
```

- `animate={{ ... }}`
  - `fontSize: 50` → Matn hajmi 50px bo‘ladi.
  - `color: "#ff2994"` → Matn rangi pushti (#ff2994) bo‘ladi.
  - `x: 100` → Element o‘ng tomonga 100px siljiydi.
  - `y: -100` → Element tepaga 100px siljiydi.

```jsx
<motion.button animate={{ scale: 1.5 }}>Create Your Pizza</motion.button>
```

- `<motion.button>`

  - Oddiy `<button>` emas, balki Framer Motion yordamida animatsiyalangan tugma.
  - Framer Motion `motion.button` orqali tugmani harakatlantirish, kattalashtirish yoki boshqa effektlar qo‘shish imkonini beradi.

- `animate={{ scale: 1.5 }}`
  - `scale: 1.5` → Tugmaning o‘lchami 1.5 barobar kattalashadi (asl hajmidan 50% kattaroq bo‘ladi).
  - Framer Motion tugmani avtomatik ravishda animatsiyalaydi, ya’ni boshlang‘ich `(scale: 1.0)` holatdan 1.5 ga o‘tadi.

---

## **3-dars Initial Animation State**

```jsx
<motion.div className="title" initial={{ y: -250 }} animate={{ y: -10 }}>
  <h1>Pizza Joint</h1>
</motion.div>
```

- `initial={{ y: -250 }}` – initial xossasi komponentning dastlabki holatini belgilaydi.

  - Bu yerda `{ y: -250 }` animatsiyaning boshlang‘ich o‘rnini bildiradi, ya’ni `<div>` sahifaning yuqori qismidan `250px` tashqarida joylashgan bo‘ladi.

- `animate={{ y: -10 }} `– animate xossasi komponent qanday harakatlanishini bildiradi.
  - `{ y: -10 }` bu elementni -10px koordinataga olib keladi, ya’ni u sahifaning yuqori qismidan pastga tushadi, lekin biroz yuqorida qoladi.

```tsx
<motion.div className="next" initial={{ x: "-100vw" }} animate={{ x: 0 }}>
  <Link to="/toppings">
    <button>Next</button>
  </Link>
</motion.div>
```

- Dastlab komponent ekrandan tashqarida (`x: "-100vw", ya’ni butun ekran kengligi bo‘ylab chapga siljigan`).
- Animatsiya orqali `x: 0` ga harakatlanadi, ya’ni ekranga kirib keladi

---

## **4-dars Transition Options**

`transition` Framer Motion da animatsiyaning davomiyligi, kechikishi va tezlashishini boshqarish uchun ishlatiladi.

```jsx
<motion.div
  className="home container"
  initial={{ opacity: 0 }}
  animate={{ opacity: 1 }}
  transition={{ delay: 1.5, duration: 1.5 }}
>
  <motion.h2>Welcome to Pizza Joint</motion.h2>
  <Link to="/base">
    <motion.button>Create Your Pizza</motion.button>
  </Link>
</motion.div>
```

- `transition={{ delay: 1.5, duration: 1.5 }}` – Animatsiya `1.5` soniya kechikib boshlanadi va `1.5` soniya davom etadi.
  - `delay` Animatsiya boshlanishidan oldin qancha kechikishini belgilaydi.
  - `duration` Animatsiya qancha davom etishini (sekundda) belgilaydi.
  - `ease` Animatsiyaning tezlashish va sekinlashish usulini belgilaydi.
  - `type` Animatsiya turini belgilaydi (spring, tween, keyframes).

```jsx
<motion.div
  className="title"
  initial={{ y: -250 }}
  animate={{ y: -10 }}
  transition={{ delay: 0.2, type: "tween" }}
></motion.div>
```

- `type: "tween"` – Harakat barqaror tezlik bilan sodir bo‘ladi (prujinali tebranishsiz).
- `type: "spring"` animatsiya tabiiy prujina effekti bilan bajarilardi.

```jsx
<motion.div
  className="title"
  initial={{ y: -250 }}
  animate={{ y: -10 }}
  transition={{ delay: 0.2, type: "spring", stiffness: 500 }}
></motion.div>
```

- `stiffness: 500` - Prujina juda qattiq, tez va keskin harakat qiladi.
  - `stiffness: 100` – Sekin va yumshoq tushadi.
  - `stiffness: 500` – Juda tez va kuchli harakat qiladi.
  - `stiffness: 1000` – Juda qattiq va deyarli tebranishsiz tushadi.

---

## **5-dars Hover Animations**

```jsx
<motion.button whileHover={{ scale: 1.1 }}>Create Your Pizza</motion.button>
```

- `whileHover={{ scale: 1.1 }}` – Tugma ustiga sichqoncha olib borilganda (`hover holati`) `1.1` marta kattalashadi.

```jsx
<motion.li
  whileHover={{ scale: 1.3, color: "#f8e112", originX: 0 }}
  transition={{ type: "spring", stiffness: 300 }}
>
  <span>{topping}</span>
</motion.li>
```

- `whileHover={{ ... }}` – Bu qism `hover` qilinganda (sichqoncha ustiga olib borilganda) qanday animatsiya bo‘lishini belgilaydi:

  - `scale: 1.3` → Element 1.3 baravar kattalashadi.
  - `color: "#f8e112"` → Matn sariq rangga o‘zgaradi.
  - `originX: 0` → Animatsiya chap tomondan boshlanadi (standart qiymat 0.5, ya’ni markazdan).

- `transition={{ type: "spring", stiffness: 300 }}` – Bu qism animatsiya qanday ishlashini belgilaydi:
  - `type: "spring"` → Harakat tabiiy prujina (spring) effektida bo‘ladi.
  - `stiffness: 300` → Prujina qanchalik qattiq ekanligini belgilaydi (qiymat qanchalik katta bo‘lsa, animatsiya shuncha tez bo‘ladi).

---

## **6-dars Variants (Part-1)**

`variants` – bu Framer Motion da animatsiyani boshqarish uchun ishlatiladigan obyekt. U animatsiya holatlarini (boshlang‘ich, yakuniy va boshqa oraliq holatlar) o‘z ichiga oladi.

```jsx
const containerVariants = {
  hidden: {
    opacity: 0,
    x: "-100vw",
  },
  visible: {
    x: 0,
    opacity: 1,
  },
};

<motion.div
  className="base container"
  variants={containerVariants}
  initial={"hidden"}
  animate={"visible"}
  transition={{ type: "spring", delay: 0.5 }}
></motion.div>;
```

- `hidden` – element boshida ekranning chap tomonidan (`-100vw, butun ekran kengligi`) tashqarida bo'ladi va ko'rinmaydi (`opacity: 0`).
- `visible` – element o'z o'rniga (`x: 0`) keladi va to'liq ko'rinadi (`opacity: 1`).

- `variants={containerVariants}`
  - `containerVariants` obyektidagi animatsiya holatlarini ishlatadi.
- `initial={"hidden"}`
  - Element boshlang'ichda hidden holatda bo'ladi (ya'ni ekranda ko'rinmaydi va chap tomonda).
- `animate={"visible"}`
  - Animatsiya boshlangandan keyin visible holatiga o'tadi (ya'ni ekranga chiqadi).
- `transition={{ type: "spring", delay: 0.5 }}`
  - Animatsiya `"spring"` (prujinali) turida amalga oshiriladi va `0.5` soniya kechikish bilan boshlanadi.

```jsx
const containerVariants = {
  hidden: {
    opacity: 0,
    x: "-100vw",
  },
  visible: {
    x: 0,
    opacity: 1,
    transition: { type: "spring", delay: 0.5 },
  },
};

<motion.div
  className="base container"
  variants={containerVariants}
  initial={"hidden"}
  animate={"visible"}
></motion.div>;
```

- `transition` - xossasini varants ichiga qo'shib undan foydalanish
- `animate={"visible"}` - `transition` objecti `visible` objecti ichida ochilgani uchun `motion.div` ga alohida `transition` kalitini ko'rsatib `variants` ga murojaat qilish shart emas

```jsx
const containerVariants = {
  hidden: {
    opacity: 0,
    x: "-100vw",
  },
  visible: {
    x: 0,
    opacity: 1,
    transition: { type: "spring", delay: 0.5 },
  },
};

const nextVariants = {
  hidden: {
    x: "-100vw",
  },
  visible: {
    x: 0,
  },
  transition: {
    type: "spring",
    stiffness: 120,
  },
};

<motion.div
  className="base container"
  variants={containerVariants}
  initial={"hidden"}
  animate={"visible"}
>
  <motion.div className="next" variants={nextVariants}></motion.div>
</motion.div>;
```

- `containerVariants` va `nextVariants` ning xossali `hidden` va `visible` bir xil nomlangani va `next` classiga ega `motion.div` farzand element bo'lgani hisobiga otasidan meros oladi shuning uchun unga qaysi `variants` dan foydalanish kerakligini ko'rsatishni o'zi yetarli. `initial` va `animate` xossalari esa bu vaziyatda kerak emas
