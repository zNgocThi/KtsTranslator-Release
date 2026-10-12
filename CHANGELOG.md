# Changelog — KTS AI Translator

Nhật ký cập nhật và sửa lỗi các phiên bản phát hành của **KTS AI Translator**.

---

## [1.0.2] - 2026-10-12

### 🐛 Sửa lỗi & Nâng cấp Độ ổn định (Bug Fixes & Stability)
- **Khắc phục lỗi dịch Offline LLama (Tencent Hy-MT2 1.8B)**:
  - Loại bỏ hoàn toàn stop token `###` ngoại lai, tuân thủ đúng Jinja Chat Template nguyên bản của Tencent để chấm dứt tình trạng AI trả về kết quả rỗng.
  - Sửa lỗi nhận diện mã ngôn ngữ `zh-CN`, chuẩn hóa đầy đủ tên ngôn ngữ (`Vietnamese` / `越南语`).
  - Bảo toàn chuẩn xác các biến mask `{V0}`, `{V1}` bằng chỉ thị tự nhiên.
- **Cơ chế Bảo vệ Từng Cụm (Chunk Resilience)**:
  - Bọc khối kiểm soát lỗi độc lập cho từng cụm 8 từ: Nếu một cụm gặp sự cố (OOM, timeout hoặc ký tự lạ), hệ thống tự động fallback giữ nguyên văn bản gốc cho cụm đó và tiếp tục dịch bình thường các cụm còn lại, không làm gián đoạn toàn bộ bản vẽ.
- **Nâng cấp Thuật toán AutoDetect & Chống Trùng lặp**:
  - Nhận diện ký tự CJK (Hán tự) và dấu tiếng Việt thông minh; tự động bỏ qua nếu văn bản đã thuộc ngôn ngữ đích.
  - Chống nhân đôi dòng chữ trong chế độ song ngữ khi kết quả dịch trùng với bản gốc.
  - Tự động tách nhóm ngôn ngữ nguồn khi dùng chế độ `AutoDetect` với Google Translate và Groq API.
- **Cảnh báo Cấu hình Giao diện**:
  - Bổ sung banner cảnh báo trực quan khi chọn Groq (chưa có API Key) hoặc LLama Offline (chưa chọn file `.gguf`), kèm nút chuyển nhanh sang tab Thiết lập.

---

## [1.0.1] - 2026-10-12

### ✨ Tính năng mới & Cải tiến (What's New)
- **Chu trình Dịch liên tiếp (`KTS_TRANS`)**:
  - Bổ sung lệnh tắt **`KTS_TRANS`** (hoặc `KTS_TRANSLATE_SELECTION`): Quét chọn cụm 1 → Dịch ngay → Tự động chờ quét chọn cụm 2 mà không cần gõ lại lệnh. Nhấn `Enter` hoặc `ESC` để kết thúc.
  - Hỗ trợ phím lặp lệnh (`Space` hoặc `Enter`) để gọi lại lệnh nhanh chóng.
  - Bổ sung lệnh **`KTS_TRANSLATE_ALL`**: Dịch toàn bộ văn bản trong bản vẽ trực tiếp từ dòng lệnh CAD.
- **Ghi nhớ cấu hình Song ngữ**:
  - Tự động ghi nhớ tùy chọn **Dịch song ngữ**, giữ nguyên trạng thái giữa các phiên làm việc mà không cần chọn lại.
- **Tối ưu hóa hiệu năng & Thông báo**:
  - Tăng tốc độ thu thập và xử lý đối tượng dịch hàng loạt.
  - Báo cáo rõ ràng số lượng đối tượng dịch thành công ngay trên dòng lệnh CAD.

---

## [1.0.0] - 2026-10-11

### ✨ Phát hành lần đầu (Initial Release)
- Hỗ trợ dịch bản vẽ AutoCAD 2025+ (.NET 8) cho `DBText`, `MText` và `Block Attribute`.
- Tích hợp 3 Engine dịch thuật linh hoạt:
  - **Google Translate**: Dịch trực tuyến miễn phí, không cần tài khoản hay cấu hình.
  - **Groq API**: Dịch thuật ngữ kỹ thuật tốc độ cao qua Cloud LLM.
  - **LLamaSharp (Local Offline)**: Dịch ngoại tuyến bảo mật tuyệt đối với file model `.gguf` (Tencent Hy-MT2, Qwen 2.5), hỗ trợ tăng tốc GPU Vulkan.
- Công cụ **Chuẩn hóa Text (`KTS_NORMALIZE_TEXT`)**: Tự động gom cụm các dòng chữ rời rạc thành đoạn MText liền mạch trước khi dịch.
- Tùy chọn chế độ **Song ngữ** (giữ chữ gốc) hoặc **Ghi đè** trực tiếp.
- Tự động bảo toàn ký hiệu kỹ thuật CAD (`%%c`, `\P`, kích thước) và hỗ trợ từ điển cá nhân JSON tra cứu $O(1)$.
- Tìm kiếm & Thay thế (**Find & Replace**) kèm Zoom Highlight trên bản vẽ.
