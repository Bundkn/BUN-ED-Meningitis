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
- sửa neu, eos, gludnt "25-0026920"
- sửa bc, neu, lym, eos, gludnt 25-0030375
- sửa eosdnt 25-0116196
- sửa lacdnt, bidnt, cldnt == 0 ~ NA
- điều chỉnh snv 25-0080395, 25-0046961, 25-0057648, 24-0054626 kqvmn == 1 -> 0
- cc = ifelse(snv == "25-0020633", 162, cc),
- cn = ifelse(snv == "25-0092748", 66, cn),
- cn = ifelse(snv == "24-0083275", 48, cn),
- cn = ifelse(snv == "25-0115710", 54, cn),
- cn = ifelse(snv == "24-0076286", 52, cn),
- cn = ifelse(snv == "24-0124024", 50, cn)
- sửa sinh hiệu nhiều tst = ifelse(snv == "23-0019082", 90, tst),
      hatr = ifelse(snv == "25-0053570", 60, hatr),
      hatr = ifelse(snv == "25-0120576", 70, hatr),
      tem = ifelse(snv == "25-0003778", 36, tem),
      tem = ifelse(snv == "25-0101187", 36, tem),
      tem = ifelse(snv == "23-0110420", 37.8, tem),
      tem = ifelse(snv == "23-0056028", 37, tem),
      rr = ifelse(snv == "23-0098559", 18, rr),
      rr = ifelse(snv == "24-0120202", 18, rr),
      rr = ifelse(snv == "24-0115979", 18, rr),
      rr = ifelse(snv == "23-0031306", 18, rr),
      rr = ifelse(snv == "25-0037690", 20, rr),
      spo2 = ifelse(snv == "24-0062514", 95, spo2),
      spo2 = ifelse(snv == "25-0117709", 90, spo2),
      spo2 = ifelse(snv == "23-0023865", 95, spo2),
      spo2 = ifelse(snv == "23-0075599", 92, spo2),
      spo2 = ifelse(snv == "23-0045446", 98, spo2)
    )
 
  m <- m %>%
  mutate(
    tem = if_else(
      snv %in% c("25-0027742", "25-0010418", "25-0024956",
                 "25-0016421", "25-0090538", "25-0092582",
                 "23-0057045"),
      tem / 10,
      tem
    ))
