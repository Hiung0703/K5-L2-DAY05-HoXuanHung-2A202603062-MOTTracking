# Báo cáo cá nhân — HoXuanHung-2A202603062

Đoạn video: MOT17-09, 150 frame (frame 1–150), nguồn MOTChallenge, giấy phép CC BY-NC-SA 3.0.

## 0. Thông tin học viên

- Họ tên: HỒ XUÂN HÙNG
- MSSV: 2A202603062
- Mã đề (A/B/C): B
- Email: 26ai.hunghx@vinuni.edu.vn
- Link repository: https://github.com/Hiung0703/K5-L2-HoXuanHung-2A202603062-MOTTracking
- Giờ bắt đầu: 13/11/2026 16:00 (GMT+7; theo thông tin bạn cung cấp)
- Giờ kết thúc: Dự kiến 14/11/2026 12:00 (GMT+7); cập nhật giờ thực tế sau khi hoàn tất.

## 1. Xem trước đoạn video (CP0)

Ghi **trước khi vẽ**, mỗi người một dòng. Các mốc xuất hiện/cuối thấy dưới đây được trích từ export hiện có; hãy xác nhận chúng khớp với quan sát thực tế của bạn. Các ghi chú xem trước chưa có trong file export nên vẫn cần bạn bổ sung.

Quy đổi frame: CVAT frame 0 là ảnh `000001.jpg`; CVAT frame `f` tương ứng ảnh `0000(f+1).jpg`. Ví dụ: frame 43 = `000044.jpg`, frame 44 = `000045.jpg`, frame 54 = `000055.jpg`, frame 97 = `000098.jpg`, frame 108 = `000109.jpg`, frame 111 = `000112.jpg`, frame 124 = `000125.jpg`, frame 136 = `000137.jpg`, frame 140 = `000141.jpg`.

| Mã | Frame xuất hiện | Frame cuối thấy được | Rẽ / dừng / đổi tốc độ ở frame | Bị che ở frame | Ghi chú |
|---|---|---|---|---|---|
| P1 | 0 | 149 | | 30–41 và 44–50 (occluded); export thiếu box 42–43 | Mốc từ export; ảnh `000044.jpg` (frame 43) vẫn thấy người này trong cảnh nhưng không có box — cần rà/sửa nhãn, không xem đây là mất dấu do bị che |
| P2 | 0 | 149 | | | Mốc từ export; xác nhận tên P2 và quan sát trước khi vẽ |
| P3 | 39 | 149 | | | Mốc từ export; xác nhận tên P3 và quan sát trước khi vẽ |
| P4 | 0 | 147 | | | Mốc từ export; xác nhận tên P4 và quan sát trước khi vẽ |
| P5 | 1 | 139 | | | Mốc từ export; xác nhận tên P5 và quan sát trước khi vẽ |

### Đối chiếu trực quan các ảnh CVAT bạn gửi

Đây là kiểm tra các ảnh chụp rời, không phải xem lại toàn bộ 150 frame. Số trong cột “frame CVAT” bắt đầu từ 0; tên ảnh luôn lớn hơn số frame một đơn vị.

| Track hiển thị trên ảnh | Người có thể nhận diện trong các ảnh mẫu | Quan sát từ các frame mẫu | Mức chắc chắn / việc cần rà |
|---|---|---|---|
| P1 | Người đàn ông mặc áo khoác đen, áo trong đỏ, quần sáng màu và bốt đen | Có mặt ở ảnh `000044.jpg`, `000045.jpg`, `000055.jpg`; trong các ảnh này đang đi về phía trái khung hình. Ở ảnh `000045.jpg`, box có nét đứt/nhãn occlusion theo giao diện. | Nhận dạng trong các ảnh mẫu khá rõ; cần rà liên tục các frame quanh 30–55 vì export ghi trạng thái che/mất ở đoạn này. |
| P2 | Có ảnh cho thấy nhãn P2 gắn với người đàn ông áo polo xanh, quần xám, đội mũ sáng màu | Nhìn rõ ở `000044.jpg`, `000112.jpg`, `000125.jpg`, `000137.jpg`, `000141.jpg`; người này tiến gần camera nên kích thước box tăng và bị cắt một phần ở mép trên trong vài ảnh. | Cần kiểm tra lại đoạn `000044.jpg`–`000055.jpg`: vị trí chữ/box P2 và P5 chồng lấn, nên ảnh rời chưa đủ để khẳng định ID nhất quán. |
| P3 | Trẻ nhỏ mặc váy sáng màu, giày hồng/đỏ | Xuất hiện ở các ảnh từ `000044.jpg`/`000045.jpg` đến `000141.jpg`; thường ở phía sau người lớn và có lúc bị che một phần. Box rất nhỏ nên cần theo dõi kỹ khi người lớn đi ngang phía trước. | Hình dáng/trang phục giúp nhận diện trong các ảnh mẫu; cần rà những frame bị che để xác nhận không mất track hoặc đổi ID. |
| P4 | Một phụ nữ ở phía sau, mặc áo hồng và quần tối/xanh | Nhìn thấy ở `000044.jpg`–`000055.jpg`; về sau có các box nét đứt/box nhỏ nằm trong vùng bị người đi trước che ở `000125.jpg` và `000137.jpg`. | Chưa thể xác nhận các box về sau có còn theo đúng người phụ nữ này hay không; cần mở trực tiếp các frame và so vị trí, hướng đi trước/sau vùng che. |
| P5 | Một phụ nữ lớn tuổi, tóc ngắn bạc, áo khoác xanh lá, quần tối màu, mang túi đen | Nhìn rõ ở `000044.jpg`, `000045.jpg`, `000098.jpg`, `000108.jpg`, `000112.jpg`; di chuyển về phía camera. | Nhãn P5/P2 có vẻ chồng lấn hoặc đổi vị trí trong một số ảnh đầu; chưa kết luận ID switch từ ảnh chụp rời. Hãy rà trực tiếp vùng `000044.jpg`–`000055.jpg` và đối chiếu track trên CVAT. |

**Điểm cần rà trước khi chốt báo cáo:** ảnh `000044.jpg`/`000045.jpg` và `000055.jpg` có nhãn P2/P5 gần nhau, trong khi ở các ảnh muộn hơn P2 nhìn thấy trên người đàn ông áo xanh. Kiểm tra từng track trong CVAT tại các frame 43–55 để xác nhận box nào thuộc người phụ nữ áo xanh lá và box nào thuộc người đàn ông áo xanh. Đây là dấu hiệu cần kiểm tra, chưa phải kết luận có lỗi ID.

## 2. Keyframe và thời gian (CP1, CP4)

Số keyframe lấy từ kết quả `src/check_submission.py`.

Thời gian làm từng người và “chỗ khó” không có trong file export hay ảnh chụp, nên chưa điền để tránh tự đặt số liệu. Cần ghi theo thời gian/quan sát thực tế của học viên.

| Mã | Số keyframe | Keyframe ở frame | Số frame có mặt | Keyframe / 100 frame | Thời gian (phút) | Chỗ khó |
|---|---|---|---|---|---|---|
| P1 | 27 | 0, 19, 30, 35, 44, 51, 55, 66, 81, 91, 99, 105, 110, 111, 112, 113, 115, 125, 129, 130, 132, 138, 141, 142, 143, 144, 148 | 148 | 18,2 | | |
| P2 | 34 | 0, 4, 17, 21, 23, 26, 27, 28, 29, 30, 31, 33, 40, 49, 59, 68, 83, 88, 92, 96, 98, 108, 117, 119, 123, 130, 131, 133, 134, 135, 136, 138, 144, 149 | 150 | 22,7 | | |
| P3 | 13 | 39, 58, 75, 84, 93, 100, 108, 114, 119, 123, 130, 137, 145 | 111 | 11,7 | | |
| P4 | 9 | 0, 10, 18, 23, 27, 106, 135, 140, 143 | 124 | 7,3 | | |
| P5 | 7 | 1, 9, 29, 47, 97, 103, 123 | 123 | 5,7 | | |
| **Tổng** | **90** | | **656** | **13,7** | | |

Keyframe / 100 frame của cả bài = tổng keyframe ÷ tổng số frame có mặt × 100 = 90 ÷ 656 × 100 = **13,7**.

Ghi chú: Export CVAT không lưu tên P1–P5; bảng trên đối chiếu thứ tự track với mã đề B và vị trí tham chiếu trong `src/lab_variants.json`.

Bạn đặt keyframe nhiều nhất ở người nào? Vì sao (người đó rẽ, dừng, lại gần camera hay bị che)?

...

## 3. Đoạn bị che (CP2)

Người bị che: `P1` (đối chiếu theo mã đề B; xác nhận trực quan)

| Mốc | Frame |
|---|---:|
| Bắt đầu bị che một phần (bật `occluded`) | 30 |
| Mất hẳn (bật `outside`) | 42 |
| Hiện lại (tắt `outside`) | 44 |
| Thấy rõ trở lại (tắt `occluded`) | 51 |

- Theo export, track P1 bật `outside` ở frame 42 và không có box ở frame 43; track xuất hiện lại ở frame 44. Tuy nhiên, ảnh `000044.jpg` (CVAT frame 43) cho thấy người đàn ông áo khoác đen vẫn hiện rõ ở phía trái cảnh, nhưng chưa có box. Đây có vẻ là nhãn bị mất ít nhất tại frame 43, không phải bằng chứng người đó bị khuất hoàn toàn; cần mở CVAT và thêm/sửa box trước khi chốt điểm.
- Khoảng thiếu box trong export: 2 frame (42–43), tương đương khoảng 0,07 giây ở 30 fps. Chỉ frame 43 được đối chiếu trực tiếp bằng ảnh bạn gửi; chưa có ảnh `000043.jpg` để kết luận tình trạng ở frame 42.
- Export nối lại cùng track/ID sau khoảng thiếu; đây là quyết định hiện có trong nhãn, chưa xác nhận đúng bằng cách xem lại toàn bộ chuyển động.
- Lý do giữ cùng ID (cần bạn xác nhận sau khi rà CVAT: ngoại hình có khớp, thời gian gián đoạn so với ngưỡng 60 frame, hướng và tốc độ tại lúc xuất hiện lại):

...

Ảnh minh chứng CP2: chưa có ảnh nào được lưu trong `report/individual/images/`. Cần bổ sung ảnh trước khi che, ảnh giữa đoạn che thấy cờ `occluded` trên panel object, và ảnh sau khi hiện lại thấy cùng ID. Ảnh `000044.jpg` bạn gửi trong hội thoại chỉ dùng để nhận ra box P1 đang thiếu ở frame 43; ảnh này chưa được đưa vào repo.

## 4. Tự review ID (CP3)

Lượt 1 theo người (đi ngược từ frame 149 về 0 trên CVAT), lượt 2 theo cảnh (nhảy 10 frame). Ít nhất 3 dòng; không có lỗi thì ghi một dòng "đã kiểm hai lượt, không lỗi".

Loại lỗi dùng đúng một trong 7 mã: `id_switch`, `fragmentation`, `lost`, `merge`, `false_track`, `drift`, `flag`.

| Frame | Mã người | Loại lỗi | Mô tả một câu | Phát hiện ở lượt | Đã sửa? |
|---:|---|---|---|---|---|
| | | | | | |
| | | | | | |
| | | | | | |

Tổng hợp số lỗi theo loại:

| `id_switch` | `fragmentation` | `lost` | `merge` | `false_track` | `drift` | `flag` |
|---:|---:|---:|---:|---:|---:|---:|
| | | | | | | |

Lỗi nào chỉ lượt 2 (theo cảnh) mới thấy, lượt 1 (theo người) không thấy? Vì sao?

...

## 5. File xuất và kết quả tự kiểm (CP4)

| Kiểm tra | Kết quả |
|---|---|
| Tên file MOT 1.1 | `src/exports/HoXuanHung_mot.zip` |
| Tên file CVAT for video 1.1 | `src/exports/HoXuanHung_cvat_video.zip` |
| Số track ID khác nhau trong `gt/gt.txt` (phải là 5) | 5 |
| Frame `outside` không có dòng trong `gt.txt` (đúng / sai) | Đúng; track 1 vắng ở frame CVAT 42–43 |
| Job đã completed trên CVAT máy cá nhân | Job #20 (Task #21) ở `in progress` lần kiểm tra ngày 13/11/2026; cần kiểm tra lại trạng thái hiện tại |

Dán phần tóm tắt in ra từ `src/check_submission.py`:

```text
Số frame in theo CVAT (bắt đầu từ 0). Trong gt.txt, frame_id = frame CVAT + 1.

=== File MOT 1.1: HoXuanHung_mot.zip ===
Số track ID: 5 | Tổng số box: 656
[OK] Đúng 5 track ID.

=== File CVAT for video 1.1: HoXuanHung_cvat_video.zip ===
Đọc được 5 track từ annotations.xml.
Tổng: 90 keyframe / 656 frame có mặt = 13.7 keyframe / 100 frame

=== Tóm tắt ===
Lỗi: 0 | Cảnh báo: 0
Đạt. Dán phần tóm tắt này vào báo cáo mục 5.
```

## 6. Ba câu kết

1. Nếu được gán lại, bạn sẽ đặt keyframe khác ở đâu? Vì sao?

   ...

2. Có chỗ nào bạn không chắc "cùng ID hay ID mới"? Bạn đã quyết định và ghi chú thế nào?

   ...

3. Một lỗi ID trong job của bạn (nếu không còn sót, chọn lỗi đã sửa) có thể làm xe tự lái dự đoán sai chuyển động của người đó như thế nào? Lỗi đó ảnh hưởng MOTA hay IDF1 nhiều hơn?

   ...

## Bonus (nếu làm)

### B1 — Hai người đi sát

...

### B2 — So cách đặt keyframe

| Cách đặt | Số keyframe | Frame trôi nhất | Ghi chú |
|---|---:|---:|---|
| Đều mỗi 30 frame | | | |
| Theo chỗ đổi hướng | | | |

...

### B3 — So với tracker có sẵn

| Frame | Mã người | Tracker làm gì | Nhãn của bạn | Giải thích (đoán rồi sửa / ghép IoU / box score thấp / ngoại hình) |
|---:|---|---|---|---|
| | | | | |
| | | | | |

## 7. Tài liệu tham khảo và công cụ AI đã dùng

Nguồn dữ liệu: MOT17-09, MOTChallenge (Milan et al., 2016), giấy phép CC BY-NC-SA 3.0.

ChatGPT được dùng để chạy/giải thích script tự kiểm và hỗ trợ hoàn thiện báo cáo. Không dùng AI để tạo box/track; mục tự review và ba câu kết cần học viên tự viết dựa trên quá trình làm bài.
