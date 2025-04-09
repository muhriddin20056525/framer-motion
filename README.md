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
| [6-dars Variants (Part-1)][6-dars]       |
| [7-dars Variants (Part-2)][7-dars]       |
| [8-dars Keyframes][8-dars]               |
| [9-dars Repeating Animations][9-dars]    |
| [10-dars Animate Presence][10-dars]      |

[1-dars]: https://github.com/muhriddin20056525/framer-motion?tab=readme-ov-file#1-dars-project-setup
[2-dars]: https://github.com/muhriddin20056525/framer-motion?tab=readme-ov-file#2-dars-animating-elements
[3-dars]: https://github.com/muhriddin20056525/framer-motion?tab=readme-ov-file#3-dars-initial-animation-state
[4-dars]: https://github.com/muhriddin20056525/framer-motion?tab=readme-ov-file#4-dars-transition-options
[5-dars]: https://github.com/muhriddin20056525/framer-motion?tab=readme-ov-file#5-dars-hover-animations
[6-dars]: https://github.com/muhriddin20056525/framer-motion?tab=readme-ov-file#6-dars-variants-part-1
[7-dars]: https://github.com/muhriddin20056525/framer-motion?tab=readme-ov-file#7-dars-variants-part-2
[8-dars]: https://github.com/muhriddin20056525/framer-motion?tab=readme-ov-file#8-dars-keyframes
[9-dars]: https://github.com/muhriddin20056525/framer-motion?tab=readme-ov-file#9-dars-repeating-animations
[10-dars]: https://github.com/muhriddin20056525/framer-motion?tab=readme-ov-file#10-dars-animate-presence

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

---

## **7-dars Variants (Part-2)**

```jsx
const containerVariants = {
  hidden: {
    opacity: 0,
    x: "-100vw",
  },
  visible: {
    x: 0,
    opacity: 1,
    transition: {
      type: "spring",
      mass: 0.4,
      damping: 8,
      when: "beforeChildren",
      staggerChildren: 2,
    },
  },
};

const childVariants = {
  hidden: {
    opacity: 0,
  },

  visible: {
    opacity: 1,
  },
};

<motion.div
  variants={containerVariants}
  initial="hidden"
  animate="visible"
  className="container order"
>
  <h2>Thank you for your order :)</h2>
  <motion.p variants={childVariants}>
    You ordered a {pizza.base} pizza with:
  </motion.p>

  <motion.div variants={childVariants}>
    {pizza.toppings.map((topping) => (
      <div key={topping}>{topping}</div>
    ))}
  </motion.div>
</motion.div>;
```

- `transition:`
  - `"spring"` - elastik harakat qiladi.
  - `mass: 0.4` - og‘irligi kam, tezroq harakatlanadi.
  - `damping: 8` - tebranishlarni kamaytirish uchun.
  - `when: "beforeChildren"` - avval asosiy konteyner ko‘rinadi, keyin bolalar (children).
  - `staggerChildren: 2` - har bir bola elementi orasida 2 soniya farq bo‘ladi.

---

## **8-dars Keyframes**

`Keyframes` – bu animatsiya davomida bir nechta oraliq qiymatlarni ketma-ket bajarish imkonini beruvchi usul.

```jsx
const buttonVariants = {
  visible: {
    x: [0, -20, 20, -20, 20, 0],
    transition: { delay: 2 },
  },

  hover: {
    scale: 1.1,
    textShadow: "0px 0px 8px rgb(255,255,255)",
    boxShadow: "0px 0px 8px rgb(255,255,255)",
  },
};

<motion.button variants={buttonVariants} animate="visible" whileHover="hover">
  Create Your Pizza
</motion.button>;
```

- `visible – tugma sahifaga chiqayotganda bajariladigan animatsiya`

  - `x: [0, -20, 20, -20, 20, 0]` → Keyframes animatsiya bo‘lib, tugma o‘zining joyidan chapga (`-20`), o‘ngga (`20`) tebranib, yana o‘z holatiga qaytadi.
  - `transition: { delay: 2 }` → Animatsiya 2 soniyadan keyin boshlanadi.

- `hover – foydalanuvchi sichqoncha bilan tugmaga kelganda ishlaydigan animatsiya`

  - `scale: 1.1` → Tugma kattalashadi (1.1 = 110%).
  - `textShadow` → Matn atrofida oq rangli porlash paydo bo‘ladi.
  - `boxShadow` → Tugma orqa foniga ham oq rangli porlash qo‘shiladi.

- `motion.button – animatsiyalangan tugma`
  - `variants={buttonVariants}` → Tugmaga oldindan belgilangan animatsiya variantlari biriktirilmoqda.
  - `animate="visible"` → Tugma sahifaga chiqayotganda "visible" holati bajarilyapti (chapga-o‘ngga tebranadi).
  - `whileHover="hover"` → Tugmaga sichqoncha olib borilganda "hover" holati ishlaydi (kattalashadi va porlaydi).

---

## **9-dars Repeating Animations**

`Repeating Animations` - deb bir animatsiyani bir necha marta takrorlashga aytiladi

```js
const buttonVariants = {
  hover: {
    scale: 1.1,
    textShadow: "0px 0px 8px rgb(255,255,255)",
    boxShadow: "0px 0px 8px rgb(255,255,255)",
    transition: {
      yoyo: 10,
    },
  },
};
<motion.button variants={buttonVariants} animate="visible" whileHover="hover">
  Create Your Pizza
</motion.button>;
```

- `transition`: Bu animatsiyaning qanday amalga oshishini aniqlaydi. Bu yerda `yoyo: 10` bo'lib, u animatsiyani `yoyo` effektida bajaradi. `yoyo` effekti — animatsiya tugmasi bir yo'nalishda ishlaganidan so'ng, orqaga qaytadi. `10` soni esa bu animatsiyaning qaytalanish sonini bildiradi. Ya'ni, tugma ustiga kursorni olib borish va olib chiqish jarayonida animatsiya `10` marta qayta takrorlanadi.

---

## **10-dars Animate Presence**

`AnimatePresence` — bu Framer Motion kutubxonasidagi juda foydali komponent bo‘lib, React'da komponentlar DOM'dan o‘chirilayotganda animatsiya berish uchun ishlatiladi.

```js
const [showTitle, setShowTitle] = useState(true);

setTimeout(() => {
  setShowTitle(false);
}, 4000);

<AnimatePresence>
  {showTitle && (
    <motion.h2 exit={{ x: 1000 }} transition={{ duration: 0.1 }}>
      Thank you for your order :)
    </motion.h2>
  )}
</AnimatePresence>;
```

- `<AnimatePresence>...</AnimatePresence>`
  - Bu Framer Motion komponenti.
  - Uning vazifasi: element DOM’dan o‘chib ketayotganda animatsiya qo‘shish.
- `<motion.h2 exit={{ x: 1000 }}>`
  - motion.h2 — bu animatsiyali <h2> elementi.
  - exit={{ x: 1000 }} — element DOM’dan o‘chayotganda 1000px o‘ng tomonga siljiydi.
  - transition={{ duration: 0.3 }} — bu harakat 0.3 soniya davom etadi.

---

## **11-dars Animating Routes**

```jsx
// App.js
const location = useLocation();
<AnimatePresence exitBeforeEnter>
  <Switch location={location} key={location.key}>
    <Route path="/base">
      <Base addBase={addBase} pizza={pizza} />
    </Route>
    <Route path="/toppings">
      <Toppings addTopping={addTopping} pizza={pizza} />
    </Route>
    <Route path="/order">
      <Order pizza={pizza} />
    </Route>
    <Route path="/">
      <Home />
    </Route>
  </Switch>
</AnimatePresence>;

// Home.js

const containerVariants = {
  hidden: {
    opacity: 0,
  },
  visible: {
    opacity: 1,
    transition: {
      delay: 1.5,
      duration: 1.5,
    },
  },

  exit: {
    x: "-100vw",
    transition: { ease: "easeInOut" },
  },
};

<motion.div
  variants={containerVariants}
  initial="hidden"
  animate="visible"
  exit="exit"
  className="home container"
></motion.div>;

// Base.js

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
  exit: {
    x: "-100vw",
    transition: { ease: "easeInOut" },
  },
};

<motion.div
  className="base container"
  variants={containerVariants}
  initial={"hidden"}
  animate={"visible"}
  exit="exit"
></motion.button>
```

**`App.js`:**

- `useLocation`: Bu React Router hooki bo'lib, hozirgi sahifa manzilini (URL) olishga yordam beradi. Sahifa o'zgarganda animatsiyalarni to'g'ri ishlatish uchun kerak.
- `AnimatePresence`: `framer-motion` komponenti bo'lib, sahifa o'zgarganda animatsiyalarni qo'llash imkonini beradi. `exitBeforeEnter` atributi bilan yangi sahifa faqat oldingi sahifa to'liq chiqib ketgandan keyin ko'rsatiladi.
- `Switch`: React Router komponenti bo'lib, URL manziliga mos keladigan komponentni ko'rsatadi.
- `Route`: Har bir URL manzili uchun mos komponentni render qiladi. Masalan: `/base`, `/toppings`, `/order` va boshqalar.
- `key={location.key}`: Har bir sahifa o'zgarganda animatsiya to'g'ri ishlashi uchun sahifaga o'ziga xos kalit beradi.

**`Home.js`:**

- `containerVariants`: Bu animatsiya variantlari bo'lib, sahifa ko'rinishini boshqaradi.
  - `hidden`: Sahifa boshlanishida ko'rinmas.
  - `visible`: Sahifa ko'rinadigan bo'lib, 1.5 soniya kechikish va 1.5 soniya davomida animatsiya qiladi.
  - `exit`: Sahifa chiqayotganda chapga siljiydi (`x: "-100vw"`).
- `motion.div`: Bu `framer-motion` tomonidan taqdim etilgan animatsiyalangan div elementidir. `variants` yordamida sahifani ko'rsatishda animatsiya variantlari qo'llanadi.

**`Base.js`:**

- `containerVariants`: Sahifa ko'rinishi uchun animatsiya variantlari.
  - `hidden`: Sahifa boshlanishida xususan, chapdan kiradi (`x: "-100vw"`) va `opacity: 0` bo'ladi.
  - `visible`: Sahifa ekranga kiritiladi va `spring` animatsiyasi bilan ko'rinish yaxshilanadi. `delay` bilan animatsiya kechikadi.
  - `exit`: Sahifa chiqayotganda chapga siljiydi.
- `motion.div`: Animatsiyalangan div, sahifa animatsiyalarini qo'llaydi.

**Natija:**

- Bu kod `framer-motion` kutubxonasidan va React Router'dan foydalanib, sahifalar o'rtasida animatsiyalarni qo'llash uchun ishlatiladi. Har bir sahifa uchun animatsiya variantlari belgilangan va sahifa o'zgarganda (URL manzili o'zgarganda) animatsiyalarni qo'llashga imkon beradi.
