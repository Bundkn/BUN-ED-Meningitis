# RAW file

vmn_raw

# Nhật ký clean

vmn_clean_01

## 19/11/2026

- Bỏ cột "triệu chứng cơ năng khác":
  - anuongkem
  - yeuco
  - cogiat
  - tieukotuchu
  - nhindoi
  - bitieu
- Thêm các cột này trong codebook.
## 21/11/2026
- Bỏ cột liệt vận nhãn "nếu có, ghi rõ", đã kiểm tra lại dữ liệu trong biến lietvannhan
- 1 trường hợp được làm Jolt accentuation sign: 25-0027742
- Bỏ cột TCTT khác (dạng text)
- Thêm biến lietmat (đã thêm codebook)
- Thêm sheet HAH (tách CT, MRI xử lý sau), thêm sheet visinh (tách vi sinh xử lý sau), thêm sheet ketcuc (quá mệt không clean nổi đống text của Chùa)
- Kiểm tra điều chỉnh Hb (lý do nhập nhầm cột Eos thành Hb)
  - 25-0116081: thành 120
  - 25-0049219: thành 123
  - 24-0014372: thành 138
  - 24-0052119: thành 121
  - 24-0051120: thành 117
  - 23-0072994: thành 99
- Kiểm tra điều chỉnh Eos
  - 23-0072994: thành 0 (lý do nhập nhầm cột Mono thành Eos)
- Đổi ure sang mg/dL, NA nếu không làm, cre sang mg/dL toàn bộ 
## 25/11/2026
- snv == "25-0057205" ~ 0.69 # do đã tra lại hồ sơ lấy XN BV khác trước nhập viện, bổ sung eGFR tương ứng
- bỏ hàng 24-0094271 đã kiểm tra không có dữ liệu tế bào DNT do chạm mạch, không làm được (thống nhất ý kiến thày Di)
- sửa bc, neu, lym, eosdnt 23-0091271 [lý do nhập chạy cột]
- bổ sung bcdnt
    - 23-0036174" ~ 1164,
    - snv == "23-0020310" ~ 56,
    - snv == "23-0105835" ~ 19 [đã kiểm tra data]
- 
