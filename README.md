# 🕸️ KTS AI TRANSLATOR — Plugin Dịch Thuật Bản Vẽ AutoCAD 2025+

> **Tác giả**: Ngọc Thi (`@zNgocThi`)  
> **Nền tảng**: AutoCAD 2025 trở lên (Windows 64-bit, `.NET 8`)  
> **Giấy phép**: Freeware (`© 2026 Ngọc Thi. All Rights Reserved`)

---

## 📥 Tải Về Phiên Bản Mới Nhất (Download)

👉 **[Tải bộ cài KTS AI Translator tại mục Releases](../../releases/latest)**

*(Bộ cài nén `.rar` bao gồm: File tự cài đặt `.exe`, `UnInstall - Kts AI Translator.bat` và `Huong dan.txt`).*

---

## ✨ Tính Năng Nổi Bật

1. **Hỗ trợ 3 Engine Dịch Thuật Linh Hoạt**:
   - **Google Translate (Free)**: Dùng ngay lập tức sau khi cài đặt (cần kết nối Internet), không cần tài khoản hay API Key.
   - **Groq API (Cloud LLM)**: Dịch thuật ngữ kỹ thuật Kiến trúc - Xây dựng - MEP tốc độ cao bằng các mô hình LLM đám mây.
   - **LLamaSharp (100% Local Offline)**: Dịch hoàn toàn trên máy tính cá nhân bằng file mô hình `.gguf` (**Tencent Hy-MT2**, **Qwen 2.5**), bảo mật tuyệt đối bản vẽ dự án, hỗ trợ tăng tốc phần cứng **GPU (Vulkan)**.
2. **Chuẩn Hóa Text Thông Minh (`Merge MText`)**:
   - Tự động gom cụm các dòng chữ rời rạc (`DBText`) nằm gần nhau thành một đoạn `MText` hoàn chỉnh trước khi dịch để câu văn liền mạch, đúng ngữ cảnh kỹ thuật.
3. **Bảo Toàn Ký Hiệu Kỹ Thuật CAD & Từ Điển Cá Nhân $O(1)$**:
   - Tự động nhận diện và giữ nguyên các mã điều khiển CAD (`%%c`, `\P`, kích thước, ký hiệu trục/cốt cao độ).
   - Cho phép lưu thuật ngữ chuyên ngành riêng vào từ điển JSON (`dict_to_vi.json`, `dict_to_en.json`, `dict_to_zh-CN.json`) để tra cứu tức thì $O(1)$.
4. **Hỗ Trợ Chế Độ Song Ngữ (Bilingual) & Ghi Đè (Replace)**:
   - Tùy chọn giữ nguyên chữ gốc kèm bản dịch song ngữ hoặc thay thế trực tiếp trên `DBText`, `MText` và `Block Attribute`.

---

## 🚀 Hướng Dẫn Cài Đặt Nhanh

1. Tải file `.rar` tại mục **[Releases](../../releases/latest)** và **giải nén** ra một thư mục trên máy tính.
2. **Đóng AutoCAD** (nếu đang mở), chạy file **`[KTS] AI TRANSLATOR ... .exe`** và bấm **Install** để tự động cài đặt vào AutoCAD.
3. Mở AutoCAD 2025+, gõ lệnh:
   ```text
   KTS_TRANSLATOR
   ```
   để bật bảng điều khiển **KTS AI Translator**.
4. **Gỡ cài đặt (khi cần)**: Đóng AutoCAD và chạy file `UnInstall - Kts AI Translator.bat`.

---

## ⌨️ Các Lệnh AutoCAD (Commands)

- **`KTS_TRANS`** hoặc **`KTS_TRANSLATE_SELECTION`**: Dịch văn bản theo vùng chọn với cơ chế **chọn liên tiếp (Continuous Selection Loop)** — Quét chọn cụm 1 -> Dịch ngay -> Tiếp tục chọn cụm 2 mà không cần gõ lại lệnh (nhấn `Enter` hoặc `ESC` khi kết thúc; hỗ trợ phím `Space`/`Enter` để lặp lại lệnh).
- **`KTS_TRANSLATE_ALL`**: Dịch toàn bộ văn bản trong bản vẽ hiện hành.
- **`KTS_TRANSLATOR`**: Mở bảng điều khiển giao diện (PaletteSet) KTS AI Translator.
- **`KTS_NORMALIZE_TEXT`**: Tự động gom cụm các Text rời rạc thành đoạn MText chuẩn hóa trước khi dịch.

---

## 🎬 Video Hướng Dẫn & Cài Đặt

1. **Giới thiệu Plugin KtsTranslator**: [▶ Xem trên YouTube](https://youtu.be/gF5LcHtNmrs)
2. **Hướng dẫn sử dụng API Key (Groq / OpenRouter)**: [▶ Xem trên YouTube](https://youtu.be/n4cqwEUEfb8)
3. **Giới thiệu mô hình AI Offline (Local LLM `.gguf`)**: [▶ Xem trên YouTube](https://youtu.be/8x9msDShIbo)

---

## 📜 Bản Quyền & Ghi Nhận Mã Nguồn Mở

- **© 2026 Ngọc Thi. All Rights Reserved (Freeware).**
- **Open-Source (MIT License)**: Powered by `LLamaSharp`, `llama.cpp`, `.NET Foundation` & Microsoft Libraries. Chi tiết xem tại [`LICENSE.txt`](LICENSE.txt).
- *AutoCAD® is a registered trademark of Autodesk, Inc.*
