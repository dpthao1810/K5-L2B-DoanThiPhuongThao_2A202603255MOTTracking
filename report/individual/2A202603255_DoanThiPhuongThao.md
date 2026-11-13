# Báo cáo cá nhân — DoanThiPhuongThao_2A202603255


Đổi tên file theo quy tắc `MSSV_HoTen.md`. Ví dụ: `20241234_NguyenVanAn.md`.

Đoạn video: MOT17-09, 150 frame (frame 1–150), nguồn MOTChallenge, giấy phép CC BY-NC-SA 3.0.

## 0. Thông tin học viên

- Họ tên: Doãn Thị Phương Thảo
- MSSV: 2A202603255
- Mã đề (A/B/C): B
- Email: dthao18102004@gmail.com
- Link repository: https://github.com/dpthao1810/K5-L2B-DoanThiPhuongThao_2A202603255MOTTracking.git
- Giờ bắt đầu: 16h00
- Giờ kết thúc: 18h30

## 1. Xem trước đoạn video (CP0)

Ghi **trước khi vẽ**, mỗi người một dòng.

| Mã | Frame xuất hiện | Frame cuối thấy được | Rẽ / dừng / đổi tốc độ ở frame | Bị che ở frame | Ghi chú |
|---|---|---|---|---|---|
| P1 | 1|150 |Turns around frame 107-150 |39-50 |Wearing dark clothes, walking near the store entrance. |
| P2 |1 |150 |None |None | Partially visible near the right edge of the frame.|
| P3 |1 |150 | None| None|Moves behind another pedestrian. |
| P4 |1 |147 |Stops around frame 41-110 |111-136 |None |
| P5 |1 | 105|Stops around frame 41-106 |107-150 |Temporarily disappears from view. |

## 2. Keyframe và thời gian (CP1, CP4)

Số keyframe lấy từ kết quả `src/check_submission.py`.

| Mã | Số keyframe | Keyframe ở frame | Số frame có mặt | Keyframe / 100 frame | Thời gian (phút) | Chỗ khó |
|---|---|---|---|---|---|---|
| P1 |70 |[0, 3, 4, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 25, 27, 29, 33, 34, 35, 37, 50, 57, 60, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 83, 84, 85, 86, 87, 88, 89, 90, 92, 95, 96, 97, 99, 100, 104, 110, 112, 114, 115, 116, 117, 120, 126, 130, 139, 140, 142, 144, 145, 147, 149] |139 |50.4 | 10p| Bị che khuất (19 frame), ra ngoài khung hình (1 lần bật outside). Phải đặt keyframe dày đặc.|
| P2 |65 | [0, 2, 4, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 20, 21, 22, 23, 24, 25, 35, 38, 39, 46, 50, 55, 56, 57, 58, 59, 60, 67, 70, 74, 80, 87, 88, 90, 93, 100, 110, 112, 114, 115, 116, 117, 118, 119, 120, 121, 122, 123, 124, 125, 126, 127, 128, 129, 130, 132, 133, 134, 140, 142, 144, 149]|150 |43.3 |10p |Đối tượng xuất hiện xuyên suốt nhưng thay đổi tư thế, hướng đi hoặc tốc độ nhiều. |
| P3 |78 |[0, 1, 2, 3, 4, 6, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 25, 27, 28, 29, 35, 38, 39, 40, 41, 46, 47, 50, 51, 56, 60, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 84, 86, 88, 90, 94, 100, 110, 112, 114, 120, 122, 123, 124, 125, 126, 127, 128, 129, 130, 132, 134, 135, 140, 142, 145, 149] |150 |52.0 |10p |Chuyển động phức tạp, bị che khuất (3 frame), mật độ keyframe cao nhất cảnh. |
| P4 |28 |[0, 3, 4, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 25, 35, 39, 50, 60, 80, 90, 105, 106, 136, 137, 140, 141, 142] |121 |20.0 |10p |Bị che khuất khá nhiều (14 frame) và ra ngoài khung hình (2 lần bật outside). |
| P5 |21 |[0, 3, 4, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 25, 35, 39, 50, 70, 87, 90] |105 |20.0 |8p |Bị che khuất nhiều (15 frame) nhưng di chuyển tương đối đều nên không tốn nhiều keyframe. |
| **Tổng** |262 |- |665 |- |48p | -|

Keyframe / 100 frame của cả bài = tổng keyframe ÷ tổng số frame có mặt × 100 = 39.4

Bạn đặt keyframe nhiều nhất ở người nào? Vì sao (người đó rẽ, dừng, lại gần camera hay bị che)?

Tôi đặt keyframe nhiều nhất ở Track 2 (78 keyframe, chiếm 52.0 KF/100 frame).
Người này có mật độ keyframe vượt mức cảnh báo 50. Nguyên nhân là do đối tượng có quỹ đạo di chuyển thay đổi liên tục, có thể rẽ hướng, dừng lại, hoặc tương tác với các vật thể khác gây ra tình trạng bị che khuất (occluded) và biến đổi kích thước bounding box, buộc tôi phải điều chỉnh thủ công và chốt keyframe liên tục để box bám sát mà không bị trôi.

## 3. Đoạn bị che (CP2)

Người bị che: `P1`

| Mốc | Frame |
|---|---:|
| Bắt đầu bị che một phần (bật `occluded`) |39 |
| Mất hẳn (bật `outside`) |46 |
| Hiện lại (tắt `outside`) |50 |
| Thấy rõ trở lại (tắt `occluded`) |62 |

- Thời gian khuất hẳn: 4 frame = 4 giây.
- Quyết định: giữ cùng ID.
- Lý do (trả lời 3 câu: khuất bao lâu so với 60 frame, ngoại hình có khớp, chỗ hiện lại có đúng hướng và tốc độ):
Thời gian khuất: Thời gian người này bị khuất hẳn (bật outside) chỉ kéo dài 4 frame (từ frame 46 đến frame 50), khoảng thời gian này rất ngắn và an toàn, nằm hoàn toàn dưới ngưỡng giới hạn cho phép là 60 frame.
Ngoại hình: Đặc điểm nhận dạng, vóc dáng và trang phục của đối tượng khi xuất hiện lại ở frame 50 hoàn toàn trùng khớp với người P1 trước khi bị che mất ở frame 46.
Hướng và tốc độ: Vị trí người này hiện lại nối tiếp hợp lý với quỹ đạo chuyển động. Quãng đường dịch chuyển trong 4 frame hoàn toàn tương xứng với hướng đi và tốc độ mà người này đang di chuyển trước đó.

Ảnh chụp màn hình:

![Trước khi che](images/che_1_truoc.png)
![Giữa đoạn che, thấy cờ trên panel object](images/che_2_giua.png)
![Sau khi hiện lại, cùng ID](images/che_3_sau.png)

## 4. Tự review ID (CP3)

Lượt 1 theo người (đi ngược từ frame 149 về 0 trên CVAT), lượt 2 theo cảnh (nhảy 10 frame). Ít nhất 3 dòng; không có lỗi thì ghi một dòng "đã kiểm hai lượt, không lỗi".

Loại lỗi dùng đúng một trong 7 mã: `id_switch`, `fragmentation`, `lost`, `merge`, `false_track`, `drift`, `flag`.

| Frame | Mã người | Loại lỗi | Mô tả một câu | Phát hiện ở lượt | Đã sửa? |
|---:|---|---|---|---|---|
| -|- |- |Đã kiểm tra hai lượt theo người và theo cảnh, không phát hiện lỗi. | Cả hai lượt|Không cần sửa |

Tổng hợp số lỗi theo loại:

| `id_switch` | `fragmentation` | `lost` | `merge` | `false_track` | `drift` | `flag` |
|---:|---:|---:|---:|---:|---:|---:|
| 0|0 |0 |0 | 0|0 |0 |

Lỗi nào chỉ lượt 2 (theo cảnh) mới thấy, lượt 1 (theo người) không thấy? Vì sao?

Không có lỗi nào chỉ được phát hiện ở lượt 2. Tuy nhiên, việc kiểm tra theo cảnh ở lượt 2 giúp quan sát tổng thể sự di chuyển của các đối tượng, từ đó dễ nhận ra những bất thường trong quan hệ giữa các người, sự thay đổi vị trí và tính liên tục của các bounding box mà lượt kiểm tra riêng từng người có thể bỏ sót.

## 5. File xuất và kết quả tự kiểm (CP4)

| Kiểm tra | Kết quả |
|---|---|
| Tên file MOT 1.1 |DoanThiPhuongThao_mot.zip |
| Tên file CVAT for video 1.1 |DoanThiPhuongThao_cvat_video.zip |
| Số track ID khác nhau trong `gt/gt.txt` (phải là 5) | 5|
| Frame `outside` không có dòng trong `gt.txt` (đúng / sai) |đúng |
| Job đã completed trên CVAT máy cá nhân | xác nhận|

Dán phần tóm tắt in ra từ `src/check_submission.py`:

```Số frame in theo CVAT (bắt đầu từ 0). Trong gt.txt, frame_id = frame CVAT + 1.

=== File MOT 1.1: DoanThiPhuongThao_mot.zip ===
  Số track ID: 5   |   Tổng số box: 665
  [OK]        Đúng 5 track ID.

  Track | Frame có mặt | Số frame | Đoạn vắng (outside)
      1 |   0–149      |      139 | 39–49
      2 |   0–149      |      150 | -
      3 |   0–149      |      150 | -
      4 |   0–146      |      121 | 110–135
      5 |   0–104      |      105 | -


=== File CVAT for video 1.1: DoanThiPhuongThao_cvat_video.zip ===

  Track | Nhãn   | Frame thấy | Keyframe | KF/100 frame | Frame occluded | Lần bật outside
      0 | person |        139 |       70 |         50.4 |             19 |               1
              Track 0: keyframe ở frame [0, 3, 4, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 25, 27, 29, 33, 34, 35, 37, 50, 57, 60, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 83, 84, 85, 86, 87, 88, 89, 90, 92, 95, 96, 97, 99, 100, 104, 110, 112, 114, 115, 116, 117, 120, 126, 130, 139, 140, 142, 144, 145, 147, 149]
  [CẢNH BÁO]  Track 0: 50 keyframe / 100 frame > 50. Quá dày, dồn keyframe vào chỗ rẽ / dừng / bị che.
      1 | person |        150 |       65 |         43.3 |              0 |               0
              Track 1: keyframe ở frame [0, 2, 4, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 20, 21, 22, 23, 24, 25, 35, 38, 39, 46, 50, 55, 56, 57, 58, 59, 60, 67, 70, 74, 80, 87, 88, 90, 93, 100, 110, 112, 114, 115, 116, 117, 118, 119, 120, 121, 122, 123, 124, 125, 126, 127, 128, 129, 130, 132, 133, 134, 140, 142, 144, 149]
      2 | person |        150 |       78 |         52.0 |              3 |               0
              Track 2: keyframe ở frame [0, 1, 2, 3, 4, 6, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 25, 27, 28, 29, 35, 38, 39, 40, 41, 46, 47, 50, 51, 56, 60, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 84, 86, 88, 90, 94, 100, 110, 112, 114, 120, 122, 123, 124, 125, 126, 127, 128, 129, 130, 132, 134, 135, 140, 142, 145, 149]
  [CẢNH BÁO]  Track 2: 52 keyframe / 100 frame > 50. Quá dày, dồn keyframe vào chỗ rẽ / dừng / bị che.
      3 | person |        121 |       28 |         23.1 |             14 |               2
              Track 3: keyframe ở frame [0, 3, 4, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 25, 35, 39, 50, 60, 80, 90, 105, 106, 136, 137, 140, 141, 142]
      4 | person |        105 |       21 |         20.0 |             15 |               1
              Track 4: keyframe ở frame [0, 3, 4, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 25, 35, 39, 50, 70, 87, 90]

  Tổng: 262 keyframe / 665 frame có mặt = 39.4 keyframe / 100 frame
  [OK]        Đọc được 5 track từ annotations.xml.

=== Tóm tắt ===
  Lỗi: 0   |   Cảnh báo: 2
  Không có lỗi định dạng. Mở CVAT xem lại từng [CẢNH BÁO]; cảnh báo đúng ý bạn thì ghi lý do vào báo cáo.
```

## 6. Ba câu kết

1. Nếu được gán lại, bạn sẽ đặt keyframe khác ở đâu? Vì sao?

   Nếu được thực hiện lại, em sẽ bổ sung keyframe tại những thời điểm đối tượng thay đổi hướng di chuyển, thay đổi tốc độ, bị che khuất một phần hoặc di chuyển gần các đối tượng khác. Đặc biệt, em sẽ chú ý các frame trước và sau khi đối tượng bị che khuất để đảm bảo bounding box bám sát vị trí thực tế. Điều này giúp quá trình nội suy giữa các keyframe chính xác hơn, hạn chế bounding box bị lệch hoặc không theo kịp chuyển động của đối tượng.

2. Có chỗ nào bạn không chắc "cùng ID hay ID mới"? Bạn đã quyết định và ghi chú thế nào?

  Trong quá trình tracking, em có thể gặp khó khăn khi một người bị che khuất bởi người khác hoặc tạm thời biến mất khỏi khung hình. Khi đối tượng xuất hiện trở lại, em sẽ dựa vào vị trí xuất hiện, hướng di chuyển, đặc điểm hình dáng và sự liên tục trong các frame trước đó để xác định có phải cùng một người hay không.

Nếu có đủ căn cứ nhận diện, em tiếp tục sử dụng ID cũ. Nếu không đủ chắc chắn về danh tính, em sẽ không tự ý gán ID cũ mà ghi chú lại trường hợp cần kiểm tra thêm để tránh xảy ra lỗi ID switch.

3. Một lỗi ID trong job của bạn (nếu không còn sót, chọn lỗi đã sửa) có thể làm xe tự lái dự đoán sai chuyển động của người đó như thế nào? Lỗi đó ảnh hưởng MOTA hay IDF1 nhiều hơn?

  Ví dụ, nếu xảy ra lỗi ID switch, hệ thống có thể nhận nhầm một người đang đi bộ thành một người khác khi hai người di chuyển gần nhau hoặc bị che khuất. Khi đó, hệ thống sẽ không theo dõi được chính xác lịch sử chuyển động của từng người, dẫn đến dự đoán sai hướng đi hoặc tốc độ di chuyển. Đối với xe tự lái, điều này có thể khiến hệ thống đánh giá sai nguy cơ va chạm và đưa ra quyết định phanh hoặc chuyển hướng không phù hợp.

Lỗi ID switch thường ảnh hưởng đến IDF1 nhiều hơn vì IDF1 đánh giá mức độ duy trì danh tính đối tượng chính xác xuyên suốt quá trình tracking. Tuy nhiên, lỗi này cũng có thể ảnh hưởng đến MOTA nếu gây ra các lỗi ghép nối đối tượng hoặc các sai lệch trong kết quả phát hiện.

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

cvat, claude, gemini 
