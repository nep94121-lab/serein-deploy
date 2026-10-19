# Bàn giao Serein để deploy

## Bản có thể deploy

Thư mục `site/` là website tĩnh, đã chứa đủ bảy màn hình và hiệu ứng. Upload NỘI DUNG thư mục này làm thư mục gốc của website. File khởi đầu là `index.html`. Không cần chạy backend Doop, database hoặc MCP. Không cần build lại nếu giữ bản hiện tại.

- Entry: `site/index.html` — HTML, CSS và mã ứng dụng React đã gộp.
- Ảnh: `site/a/*.jpg` — đủ bảy ảnh lấy từ dữ liệu hiện tại.
- Runtime: `site/evaluation-vendor/*.js` — React, ReactDOM và component bundle.
- Font: DM Sans và Instrument Serif đang tải từ Google Fonts; muốn tự host font thì bổ sung ở bước triển khai.
- Route: `/#home`, `/#room`, `/#booking`, `/#experiences`, `/#dining`, `/#about`, `/#visit`. Đây là một ứng dụng với bảy màn hình, không phải bảy backend.

Các URL tài nguyên `http://localhost:4300/` đã đổi sang đường dẫn từ gốc website. Deploy ở domain/subdomain gốc; nếu dùng subfolder thì sửa asset base phù hợp. Phục vụ qua HTTP/HTTPS, không mở trực tiếp file://.

## Gửi nguyên đoạn này cho AI triển khai

> Deploy website Serein từ thư mục site trong gói này lên nền tảng hosting tĩnh tôi chọn. Publish directory là site, entry index.html, không cần lệnh build. Giữ đủ ảnh a/ và runtime evaluation-vendor/. Giữ nguyên thiết kế, bảy màn hình, hiệu ứng tự chạy, Pause và điều hướng. Các ảnh cần cùng origin hoặc CORS phù hợp để WebGL hoạt động. Đây là form demo: không xác nhận đặt phòng thật, không gửi email hay thanh toán. Nếu cần nghiệp vụ thật hãy triển khai riêng theo yêu cầu của tôi. Sau deploy, kiểm tra link, ảnh, WebGL fallback, Pause, các màn hình và giao diện mobile; gửi lại URL công khai. Chỉ xuất bản khi tôi đã cho phép nền tảng/đích triển khai.

## Giới hạn và giấy phép

Form hiện là demo, không có dịch vụ đặt phòng thật. Canvas và dây nối là công cụ thiết kế trong Doop, không phải phần giao diện khách truy cập; chúng không nằm trong bản deploy này. Giữ thông báo giấy phép React Bits trong REACT-BITS-LICENSE.md và các banner giấy phép trong runtime. Gói này không chứa cấu hình MCP, API key hay database. Bản đóng gói chưa được kiểm tra trên hosting công khai.

## Mã nguồn gốc trên máy hiện tại

- Web hiện tại: `C:\Users\LENOVO\Documents\Codex\2026-10-10\x20\work\doop-evaluation\public\serein-preview.html`
- Nguồn từng trang và CSS: `C:\Users\LENOVO\Documents\Codex\2026-10-10\x20\outputs\Canvas-Tool-Evaluation\upgrade\`
- Component và hiệu ứng: `C:\Users\LENOVO\Documents\Codex\2026-10-10\x20\work\doop-motion\`
- Ảnh đang sử dụng: `C:\Users\LENOVO\Documents\Codex\2026-10-10\x20\work\doop-evaluation\data\assets\`
- Thư viện chạy trong browser: `C:\Users\LENOVO\Documents\Codex\2026-10-10\x20\work\doop-evaluation\public\evaluation-vendor\`
- Template build: `C:\Users\LENOVO\Documents\Codex\2026-10-10\x20\outputs\Canvas-Tool-Evaluation\motion-probe.html`

Nếu sửa nguồn gốc: từ outputs/Canvas-Tool-Evaluation chạy lần lượt node upgrade/assemble.cjs rồi node upgrade/render-long.cjs. Sau đó chạy node upgrade/prepare-deploy.cjs để tạo lại bản bàn giao. Build nguồn gốc cần dependencies đã có trong work/doop-evaluation; site/ đã xuất không cần chúng.
