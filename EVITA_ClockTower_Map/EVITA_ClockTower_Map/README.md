# EVITA — ANIMATED HERO + ANCIENT RUINS 3D

Game Web 3D Three.js nâng cấp từ Coin Quest 3D. Nhân vật chính dùng model **Evita** do bạn cung cấp.

## Chạy game (không cần cài Node.js)
1. Giải nén ZIP đầy đủ (đừng chỉ mở file index.html lẻ).
2. Mở thư mục dự án bằng **Visual Studio Code**.
3. Cài **Live Server** (Ritwick Dey), nhấp chuột phải **index.html** -> **Open with Live Server**.
4. Trình duyệt Chrome/Edge hỗ trợ WebGL, Internet cần để tải thư viện Three.js từ CDN.

> Nếu nhấp đúp vào index.html bằng giao thức `file://`, trình duyệt có thể chặn tải file `.gltf` vì CORS. Hãy dùng Live Server hoặc `python -m http.server 5500` trong thư mục dự án rồi mở http://localhost:5500/.

## Điều khiển
- WASD / mũi tên: di chuyển; Space: nhảy.
- Q: lướt nhanh; E: lá chắn; R: sóng năng lượng (choáng quái).
- J: chém phép; F: cầu phép tự nhắm quái ở phía trước; T: thiên thạch diện rộng.
- Nhấn nút tương ứng trên HUD khi chơi bằng điện thoại.
- ✨ ở bên phải: bật/tắt hiệu ứng Bloom khi máy chậm.
- Nhặt 10 xu trong 120 giây để thắng; có 3 mạng, quái có thanh máu và hồi sinh.

## Cấu trúc
- `index.html`: toàn bộ mã giao diện, logic game và hiệu ứng (có chú thích tiếng Việt).
- `assets/evita/scene.gltf`, `scene.bin`, `textures/`: model nhân vật Evita, giữ nguyên cấu trúc phụ thuộc.
- `assets/evita/license.txt`: bản quyền của tác giả model.

## Hoạt ảnh xương (7 clip trong file GLTF)
Model gốc có rig nhưng không có animation. Phiên bản này **tạo và lưu 7 animation clip thực sự vào glTF**, kèm `animations.bin`: `Idle`, `Run`, `Jump`, `Slash`, `Cast`, `Dash`, `Hit`. Three.js `AnimationMixer` nội suy quaternion và chuyển cảnh bằng crossfade. Đây là hoạt ảnh tự thiết kế, **không phải motion capture** nên độ mượt/tự nhiên chưa đạt mức studio.

## Map 3D
- Đấu trường chơi mặc định trong bản đồ tự tạo **Ancient Forest Ruins**: nền đất tạo địa hình, tàn tích đá, cột, tháp, đá tảng, cây, bụi cỏ InstancedMesh, ánh nắng và sương mù.
- Để đưa map GLB khác vào game: vào màn chơi, nhấn **🗺 Chọn map GLB** (góc trên bên trái) và chọn file `.glb` trên máy. Game sẽ tự chỉnh kích thước và đặt model. Phần sàn chơi và va chạm vẫn theo sân đấu cũ, do model nhập tùy ý chưa có dữ liệu collision.
- **Lưu ý:** Trong hội thoại chưa có file map 3D khác đính kèm, chỉ có model Evita. Khi gửi map `.glb` thực tế, có thể tích hợp cố định và thêm collision tương ứng.

## Tối ưu đồ họa
Vật liệu Standard/PBR, texture sàn có bump, bóng PCFSoft 2K, fog chiều sâu, 3 nguồn sáng, hậu kỳ Bloom tùy chọn. Mức chân thực phụ thuộc GPU và chất lượng model, không phải đồ họa AAA.

## Ghi công model 3D (bắt buộc, CC BY 4.0)
This work is based on ["Evita (Arena Of Valor)"](https://sketchfab.com/3d-models/evita-arena-of-valor-45d00860ab204eee99a90d3dc45f4499) by [topomega3](https://sketchfab.com/topomega3) licensed under [CC BY 4.0](http://creativecommons.org/licenses/by/4.0/).

Ghi công này cũng hiển thị ngay trong game.


## Bản cập nhật mới

- Đã tích hợp sẵn map **Clock Tower Free Fire** từ file model bạn gửi.
- Game tự động tải map này khi mở trang.
- Vẫn giữ nút **🗺 Chọn map GLB** để thay map khác nếu muốn.
