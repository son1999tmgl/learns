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