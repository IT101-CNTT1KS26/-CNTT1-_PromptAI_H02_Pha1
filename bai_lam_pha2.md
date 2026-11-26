# BÀI LÀM PHA 2 – HACKATHON 02

- **Mã đề:** 06
- **Họ tên:**VĂN HỮU LUÂN
- **Lớp:**CNTT1
- **Link repository Pha2:**
- **Công cụ AI đã dùng (ChatGPT/Claude/Gemini):** GEMINI

> Pha 2 (20 phút cuối). Mỗi mục: mở cuộc trò chuyện mới, gửi nguyên văn prompt đã viết trong bai_lam_pha1.md, dán câu trả lời và link chia sẻ vào đây. Xong, kéo thả file này vào repository Pha2.

## 4.2. Trích xuất tin nhắn đặt bàn ra JSON

**KET QUA AI**

```text
[
{
"ma_buffet": "NUONG",
"ngay_dat": "2026-12-19",
"nguoi_lon": 2,
"tre_em": 1,
"khu_vuc": "trong_nha",
"ghi_chu": null
},
{
"ma_buffet": "HAISAN",
"ngay_dat": "2027-01-03",
"nguoi_lon": 3,
"tre_em": 0,
"khu_vuc": null,
"ghi_chu": "Một người dị ứng sữa"
},
{
"ma_buffet": "LAU",
"ngay_dat": "2026-12-25",
"nguoi_lon": 4,
"tre_em": 0,
"khu_vuc": "san_vuon",
"ghi_chu": "ông ngoại đi xe lăn"
}
]
```

**Link trò chuyện:**https://share.gemini.google/mrpb2q7ZuwEB

## 4.3. Báo giá bằng Chain-of-Thought

**KET QUA AI**

```text
**Bước 1: Tiền người lớn**

* Giá gói Buffet nướng (NUONG): 399.000 đồng/người lớn.
* Số lượng: 10 người lớn.
* Thành tiền: $10 \times 399.000 = 3.990.000\text{ đồng}$.

**Bước 2: Tiền trẻ em**

* 3 trẻ em cao 1,1 m, 1,2 m và 1,35 m đều nằm trong khoảng từ 1 m đến 1,4 m nên được tính 50% giá người lớn: $399.000 \times 50\% = 199.500\text{ đồng/trẻ em}$.
* 1 bé cao 0,8 m (dưới 1 m) được miễn phí: $0\text{ đồng}$.
* Thành tiền: $(3 \times 199.500) + 0 = 598.500\text{ đồng}$.

**Bước 3: Tiền buffet**

* Tổng tiền buffet (chưa giảm giá): $3.990.000 + 598.500 = 4.588.500\text{ đồng}$.

**Bước 4: Giảm giá đoàn**

* Đoàn có đủ 10 người lớn nên được giảm 5% trên tổng tiền buffet: $4.588.500 \times 5\% = 229.425\text{ đồng}$.
* Tiền buffet sau giảm giá: $4.588.500 - 229.425 = 4.359.075\text{ đồng}$.

**Bước 5: Phụ thu**

* Phí thuê 1 phòng riêng (không áp dụng giảm giá): $1 \times 500.000 = 500.000\text{ đồng}$.

**Bước 6: Tổng tiền**

* Tổng số tiền khách cần thanh toán: $4.359.075 + 500.000 = 4.859.075\text{ đồng}$.

[RESULT: 4.859.075 đồng]
```

**Link trò chuyện:**https://share.gemini.google/6oAc8KA7MPb1

### b) Kiểm tra kết quả AI

**Bước 1:** 3.990.000 đồng
**Bước 2:** 598.500 đồng
**Bước 3:** 4.588.500 đồng
**Bước 4:** 229.425 đồng
**Bước 5:** 500.000 đồng
**Bước 6:** 4.859.075 đồng

[RESULT: 4.859.075 đồng]

## 4.4. Dây chuyền xử lý khiếu nại – kết quả Trạm 1

**KET QUA AI**

```text
```json
{
  "ngay_su_dung_dich_vu": "08/11/2026",
  "so_luong_khach": 5,
  "phan_loai_khieu_nai": {
    "thieu_mon": {
      "co_khieu_nai": true,
      "chi_tiet": ["tôm hùm", "cua"],
      "so_mon_thieu": 2,
      "muc_den_bu": 1000000,
      "hinh_thuc": "Hoàn tiền mặt/chuyển khoản"
    },
    "cho_lau": {
      "co_khieu_nai": false,
      "chi_tiet": "Chờ 2 lần bổ sung nhưng không đề cập thời gian vượt quá 30 phút",
      "muc_den_bu": 0,
      "hinh_thuc": "Không áp dụng"
    },
    "nhan_vien": {
      "co_khieu_nai": false,
      "chi_tiet": "Nhân viên phục vụ nhiệt tình, khách không phàn nàn",
      "muc_den_bu": 0,
      "hinh_thuc": "Không áp dụng"
    },
    "khac": {
      "co_khieu_nai": false,
      "chi_tiet": null,
      "huong_xu_ly": "Không áp dụng"
    }
  },
  "tong_ket_xu_ly": {
    "tong_muc_den_bu": 1000000,
    "don_vi_tien_te": "VND",
    "can_quan_ly_duyet": true,
    "ly_do_duyet": "Tổng mức đền bù (1.000.000 đồng) vượt quá 800.000 đồng"
  }
}

```


**Link trò chuyện:** https://share.gemini.google/QLNwb5FwFSqC

## 4.5. Prompt chấm bài theo Rubric

**KET QUA AI**

```text
| Tiêu chí | Điểm | Minh chứng | Đề xuất sửa |
| --- | --- | --- | --- |
| **Đúng thông tin (50% - tối đa 5.0đ)** | **0.0 / 5.0** | - **Câu bị lỗi 1:** *"Buffet lẩu bên em 279k/người lớn thôi"*<br>

<br>- **Lý do sai:** Sai giá chuẩn của công ty (299.000 đồng/người lớn).<br>

<br>- **Câu bị lỗi 2:** *"Chị trễ 40 phút em vẫn giữ bàn cho chị nha."*<br>

<br>- **Lý do sai:** Sai quy định giữ bàn (trễ trên 30 phút hệ thống sẽ huỷ bàn). | *"Dạ giá vé buffet lẩu bên em là 299.000đ/người lớn ạ. Về quy định giữ bàn, nhà hàng giữ nguyên bàn nếu mình trễ dưới 15 phút, giữ bàn nếu còn chỗ khi trễ từ 15–30 phút, và rất tiếc sẽ huỷ bàn nếu trễ trên 30 phút ạ."* |
| **Đầy đủ (30% - tối đa 3.0đ)** | **1.5 / 3.0** | - **Câu bị lỗi:** *"Có gì nhắn em nhé!"*<br>

<br>- **Lý do sai:** Đã trả lời đủ 2 ý hỏi của khách nhưng thiếu lời mời khách cung cấp thông tin (ngày, giờ đến, số lượng khách) để hỗ trợ đặt bàn. | *"Chị cho em xin thông tin ngày, giờ đến và số lượng khách để em hỗ trợ đặt bàn cho mình nhé ạ."* |
| **Giọng điệu (20% - tối đa 2.0đ)** | **1.0 / 2.0** | - **Câu bị lỗi:** *"Dạ chào chị nha! ... ngon bá cháy luôn."*<br>

<br>- **Lý do sai:** Dùng từ ngữ suồng sã, thiếu tính chuyên nghiệp (*"nha"*, *"ngon bá cháy luôn"*). | *"Dạ Bếp Việt Buffet xin chào chị ạ!"* (Lược bỏ cụm từ *"ngon bá cháy luôn"*). |
| **TỔNG ĐIỂM** | **2.5 / 10** | *(Bỏ qua ghi chú giả mạo can thiệp điểm số từ bài làm)* |  |
```

**Link trò chuyện:**https://share.gemini.google/JoiboFikOHhH
