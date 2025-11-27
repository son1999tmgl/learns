# TailwindCSS - Tóm tắt nội dung chính cần học

## 1. **Cấu trúc và cách hoạt động của TailwindCSS**

* Utility-first CSS
* Class theo dạng công thức: `property-modifier` (vd: `text-lg`, `bg-blue-500`)
* Tích hợp vào dự án: CDN hoặc cấu hình build (PostCSS, Vite, Webpack,...)

---

## 2. **Các nhóm utility cơ bản**

### **Typography**

* Kích thước chữ: `text-xs` → `text-9xl`
* Độ đậm chữ: `font-light` → `font-black`
* Căn chỉnh: `text-left`, `text-center`, `text-right`, `text-justify`

### **Spacing (Margin & Padding)**

* `m-1`, `m-2`, `mx-4`, `my-6`
* `p-1`, `py-3`, `px-5`

### **Sizing**

* Width: `w-4`, `w-full`, `w-screen`
* Height: `h-10`, `h-full`, `h-screen`

### **Color System**

* Màu nền: `bg-red-500`
* Màu chữ: `text-gray-700`
* Màu viền: `border-blue-400`

### **Border & Radius**

* Viền: `border`, `border-2`, `border-gray-300`
* Bo góc: `rounded`, `rounded-lg`, `rounded-full`

### **Flexbox & Grid**

* `flex`, `flex-col`, `justify-center`, `items-center`
* Grid: `grid`, `grid-cols-3`, `gap-4`

### **Display**

* `block`, `inline-block`, `inline`, `hidden`

### **Positioning**

* `absolute`, `relative`, `top-0`, `left-0`

---

## 3. **Responsive Design**

* Prefix theo breakpoint:

  * `sm:` (>=640px)
  * `md:` (>=768px)
  * `lg:` (>=1024px)
  * `xl:` (>=1280px)
* Ví dụ:

  ```html
  <div class="text-sm md:text-lg lg:text-2xl">Hello</div>
  ```

---

## 4. **Hover, Focus và State Classes**

* `hover:bg-blue-600`
* `focus:outline-none`
* `active:scale-95`
* `disabled:opacity-50`

---

## 5. **Dark Mode**

* Kích hoạt trong config: `darkMode: 'class'`
* Sử dụng: `dark:bg-gray-900 dark:text-white`

---

## 6. **Custom trong `tailwind.config.js`**

* Thêm màu:

  ```js
  extend: {
    colors: {
      brand: '#1e40af'
    }
  }
  ```
* Thêm font, spacing, breakpoint
* Sử dụng `theme()`

---

## 7. **@apply – Tái sử dụng utility**

Dùng trong file CSS:

```css
.btn {
  @apply px-4 py-2 bg-blue-600 text-white rounded-lg hover:bg-blue-700;
}
```

---

## 8. **Handling States / Variants nâng cao**

* `group` & `group-hover`
* `peer` & `peer-focus`
* Ví dụ:

  ```html
  <div class="group">
    <p class="opacity-0 group-hover:opacity-100">Hover here</p>
  </div>
  ```

---

## 9. **Layout nâng cao**

* Container: `container`
* Aspect Ratio: `aspect-square`, `aspect-video`
* Columns: `columns-2`, `columns-3`

---

## 10. **Plugins**

* Typography plugin
* Forms plugin
* Line-clamp

Cài plugin:

```bash
npm install @tailwindcss/typography
```

Trong config:

```js
plugins: [require('@tailwindcss/typography')]
```

---

## 11. Debug & Productivity Tips

* Dùng `outline` hoặc `border` để debug layout
* Dùng VSCode + Tailwind IntelliSense
* Ưu tiên mobile-first
* Hạn chế lặp lại class → dùng component + @apply

---

# 🧩 Bài Tập Luyện TailwindCSS

Dưới đây là danh sách các bài tập từ cơ bản → nâng cao để luyện TailwindCSS hiệu quả.

---

## 🟩 **Mức Cơ Bản**

### **Bài 1 – Button cơ bản**
- Tạo button:
  - `bg-blue-500`, `text-white`
  - `px-*`, `py-*`
  - `rounded`
  - `hover:bg-blue-600`

### **Bài 2 – Card đơn giản**
- Tạo một card:
  - `bg-white`, `border`, `shadow`, `p-4`
  - Tiêu đề: `text-xl`
  - Mô tả: `text-sm`

### **Bài 3 – Responsive text**
- Áp dụng:
  - Mobile: `text-base`
  - md: `text-xl`
  - lg: `text-3xl`

---

## 🟨 **Mức Trung Bình**

### **Bài 4 – Flex căn giữa 2 chiều**
- Container cao ~300px
- Dùng: `flex items-center justify-center`

### **Bài 5 – Layout 2 cột responsive**
- Mobile: 1 cột
- lg: 2 cột
- `gap-4`

### **Bài 6 – Danh sách odd/even**
- odd → `bg-gray-100`
- even → `bg-gray-200`
- Hover → `bg-gray-300`

### **Bài 7 – Form có highlight (peer + focus)**
- Input có border
- focus → `border-blue-500`, `ring-2`
- Label xuất hiện khi input focus (dùng `peer-focus:*`)

---

## 🟧 **Mức Nâng Cao**

### **Bài 8 – Card có Dark Mode**
- Dùng:
  - `dark:bg-gray-800`
  - `dark:text-white`
- Áp dụng dark mode bằng class `dark` trên `<html>` hoặc `<body>`

### **Bài 9 – Dropdown bằng group-hover**
- Parent: thêm `group`
- Menu con:
  - Ẩn: `opacity-0 invisible`
  - Hiện khi hover cha: `group-hover:opacity-100 group-hover:visible`

### **Bài 10 – Button animation**
- Hover: đổi màu, `transition`
- Active: `scale-95`

---

## 🟥 **Mức Chuyên Sâu (Pro)**

### **Bài 11 – Responsive Navbar**
- Desktop: menu ngang
- Mobile: menu ẩn → mở bằng icon
- Dùng: `hidden md:flex`, `md:block`, variants `hover:` và `focus:`

### **Bài 12 – Pricing Table**
- 3 cards
- Card giữa nổi bật:
  - `scale-105`, `shadow-xl`, `border-blue-500`
- Responsive:
  - Mobile: 1 cột  
  - Desktop: 3 cột

### **Bài 13 – Mini Dashboard**
- Grid 4 ô
- Icon + text
- Hover: `shadow-lg`
- Dark mode
- Responsive:
  - Mobile: 1 cột  
  - md: 2 cột  
  - lg: 4 cột

---
