# **FRAMER_MOTION**

- Framer Motion – bu React uchun kuchli animatsiya kutubxonasi.
- U oʻzgarishlar, holat oʻtishlari va gestlar (masalan, hover, drag) bilan ishlashni osonlashtiradi.
- CSS animatsiyalariga qaraganda silliqroq va optimallashtirilgan tarzda ishlaydi.
- Kod yozish oddiy: motion.div orqali har qanday elementga animatsiya qo‘shish mumkin.
- Next.js va React bilan to‘liq mos keladi va AnimatePresence orqali komponentlarni jonli o‘tishlarini boshqarish mumkin.

---

| Mundarija                                  |
| ------------------------------------------ |
| [1-dars Project Setup][1-dars]             |
| [2-dars 2-dars Animating Elements][2-dars] |

[1-dars]: https://github.com/muhriddin20056525/framer-motion?tab=readme-ov-file#1-dars-project-setup
[2-dars]: https://github.com/muhriddin20056525/framer-motion?tab=readme-ov-file#2-dars-animating-elements

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
