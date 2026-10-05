# Korea and the AI Bubble — trạng thái dự án

Cập nhật: 27/09/2026

## Quy ước cố định

| Mục | Chốt |
| --- | --- |
| Comp | 3840 × 2160 · 30fps |
| Font | **Plus Jakarta Sans** — duy nhất, mọi chỗ |
| **Thang cỡ chữ** | **Chỉ được dùng 5 bậc: `44` · `56` · `68` · `80` · `96`.** Số chính dùng `LIB_Counter` (nền 300, scale theo beat). **Không tự đặt cỡ ngoài thang.** Chốt 29/09/2026 — xem bảng bên dưới. |
| Ngôn ngữ trên hình | **Toàn bộ chữ lên hình là tiếng Anh**, kể cả dòng nguồn. Ngày ghi kiểu `28 JUL 2026`. Tiếng Việt chỉ dùng trong tên layer và tài liệu. |
| Bảng màu | **Vẫn đúng 6 màu** (không đổi): `#14191D` nền · `#1F242B` khối phụ · `#BBBBBB` chữ phụ · `#FFFFFF` chữ chính · `#E61A1A` đỏ · `#0066FF` xanh. *Lưu ý: cyan/đỏ-sáng thấy trong video đầu chỉ là **Glow nở màu** trên frame nén, KHÔNG phải màu mới.* |
| Glow | **Chỉ dùng để NHẤN thứ muốn nhấn — KHÔNG phải luật "số nào cũng glow".** Glow cùng hue với layer, tiết chế. Plugin: **Deep Glow 2** hoặc **Stylize > Glow** (khi viết `.jsx` gọi đúng effect này). Trước tôi cấm glow — bỏ lệnh cấm; nhưng cũng đừng lạm dụng. |
| In nghiêng | **Bỏ hoàn toàn.** Số và chữ đều đứng. |
| 🔴 Style thân bài — template = B8 (chốt 30/09) | **`assets/B8_depth.png` là CHUẨN style cho toàn bộ B2→OUTRO** (anh đã duyệt). Gồm: **nền radial vignette** (sáng nhẹ tâm, tối rìa — không phẳng trơn) · **gradient dọc nhẹ trên khối/bar** · **đổ bóng elevation** cho card/khối · **glow chỉ ở 1 câu/số nhấn mỗi beat** · lưới rất mờ (≤7%). Chữ PJS đứng, 6 màu. Đã xem bản dựng Master_KB02 (3 hook): Hook 1 nền ảnh+grade+tint+bloom; Hook 2/3 nền phẳng + chart đỏ full-bleed + số lớn đè lên. Body beat theo B8, beat cần không khí (B10 Seoul, B20 người) dùng nền ảnh như Hook 1. |
| Thiết bị trình bày | bar/area **gradient dọc nhẹ**, caption kết **đóng khung**, **VS/≠/chevron**, icon — dùng được, là phụ. |
| Voice | `VO/Beats/*.wav`, mỗi file đặt ở **f0** của pre-comp tương ứng |
| Chart | mọi chart phải có **nguồn hiện trên hình** |
| Chuyển cảnh | viết trong hướng dẫn của chính beat đó, không tách bảng riêng |
| Mister Horse | chỉ dùng cho chuyển cảnh / easing / SFX. **Không dùng cho phần tử dữ liệu** |
| Nguyên tắc hình | đọc thì phẳng, kể thì có chiều sâu — shot có camera/parallax không bao giờ là nơi duy nhất chứa thông tin cần đọc |
| Bố cục chống đơn điệu | **không căn giữa mọi beat.** Gán mỗi beat một kiểu theo nội dung: số hero lệch trái · thanh tỉ lệ ngang · chuỗi ngang · sổ hai cột · lưới. Xen beat "ồn" với beat "tĩnh". Demo: `assets/Variety_demo.png` |
| Từ vựng biểu đồ | beat nặng số phải chọn **dạng hình hợp với việc của số**, không phải lúc nào cũng số to. 9 dạng + cấm pie/gauge/dual-axis: `build/Chart_Vocabulary.md` · catalog `assets/Chart_catalog.png`. Bar xếp hạng dùng 1 màu + nhãn, không tô theo thứ hạng |
| Ngôn ngữ hook vs thân bài | **3 hook nóng hơn** — chữ to, tương phản mạnh, glow đậm. **Thân bài từ B1: chart animate có trục + số hero (nghiêng, glow nhẹ) + caption khung** (style kênh, sửa 30/09 — không còn "phẳng tuyệt đối"). `LIB_Card` là đồ thân bài, không dùng trong hook. |
| Chú giải màu | hiện **một lần ở B1**: hai viên nang `REAL` (xanh) · `BORROWED` (đỏ), giữ 60 frame. Không đặt ở hook. |
| Dòng phán quyết | một câu khẳng định ngắn hai màu, ExtraBold 88, y1780, mờ vào 12 frame cuối beat. **Chỉ ở 3 hook + 7 beat ★.** Dùng khắp nơi là hết thiêng. |
| Ảnh người thật | **chỉ B20**, một lần duy nhất trong 15 phút. Đơn sắc, Tint `#14191D`, Opacity 70–80. |
| Cách làm việc | render ảnh tham chiếu → duyệt → mới viết bước AE. Đến beat nào làm beat đó. |
| Tên layer trong comp beat | **tag loại 2 chữ in hoa + mô tả tiếng Việt**, chốt 28/09/2026. `BG` nền · `GR` grade · `LP` lớp chiều sâu · `CH` chữ · `SO` số · `NANG` viên nang · `NG` nguồn · `CC` chuyển cảnh. Ví dụ: `BG ảnh phòng máy` · `GR tối 4 góc` · `SO −10%+` · `NANG Samsung`. |
| Tên layer trong comp `LIB_*` | **không được đổi** — biểu thức gọi theo tên: `CTRL` · `PILL_TXT` · `PILL_BG` · `S_PRE` · `S_SUF` · `TXT_NUM` · `CARD_BG` · `CARD_ACCENT` · `MATTE` · `CARD_LABEL` · `EYE_TXT` · `SRC_TXT` |

## Thang cỡ chữ — chốt 29/09/2026

Trước ngày này dự án dùng **11 cỡ rải rác** (30 · 38 · 42 · 44 · 48 · 50 · 56 · 58 · 76 · 80 · 82 · 88). Đó là nguyên nhân chữ chỗ to chỗ nhỏ không có lý do.

Mốc tính: khung 3840 px xem **toàn màn ngang trên điện thoại** = tỉ lệ **×0,22**. Ngưỡng đọc thoải mái là **≥14pt**.

| Bậc | Vai trò | Trên điện thoại ngang | Dùng ở |
| --- | --- | --- | --- |
| **96** | tuyên bố — dòng phán quyết, chữ lớn mở beat | 21,1pt | `CH ngày JULY 28` · dòng phán quyết |
| **80** | chữ chính trên hình | 17,6pt | `LIB_Pill` · `LIB_Card` nhãn · chữ chạy |
| **68** | **chữ mang lập luận** — mặc định cho mọi dữ kiện | 14,9pt | tên công ty · dòng dữ kiện phụ |
| **56** | nhãn mô tả con số | 12,3pt | nhãn dưới `LIB_Counter` · `LIB_Eyebrow` |
| **44** | chú thích, trích dẫn | 9,7pt | `LIB_Source` · nhãn giá trên trục |
| *300* | *nền của `LIB_Counter`* | *scale theo từng beat* | mọi con số chính |

**Hai bậc dưới cùng cố ý nhỏ.** 44 là trích dẫn, 56 là nhãn phụ thuộc con số bên cạnh — chúng không phải lập luận nên không cần đọc được trên điện thoại.

**Không thể làm chữ phụ đọc được trong feed dọc.** Video 16:9 lọt khung dọc 390pt thì tỉ lệ chỉ còn ×0,10, chữ 96px cũng chỉ ra 9,8pt. Mọi video 16:9 đều vậy — trong feed người xem chỉ đọc được con số lớn. **Đừng thiết kế theo feed dọc.**

### Quy tắc đi kèm

- **Câu ngắn quan trọng hơn chữ to.** Phóng to mà giữ câu dài là tràn khung. Cắt câu trước, phóng sau.
- **Cùng một cỡ, phân vai bằng đậm nhạt và màu**, không bằng cỡ. Ví dụ ở bậc 68: Medium `#8C8C8C` là nhãn, Bold `#0066FF` là dữ kiện.
- **Dòng nguồn luôn tiếng Anh**, mở đầu bằng `SOURCE:`.

## Tiến độ dựng

| Việc | Trạng thái |
| --- | --- |
| **Thư viện tầng 1** (5 comp) | **xong** 28/09/2026 · đặc tả: `assets/LIB_ref.png` · hướng dẫn: `build/LIB01_Build.md` · script: `build/DTT_LIB_Build.jsx` v3 |
| HOOK 1 | hướng dẫn **v4**: `build/HOOK01_Build.md` · **đặc tả đã đầy đủ, không còn việc viết** · đã sửa 4 lỗi: rung khung thiếu Scale 103 · vòng sáng chuyển vào `LIB_Pill` · viên nang 3 thành **`RECORD RESULTS · JULY 29–30`** · mục 9 thay bằng **Solid `#14191D` mờ vào f352→f367** (bỏ Directional Blur và Dip to Color) · **còn lại là thao tác trong AE** |
| HOOK 2 | **hướng dẫn v2: `build/HOOK02_Build.md`** · đổi hướng hoàn toàn, bỏ card, dùng đường giá thật làm nền · asset sẵn: `assets/hook2_line.pdf` + script dự phòng `build/Hook2_Line.jsx` · **sẵn sàng dựng** |
| HOOK 3 | **hướng dẫn: `build/HOOK03_Build.md`** · bố cục duyệt 29/09, preview `assets/Hook3_ref.png` · dựng bằng cách **nhân bản comp Hook02 rồi xoá hết keyframe tại f364** · 216 frame · **phải dựng xong Hook 2 trước** |
| B1 → OUTRO | chưa bắt đầu · `storyboard/Storyboard_Updates.md` **3 phần, 20 frame phải sửa** — phần 1 số sai, phần 2 thiết bị trình bày mới, **phần 3 cập nhật sau khi mở 19 link nguồn (29/09)**. ⚠ Phần 3 đè lên phần 1 ở B6, B15, B20 |
| Bộ icon | cách làm đã chốt: **tải sẵn từ một bộ duy nhất, không tự vẽ, tô màu bằng Fill effect trong AE** · kiểm kê 22 icon + 4 điều kiện tải: `build/LIB_Icon_Plan.md` · **chưa tải** |

### Việc kế tiếp, theo thứ tự

1. Thao tác trong AE: **HOOK 1** hai chỗ sửa ở `HOOK01_Build.md` mục 7 và mục 9 → rồi **HOOK 2** theo `HOOK02_Build.md` v2.
2. ~~Viết `build/HOOK03_Build.md`.~~ **Xong 29/09.** Còn lại là thao tác trong AE, sau khi Hook 2 xong.
3. Tải 22 icon từ **một bộ duy nhất** về `assets/icons/` — xem `build/LIB_Icon_Plan.md`.
4. **Link nguồn — đã mở 19/28 (29/09/2026).** Kết quả đầy đủ ở `data/Link_Verification.md`: 5 thay đổi bắt buộc với kịch bản, 2 item treo được gỡ, và rất nhiều số mới dùng được ngay. Còn lại: **bài Reuters 20/07 về margin** (quan trọng nhất, đang bị rate-limit) · Reuters CSOP 28/07 · CNA Đài Loan (403) · PDF S&P DJI (403) · sedaily · FSC 86910 · FSC dicId=1831 · investing.com Fed · x.com/KobeissiLetter.
5. Upscayl ×4 `assets/W1_raw.webp` → `assets/W1_bg.png`.

Thứ tự đã chốt 28/09/2026: **dựng thư viện trước, rồi mới tới beat.** Lý do và số lần dùng: `build/LIB_Plan.md`.

Bảng frame đầy đủ 39 beat: `Beat_Frames_REAL.csv` (tổng 27.626 frame = đúng độ dài file voice).

## Thư viện `DTT_LIB.aep` — **dựng trước, không tách sau**

Đếm lại từ 39 frame storyboard (28/09/2026): kế hoạch cũ "dựng xong Hook 1 rồi tách" là sai thứ tự — riêng viên nang đã dùng ~45 lần, khối số ~30 lần. Chi tiết và số lần dùng từng comp: **`build/LIB_Plan.md`**.

Tầng 1 (dựng trước tiên): `LIB_Eyebrow` ~27 beat · `LIB_Pill` ~45 lần · `LIB_Card` ~30 lần · `LIB_Counter` ~25 lần · `LIB_Source` mọi beat có số.
Tầng 2: `LIB_KOSPI_Line` (HOOK 1, B15, B17, B18) · `LIB_Timeline` (B2, B3, OUTRO) · `LIB_Check` (5) · `LIB_Donut` (3) · `LIB_Stamp` (3) · `LIB_BlockGrid` (5).
Tầng 3: `LIB_Rig_Parallax` · `LIB_Grade_Cinematic` (.ffx) · `LIB_Trans_Dip` (38 lần chuyển cảnh).

## Việc còn treo

### Nội dung cần xác minh
1. **B35 — ngưỡng FCF "$7 tỷ".** Chưa có nguồn, nhiều khả năng sai đơn vị. **Voice đã thu rồi** → cần thu lại một câu chèn.
2. ~~**HOOK 2 — SK Hynix +257% hay +557%?**~~ **ĐÃ GIẢI QUYẾT 28/09/2026.** Mở thông cáo chính thức của SK hynix: doanh thu **+257%**, lợi nhuận hoạt động **+557%** — cả hai đều đúng, không mâu thuẫn. Lời đọc chuẩn. Số Samsung $119B/$62B cũng đã xác minh qua AP. **HOOK 2 hết bị chặn.** Xem `data/Link_Verification.md`.
3. ~~**B24 — tin đồn Apple / HBM** cần nhãn **RUMOR**.~~ **ĐÃ GIẢI QUYẾT 29/09/2026 — bỏ nhãn RUMOR.** FT, Reuters, Bloomberg, Fortune cùng đưa tin 26–27/06/2026: Apple vận động chính quyền Mỹ xin mua chip nhớ CXMT. Đây là tin có nguồn, không phải đồn. Chỉ **kết quả xin phép** là chưa chắc. Ghi trên hình: *"Apple xin phép mua chip nhớ Trung Quốc — FT, 26/06/2026"*.
4. **B15 — "13/7 giảm khoảng 10%".** Dữ liệu: đóng cửa **−8,95%**. Từ đỉnh phiên xuống đáy phiên là −9,90% → lên hình ghi "−9,9% trong phiên" thì khớp lời đọc mà vẫn thật. Voice đã thu.
5. **B18 — "thấp hơn đỉnh chừng 1/3".** Thực tế **−27,64%**. Đề xuất hiện số, bỏ phân số.
6. ~~**B15 — "lần thứ bảy ngắt giao dịch".**~~ **ĐÃ GIẢI QUYẾT 29/09/2026 — lời đọc ĐÚNG.** Yonhap 13/07: *"lần thứ bảy trong năm nay KRX kích hoạt ngắt giao dịch."* Phép đếm 8 phiên từ OHLC của tôi sai vì ngắt giao dịch đòi mức giảm giữ trong 1 phút. Thêm ba số có nguồn cho B15: ngắt lúc **13:28** · dừng **20 phút** · đóng cửa **−8,95%**.
7. **B17 — "250 tỷ đô bốc hơi một phiên".** Vẫn không suy ra được cho *một phiên*. Nhưng đã có con số cho **toàn đợt**: **hơn 2 nghìn tỷ USD vốn hoá** (Unusual Whales qua Chosun 03/08). Đề xuất đổi sang con số này và ghi rõ là cả đợt, không phải một phiên.

21. **🟡 OUTRO đang thiếu một sự thật ngược chiều.** Morgan Stanley nâng Hàn Quốc lên **"overweight"** ngày 03/08, mục tiêu KOSPI **9.000**, coi đợt thanh lý là **cơ hội mua**. Và họ đúng một phần: đáy 5.593,56 (30/07) → hiện tại 6.919,81 = **+23,7%**. Video kết mà không nhắc là hở. Nêu ra làm video đáng tin hơn và không phá luận điểm — luận điểm là về đòn bẩy, không phải về việc giá không bao giờ hồi.
8. **Cấm dùng chữ "phiên tệ nhất".** Phiên giảm sâu nhất trong dữ liệu là **04/03/2026 (−12,06%)**, không phải 28/7 (−10,84%).
9. **HOOK 3 — số cổ phiếu đã kiểm.** Lời đọc "khoảng 14% / 15%"; số thật 28/07 là Samsung **−13,39%**, SK Hynix **−14,65%**. Storyboard đang in cứng −14% / −15% → sửa thành −13,4% / −14,6%. Dữ liệu: `data/Samsung_4H.csv`, `data/SKHynix_4H.csv`, tổng hợp ở `data/Stocks_Facts.md`.
10. **Cấm ghép "đợt hai nặng hơn đợt một" với số SK Hynix.** Đúng với chỉ số (−8,95% → −10,84%) nhưng ngược với SK Hynix: 13/07 nó rơi −15,37%, sâu hơn 28/07 (−14,65%).
11. **B22 "tiền rời Hàn Quốc" — tỷ giá nói ngược.** Won **mạnh lên 12,7%** suốt cú sập (USD/KRW 1.559 ngày 05/06 → 1.361 hôm nay), tức tiền chảy **vào**. Giữ ba sự kiện có nguồn (SpaceX, Nasdaq, Fed) nhưng **không để chữ "tiền rời Hàn Quốc" hay mũi tên Seoul → New York lên hình** khi chưa có dữ liệu dòng vốn ngoại ròng. Storyboard B22 đang vẽ đúng cái mũi tên đó. Chi tiết: `data/Cross_Market_Facts.md`.
12. **Đài Loan và Mỹ đã có dữ liệu** (`TAIEX_1D.csv`, `SP500_1D.csv`). B26–B27 và Phần 4 không còn phải nói chay.
13. **🔴 HOOK 1 lệch ngày với kết quả kinh doanh.** Cú sập −10,84% ngày **28/07** xảy ra **trước** khi hai công ty công bố: SK hynix công bố **29/07**, Samsung **30/07**. Lời đọc "đúng lúc cả 2 đang báo kết quả" đủ lỏng để giữ, nhưng **trên hình không được ghép ngày 28/07 với hai bảng kết quả như cùng một ngày** — storyboard HOOK 1 và HOOK 2 đang làm đúng cái đó. Xem `data/Link_Verification.md`.
14. **"$578 tỷ" — đã sửa lại lần hai, 29/09/2026.** Gốc là **896 nghìn tỷ won** (Yonhap 30/06/2026), không phải 800. Bóc tách: SK Group 470 + Samsung Group 425 + Amkor 1 = 896. **Lên hình ghi "896 NGHÌN TỶ WON · ≈ $578 TỶ · 30/06/2026".** Con số 800 nghìn tỷ won của AP là phạm vi hẹp hơn — chỉ phần nhà máy của hai *công ty* (Samsung Electronics 400 + SK hynix 400). Cả hai đều đúng. Lời đọc *"Chính phủ Hàn Quốc cùng 2 tập đoàn chip"* cũng **đúng** — Bộ Công Thương công bố "tầm nhìn S-WEST" và cam kết lo mặt bằng, điện, nước, nhân lực. Ghi chú cũ *"AP nói không có chính phủ"* đã bị bác.

15. **🔴 "1,2 triệu margin call / 300.000 thanh lý" là của ngày 13/07, KHÔNG phải 28/07.** Ảnh hưởng **B7 và B20 — cả hai đều là beat ★**. Bitget, Finimize và nhiều nguồn khác đều quy về cú rơi 9% một phiên đầu tuần đó = **13/07 (−8,95%)**. Storyboard phải gắn hai số này với 13/07. ⚠ Toàn bộ là nguồn thứ cấp — **phải mở được bài Reuters gốc trước khi cho lên hình**.

16. **🔴 ">60% dưới 30 tuổi" ở B20 là SAI — đã xác minh 29/09.** Số đúng: **62% dưới 35 tuổi** (Chosun Ilbo 03/08 dẫn Unusual Whales, khớp Reuters 20/07). **Lên hình ghi `62% DƯỚI 35 TUỔI`.** Và con số thanh lý: **hơn 300.000 tính đến 13/07** · **hơn 360.000 tính đến đầu 08**. Dùng số nào cũng được, nhưng **phải ghi mốc thời gian**.

17. **🔴 Cú sập 13/07 không phải do bong bóng AI.** Yonhap: nguyên nhân là **Mỹ–Iran đụng độ ở eo biển Hormuz**. Đòn bẩy là thứ khuếch đại nó thành −8,95% và 1,2 triệu margin call. **Không được nói 13/07 sập vì nghi ngờ nhu cầu AI.** Cách kể đúng — cú sốc từ bên ngoài, đòn bẩy biến nó thành thảm hoạ — thực ra mạnh hơn.

18. **B22 — số SpaceX ghi sai.** $75 tỷ là **quy mô thương vụ**, không phải lượng đặt mua. Lượng đặt mua từ cá nhân là **>$70 tỷ**. Và **phần chia cho nhà đầu tư quốc tế dưới 10%**, Hàn Quốc không được nhắc tới → thêm bằng chứng chống lại cách kể "tiền rời Hàn Quốc".

19. **B23 — "$250 tỷ" đã lỗi thời.** Nvidia hạ bảo lãnh xuống **dưới $120 tỷ** (14/08) rồi chốt **tối đa $105 tỷ** (17/08). Giữ $250 tỷ cho B23 vì đó là con số thị trường biết ngày 28/07, nhưng **phải ghi ngày 26/07 lên hình**. Diễn biến bị cắt giảm nên đưa vào Phần 4 — nó làm mạnh thêm luận điểm.

20. **B29 — "FCF thấp nhất 10 năm" nói nhẹ quá.** Alphabet **đã âm FCF quý 2** (lần đầu), Microsoft được dự báo âm quý 4 — **lần đầu kể từ ít nhất 2001**. Nợ tăng thêm chiếm **một phần ba** capex, so với 9% hai năm trước. Nên sửa lời trên hình.

### Nguồn còn thiếu
- C9 (14 năm thu nhập, B10) — chưa có link
- C10 (phễu 1,2 triệu → 300k, B20) — có link nhưng chưa xác định vị trí
- 6 link trong bình luận Google Doc chưa xác định neo ở câu nào
- `x.com/KobeissiLetter/status/2068724299158978671` — chưa biết thuộc beat nào

Chi tiết: `Sources.md`

### Dữ liệu
- **KOSPI — đã có** (28/09/2026). `data/KOSPI_1D.csv` 428 phiên 20/12/2024 → 28/09/2026, `KOSPI_4H.csv`, `KOSPI_1H.csv` (1H chỉ từ 22/06/2026). Số đã kiểm chứng: `data/KOSPI_Facts.md`. Chart dựng từ dữ liệu thật: `charts/KOSPI_sheet.png` (nguồn HTML + `kospi_data.js` nằm cùng thư mục) — **thay hẳn đường vẽ tay**, không dùng chart ba cột tạm nữa.
- Đỉnh **9.114,55** (22/06/2026) → đáy **5.593,56** (30/07/2026) = **−38,63%**. Hiện tại 6.919,81.

### Asset chưa làm
- Icon IC1–IC7 · bản đồ M1–M3 · world shot W2–W7
- `assets/W1_bg.png` — cần Upscayl ×4 từ `W1_raw.webp`

### Storyboard ảnh
39 frame trong `storyboard/frames/` còn hiển thị concept cũ (trước khi thêm chart) ở: **HOOK 3, B12, B13, B14, B25, B27**. Vẽ lại khi dựng tới các beat đó.

**B15, B17, B18** đang ghi thẳng trên frame là *"KOSPI (illustrative)"* — đường vẽ tay. Đã có dữ liệu thật nên **ba frame này phải vẽ lại** bằng `LIB_KOSPI_Line`. HOOK 3 cũng cần sửa: cột KOSPI đang ghi −10%, số thật là **−10,84%**.

### Tài liệu
- Google Doc `1v_4C697QcNW0QGxZ7Plw57ciK22bGWo1IBxPQqbIRAw` — cần Find & Replace bỏ dấu `**` còn sót trong các bảng.
