# Changelog — KTS AI Translator

Mọi thay đổi và cập nhật của bộ cài **KTS AI Translator** được ghi nhận tại đây.

---

## [1.0.0] - 2026-10-11

### ✨ Tính năng mới (Added)
- Hỗ trợ dịch bản vẽ AutoCAD 2025+ (`.NET 8`) cho `DBText`, `MText` và `Block Attribute` (chế độ **Song ngữ** hoặc **Ghi đè**).
- Tích hợp 3 Engine dịch thuật:
  1. **Google Translate (Free)**: Dịch trực tuyến miễn phí không cần API Key.
  2. **Groq API (Cloud LLM)**: Dịch thuật ngữ kỹ thuật bằng mô hình ngôn ngữ lớn đám mây.
  3. **LLamaSharp (100% Local Offline)**: Dịch ngoại tuyến bảo mật bằng mô hình `.gguf` (**Tencent Hy-MT2**, **Qwen 2.5**) với tùy chọn tăng tốc phần cứng **GPU (Vulkan)**.
- Tích hợp công cụ **Chuẩn hóa Text (`Merge MText`)** gom các dòng chữ rời rạc trước khi dịch.
- Tích hợp công cụ **Find & Replace** kèm **Zoom Highlight** trực tiếp trên vùng nhìn AutoCAD.
- Hệ thống **Từ điển cá nhân JSON (`dict_to_vi.json`, `dict_to_en.json`, `dict_to_zh-CN.json`)** tra cứu $O(1)$ và tự động bảo toàn ký hiệu kỹ thuật CAD (`GrammarMaskingService`).
