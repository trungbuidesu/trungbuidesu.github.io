# 🚀 Hướng Dẫn Deploy Lên GitHub Pages

## Tóm Tắt
Project React TypeScript + Vite của bạn đã được config sẵn để deploy lên GitHub Pages. Có 2 cách deploy:

---

## ✅ Cách 1: Tự Động Deploy với GitHub Actions (KHUYẾN NGHỊ)

### Bước 1: Push code lên GitHub
```bash
git add .
git commit -m "Initial commit: React TypeScript Vite app"
git push origin main
```

### Bước 2: Cấu hình GitHub Pages
1. Vào repository trên GitHub: `https://github.com/trungbuidesu/trungbuidesu.github.io`
2. Click vào **Settings** (tab ở trên)
3. Scroll xuống phần **Pages** (menu bên trái)
4. Ở phần **Build and deployment**:
   - **Source**: Chọn **GitHub Actions**
   - (Không cần chọn branch nào cả)
5. Save

### Bước 3: Chờ deploy tự động
- GitHub Actions sẽ tự động chạy workflow khi bạn push code
- Vào tab **Actions** để xem tiến trình
- Sau khi xong, site sẽ có tại: `https://trungbuidesu.github.io`

### Lần sau muốn update:
```bash
git add .
git commit -m "Update content"
git push origin main
```
→ Tự động deploy!

---

## 🔧 Cách 2: Deploy Thủ Công với gh-pages

### Bước 1: Deploy lần đầu
```bash
npm run deploy
```

Lệnh này sẽ:
1. Build project (`npm run build`)
2. Push folder `dist` lên branch `gh-pages`

### Bước 2: Cấu hình GitHub Pages
1. Vào repository trên GitHub
2. **Settings** → **Pages**
3. Ở phần **Build and deployment**:
   - **Source**: Chọn **Deploy from a branch**
   - **Branch**: Chọn `gh-pages` và folder `/ (root)`
4. Save

### Bước 3: Chờ vài phút
Site sẽ có tại: `https://trungbuidesu.github.io`

### Lần sau muốn update:
```bash
npm run deploy
```

---

## 📋 Checklist Trước Khi Deploy

- [ ] Đã chạy `npm install` thành công
- [ ] Đã test local với `npm run dev`
- [ ] Đã build thành công với `npm run build`
- [ ] Đã commit tất cả changes
- [ ] Đã push lên GitHub

---

## 🐛 Troubleshooting

### Site không hiển thị sau khi deploy?
1. Kiểm tra tab **Actions** xem có lỗi không
2. Đợi 2-3 phút cho GitHub xử lý
3. Clear cache browser (Ctrl + Shift + R)
4. Kiểm tra GitHub Pages settings đã đúng chưa

### Build bị lỗi?
```bash
# Xóa node_modules và install lại
rm -rf node_modules package-lock.json
npm install
npm run build
```

### Muốn test production build trước khi deploy?
```bash
npm run build
npm run preview
```
Mở `http://localhost:4173` để xem

---

## 📝 Lưu Ý Quan Trọng

1. **File .nojekyll**: Đã được tạo trong folder `public/` để GitHub Pages không xử lý như Jekyll site

2. **Base URL**: 
   - Hiện tại: `base: '/'` (cho user site: username.github.io)
   - Nếu là project site: Đổi thành `base: '/repo-name/'` trong `vite.config.ts`

3. **Branch chính**:
   - Workflow hiện tại trigger khi push lên branch `main`
   - Nếu branch chính của bạn là `master`, sửa trong `.github/workflows/deploy.yml`

---

## 🎉 Xong!

Sau khi deploy, site của bạn sẽ có tại:
### 🌐 https://trungbuidesu.github.io

Happy coding! 🚀
