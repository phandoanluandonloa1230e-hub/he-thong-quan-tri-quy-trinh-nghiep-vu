# CHƯƠNG 2: HỆ THỐNG QUY TRÌNH NGHIỆP VỤ HASAKI
## Mục c) NHÓM QUY TRÌNH HỖ TRỢ (SUPPORT PROCESSES)

*Người thực hiện: Hải*

---

## 0. Cách xác định nhóm quy trình hỗ trợ

Quy trình hỗ trợ là các quy trình **không trực tiếp tạo ra giá trị cho khách hàng bên ngoài**, nhưng cung cấp nguồn lực (con người, hệ thống thông tin, hàng hóa, tài chính, cơ sở vật chất) để nhóm quy trình cốt lõi vận hành được. Vì vậy **khách hàng của quy trình hỗ trợ chủ yếu là khách hàng nội bộ** (cửa hàng, clinic, kho, các phòng ban), còn khách hàng cuối chỉ hưởng lợi gián tiếp.

**Đề xuất nhánh "móng nhà" (nhóm hỗ trợ) cho mô hình ngôi nhà (gửi Luân tổng hợp):**

| Mã | Tên quy trình hỗ trợ |
|----|----------------------|
| HT-01 | Tuyển dụng và đào tạo hội nhập nhân sự tuyến đầu |
| HT-02 | Tiếp nhận và xử lý sự cố hệ thống CNTT (website/app, POS, phần mềm đặt lịch) |
| HT-03 | Kiểm kê hàng hóa định kỳ và xử lý chênh lệch tồn kho tại chi nhánh |



---

## HT-01. QUY TRÌNH TUYỂN DỤNG VÀ ĐÀO TẠO HỘI NHẬP NHÂN SỰ TUYẾN ĐẦU

**Phạm vi:** áp dụng cho các vị trí tuyến đầu tại chi nhánh, gồm nhân viên tư vấn mỹ phẩm, thu ngân, nhân viên đóng gói của khối Cửa hàng; kỹ thuật viên spa, điều dưỡng da liễu, tư vấn viên của khối Clinic. Bắt đầu từ khi phát sinh nhu cầu nhân sự, kết thúc khi nhân viên được ký hợp đồng chính thức hoặc chấm dứt sau thử việc.

**Lý do đây là quy trình hỗ trợ:** Hasaki mở rộng chuỗi chi nhánh liên tục trên toàn quốc, mỗi chi nhánh mới cần một đội ngũ tuyến đầu được chuẩn hóa. Chất lượng tư vấn và tay nghề kỹ thuật viên quyết định trực tiếp chất lượng của quy trình cốt lõi (bán hàng tại cửa hàng, cung cấp dịch vụ clinic), nhưng bản thân việc tuyển và đào tạo không tạo doanh thu.

### a) Tác nhân (Actor)

| Tác nhân | Vai trò trong quy trình |
|----------|-------------------------|
| Cửa hàng trưởng / Quản lý Clinic | Người đề xuất nhu cầu tuyển dụng, phỏng vấn vòng chuyên môn, đánh giá kết quả thử việc |
| Trưởng khối Vận hành | Phê duyệt định biên và nhu cầu tuyển dụng |
| Chuyên viên tuyển dụng (mảng Retail / mảng Clinic) | Đăng tin, sàng lọc hồ sơ, phỏng vấn sơ loại, gửi thư mời nhận việc, theo dõi tiến độ |
| Trưởng phòng Nhân sự | Phê duyệt mức lương đề xuất, phê duyệt kết quả tuyển dụng |
| Ứng viên | Tác nhân bên ngoài: nộp hồ sơ, tham gia phỏng vấn, phản hồi thư mời nhận việc |
| Bộ phận Đào tạo | Tổ chức đào tạo hội nhập: kiến thức sản phẩm, quy trình tư vấn, chuẩn dịch vụ, quy tắc an toàn và vô khuẩn cho khối Clinic |
| Nhân sự tiền lương và Hành chính (C&B) | Hoàn tất hồ sơ, hợp đồng, bảo hiểm, chấm công |
| Bộ phận CNTT | Cấp tài khoản POS, phần mềm bán hàng, phần mềm đặt lịch cho nhân viên mới |
| Hệ thống quản lý tuyển dụng và các kênh tuyển dụng | Tiếp nhận, lưu trữ hồ sơ ứng viên |

### b) Mô tả quy trình bằng lời: các bước

1. Cửa hàng trưởng hoặc Quản lý Clinic phát hiện thiếu hụt nhân sự (nhân viên nghỉ việc, mở chi nhánh mới, tăng ca dịp cao điểm) và lập **Phiếu đề xuất tuyển dụng**, ghi rõ vị trí, số lượng, thời điểm cần người và yêu cầu năng lực.
2. Trưởng khối Vận hành xem xét phiếu đề xuất, đối chiếu với định biên và ngân sách nhân sự đã duyệt. Nếu không hợp lý, phiếu được trả về cho bộ phận đề xuất điều chỉnh hoặc từ chối.
3. Sau khi được duyệt, Chuyên viên tuyển dụng tiếp nhận yêu cầu, xác định kênh tuyển dụng phù hợp (website tuyển dụng của công ty, các trang việc làm, mạng xã hội, giới thiệu nội bộ) và đăng tin tuyển dụng.
4. Chuyên viên tuyển dụng đồng thời rà soát nguồn ứng viên có sẵn trong cơ sở dữ liệu và cân nhắc phương án điều chuyển nội bộ từ chi nhánh khác trước khi tuyển mới.
5. Ứng viên nộp hồ sơ qua các kênh. Chuyên viên tuyển dụng sàng lọc hồ sơ theo tiêu chí của vị trí (độ tuổi, kinh nghiệm, chứng chỉ hành nghề đối với điều dưỡng và kỹ thuật viên, khả năng làm việc theo ca).
6. Với hồ sơ đạt yêu cầu, Chuyên viên tuyển dụng liên hệ ứng viên đặt lịch và tiến hành **phỏng vấn sơ loại** (trực tuyến hoặc trực tiếp), đánh giá thái độ, kỹ năng giao tiếp, khả năng làm ca. Hồ sơ không đạt được lưu vào nguồn dự phòng và gửi thư cảm ơn.
7. Ứng viên qua vòng sơ loại được chuyển sang **phỏng vấn chuyên môn** với Cửa hàng trưởng hoặc Quản lý Clinic. Riêng vị trí kỹ thuật viên spa và điều dưỡng da liễu có thêm **bài kiểm tra tay nghề thực hành**.
8. Bộ phận đề xuất và Chuyên viên tuyển dụng thống nhất kết quả đánh giá, xếp hạng ứng viên và đề xuất mức lương.
9. Trưởng phòng Nhân sự phê duyệt kết quả và mức lương đề xuất.
10. Chuyên viên tuyển dụng gửi **thư mời nhận việc** cho ứng viên, nêu rõ vị trí, chi nhánh làm việc, thu nhập, thời gian thử việc và ngày bắt đầu.
11. Ứng viên phản hồi. Nếu từ chối, Chuyên viên tuyển dụng chuyển sang ứng viên dự phòng kế tiếp hoặc mở lại tin tuyển dụng.
12. Ứng viên đồng ý sẽ nộp hồ sơ nhân sự, khám sức khỏe theo quy định và ký **hợp đồng thử việc** với bộ phận C&B. Bộ phận CNTT cấp tài khoản hệ thống theo phân quyền của vị trí.
13. Bộ phận Đào tạo tổ chức **đào tạo hội nhập**: giới thiệu công ty và văn hóa doanh nghiệp, kiến thức nền về mỹ phẩm và thành phần hoạt chất, quy trình tư vấn và bán hàng, quy trình thanh toán trên POS, chuẩn phục vụ khách hàng; riêng khối Clinic bổ sung quy trình vô khuẩn, an toàn thiết bị và xử lý sự cố trong dịch vụ.
14. Kết thúc khóa đào tạo, học viên làm **bài kiểm tra cuối khóa**. Người chưa đạt được đào tạo bổ sung và kiểm tra lại một lần.
15. Nhân viên mới về chi nhánh làm việc trong giai đoạn thử việc, được người kèm cặp trực tiếp hướng dẫn tại quầy hoặc tại phòng dịch vụ.
16. Hết thời gian thử việc, Cửa hàng trưởng hoặc Quản lý Clinic **đánh giá kết quả thử việc** theo các tiêu chí: doanh số tư vấn, tuân thủ quy trình, thái độ với khách hàng, chuyên cần.
17. Trưởng phòng Nhân sự phê duyệt kết quả đánh giá và ra quyết định: ký hợp đồng chính thức, kéo dài thời gian thử việc, hoặc chấm dứt.
18. Bộ phận C&B hoàn tất hợp đồng lao động, đăng ký bảo hiểm, cập nhật hồ sơ nhân sự lên hệ thống và lưu trữ. Chuyên viên tuyển dụng đóng yêu cầu tuyển dụng và lập báo cáo định kỳ về tiến độ tuyển dụng.

### c) Đối tượng khách hàng của quy trình

- **Khách hàng nội bộ (chính):** Cửa hàng trưởng, Quản lý Clinic và các chi nhánh có nhu cầu nhân sự, vì họ là bên nhận "đầu ra" là nhân viên đã được tuyển và đào tạo đạt chuẩn.
- **Khách hàng nội bộ liên quan:** Trưởng khối Vận hành (đảm bảo đủ nhân lực cho kế hoạch mở rộng chuỗi), Phòng Nhân sự (dữ liệu nhân sự).
- **Đối tượng tham gia bên ngoài:** ứng viên ứng tuyển vào các vị trí tuyến đầu.
- **Khách hàng cuối (hưởng lợi gián tiếp):** khách hàng mua mỹ phẩm và sử dụng dịch vụ tại Hasaki, vì họ được phục vụ bởi nhân viên đã qua đào tạo chuẩn.

### d) Các khả năng kết quả của quy trình

1. Tuyển dụng thành công: ứng viên hoàn thành đào tạo, đạt thử việc và được ký hợp đồng chính thức.
2. Đề xuất tuyển dụng bị từ chối hoặc bị hoãn do vượt định biên, vượt ngân sách hoặc thay đổi kế hoạch mở chi nhánh.
3. Nhu cầu được đáp ứng bằng điều chuyển nội bộ, không phát sinh tuyển mới.
4. Không tìm được ứng viên đạt yêu cầu sau một chu kỳ đăng tin, phải mở lại tin, điều chỉnh tiêu chí hoặc mức lương.
5. Ứng viên từ chối thư mời nhận việc hoặc không đến nhận việc đúng hẹn, chuyển sang ứng viên dự phòng.
6. Nhân viên không đạt bài kiểm tra cuối khóa đào tạo, phải đào tạo bổ sung, hoặc dừng nếu vẫn không đạt.
7. Không đạt đánh giá thử việc, kéo dài thời gian thử việc hoặc chấm dứt hợp đồng thử việc.
8. Nhân viên tự nghỉ trong thời gian thử việc, yêu cầu tuyển dụng được mở lại.

---

## HT-02. QUY TRÌNH TIẾP NHẬN VÀ XỬ LÝ SỰ CỐ HỆ THỐNG CÔNG NGHỆ THÔNG TIN

**Phạm vi:** xử lý sự cố phát sinh trên các hệ thống vận hành của Hasaki, gồm website và ứng dụng hasaki.vn, hệ thống POS và máy in hóa đơn tại chi nhánh, phần mềm đặt lịch dịch vụ Clinic, hệ thống quản lý kho, cổng thanh toán và hạ tầng mạng tại cửa hàng. Bắt đầu từ khi sự cố được ghi nhận, kết thúc khi phiếu sự cố được đóng và lưu hồ sơ.

**Lý do đây là quy trình hỗ trợ:** Hasaki vận hành mô hình đa kênh: bán tại chuỗi chi nhánh, bán trực tuyến với cam kết giao nhanh trong 2 giờ, đặt lịch dịch vụ tại clinic. Toàn bộ đều phụ thuộc vào hệ thống CNTT. Một sự cố POS hay sự cố cổng thanh toán làm dừng ngay quy trình cốt lõi, nhưng bản thân hoạt động CNTT là hoạt động hỗ trợ.

### a) Tác nhân (Actor)

| Tác nhân | Vai trò trong quy trình |
|----------|-------------------------|
| Người báo sự cố (nhân viên cửa hàng, thu ngân, lễ tân clinic, nhân viên kho, nhân viên văn phòng) | Phát hiện và khai báo sự cố |
| Hệ thống giám sát tự động | Tự động phát sinh cảnh báo khi dịch vụ ngừng hoạt động hoặc vượt ngưỡng |
| Nhân viên hỗ trợ CNTT cấp 1 (Helpdesk) | Tiếp nhận, phân loại, xác định mức độ ưu tiên, xử lý sự cố cơ bản |
| Kỹ thuật viên hạ tầng và vận hành (cấp 2) | Xử lý sự cố mạng, máy chủ, thiết bị POS, cơ sở dữ liệu |
| Đội phát triển phần mềm (cấp 3) | Xử lý lỗi ứng dụng, lỗi nghiệp vụ trên website/app, phát hành bản vá |
| Trưởng phòng CNTT | Phê duyệt xử lý sự cố nghiêm trọng, quyết định phương án tạm thời, phê duyệt thay đổi khẩn |
| Nhà cung cấp dịch vụ bên ngoài | Đơn vị hạ tầng, cổng thanh toán, đối tác vận chuyển, phối hợp khi nguyên nhân nằm ngoài phạm vi công ty |
| Bộ phận Vận hành / Chăm sóc khách hàng | Được thông báo để áp dụng phương án thủ công tạm thời và thông tin đến khách hàng |
| Hệ thống quản lý phiếu sự cố | Lưu trữ, theo dõi trạng thái và thời hạn xử lý |

### b) Mô tả quy trình bằng lời: các bước

1. Sự cố được ghi nhận theo một trong hai nguồn: người dùng nội bộ phát hiện và báo qua tổng đài nội bộ, nhóm chat hoặc biểu mẫu khai báo; hoặc hệ thống giám sát tự động phát cảnh báo.
2. Nhân viên hỗ trợ CNTT cấp 1 **tạo phiếu sự cố** trên hệ thống, ghi nhận thông tin: chi nhánh, hệ thống bị ảnh hưởng, thời điểm phát sinh, mô tả hiện tượng, ảnh chụp màn hình hoặc mã lỗi.
3. Nhân viên cấp 1 **phân loại sự cố** theo nhóm (phần cứng POS, mạng, ứng dụng, dữ liệu, tài khoản và phân quyền) và **xác định mức độ ưu tiên** dựa trên phạm vi ảnh hưởng và mức độ gián đoạn kinh doanh. Sự cố làm dừng thanh toán tại nhiều chi nhánh hoặc dừng đặt hàng trên website được xếp mức nghiêm trọng.
4. Với sự cố nghiêm trọng, nhân viên cấp 1 thông báo ngay cho Trưởng phòng CNTT và bộ phận Vận hành để kích hoạt **phương án dự phòng tạm thời** (ghi nhận đơn thủ công, chuyển sang hình thức thanh toán khác, tạm ngưng nhận đặt lịch).
5. Nhân viên cấp 1 tiến hành **chẩn đoán và xử lý ban đầu** dựa trên cơ sở tri thức có sẵn: hướng dẫn khởi động lại thiết bị, kiểm tra kết nối, cấp lại mật khẩu, xóa bộ nhớ đệm.
6. Nếu xử lý được, nhân viên cấp 1 chuyển sang bước xác nhận với người báo sự cố.
7. Nếu không xử lý được trong thời hạn cam kết của cấp 1, phiếu được **chuyển lên kỹ thuật viên cấp 2**. Kỹ thuật viên cấp 2 kiểm tra nhật ký hệ thống, thiết bị mạng, máy chủ, cơ sở dữ liệu, và xử lý theo phạm vi kỹ thuật của mình; nếu cần thì cử người xuống trực tiếp chi nhánh.
8. Nếu nguyên nhân được xác định là **lỗi phần mềm**, phiếu tiếp tục được chuyển cho đội phát triển. Đội phát triển tái hiện lỗi, xác định nguyên nhân, chuẩn bị bản sửa lỗi và kiểm thử trên môi trường thử nghiệm.
9. Nếu nguyên nhân nằm ở **bên thứ ba** (hạ tầng, cổng thanh toán, đối tác vận chuyển), Trưởng phòng CNTT mở yêu cầu hỗ trợ với nhà cung cấp và theo dõi tiến độ khắc phục từ phía họ.
10. Với thay đổi có rủi ro cao lên hệ thống đang chạy, Trưởng phòng CNTT **phê duyệt thay đổi khẩn** trước khi triển khai.
11. Bộ phận chịu trách nhiệm triển khai giải pháp lên môi trường vận hành và **kiểm tra lại chức năng bị lỗi**.
12. Nhân viên hỗ trợ CNTT liên hệ **người báo sự cố để xác nhận** hệ thống đã hoạt động bình thường. Nếu người dùng xác nhận chưa ổn, phiếu được mở lại và quay về bước chẩn đoán.
13. Sau khi được xác nhận, nhân viên cấp 1 **cập nhật cách xử lý vào cơ sở tri thức** và **đóng phiếu sự cố**.
14. Với các sự cố nghiêm trọng, Trưởng phòng CNTT tổ chức **phân tích nguyên nhân gốc**, lập báo cáo và đề xuất hành động phòng ngừa.
15. Định kỳ, phòng CNTT tổng hợp báo cáo số lượng sự cố, thời gian xử lý trung bình, tỷ lệ đáp ứng cam kết dịch vụ và các sự cố lặp lại để cải tiến.

### c) Đối tượng khách hàng của quy trình

- **Khách hàng nội bộ (chính):** nhân viên và quản lý tại các chi nhánh, kho, clinic và văn phòng, là những người trực tiếp sử dụng hệ thống để phục vụ khách hàng.
- **Khách hàng nội bộ liên quan:** bộ phận Vận hành, Chăm sóc khách hàng, Kế toán (khi sự cố ảnh hưởng đến số liệu bán hàng và thanh toán).
- **Khách hàng cuối (hưởng lợi gián tiếp và có thể chịu ảnh hưởng trực tiếp):** khách hàng đang thanh toán tại quầy, đang đặt hàng trên website/app hoặc đang chờ đặt lịch dịch vụ tại clinic.

### d) Các khả năng kết quả của quy trình

1. Sự cố được xử lý ngay ở cấp 1 trong thời gian ngắn, không cần chuyển tiếp.
2. Sự cố được xử lý ở cấp 2 hoặc cấp 3, hệ thống phục hồi hoàn toàn và phiếu được đóng.
3. Sự cố được khắc phục tạm thời bằng giải pháp thay thế, giữ phiếu ở trạng thái chờ để xử lý triệt để trong bản phát hành kế tiếp.
4. Nguyên nhân thuộc về nhà cung cấp bên ngoài, thời gian khắc phục phụ thuộc bên thứ ba, công ty phải duy trì phương án vận hành thủ công.
5. Không tái hiện được lỗi hoặc lỗi tự hết, phiếu được đóng kèm ghi chú theo dõi.
6. Phiếu bị hủy do khai báo sai, trùng lặp với phiếu đang xử lý, hoặc thực tế là yêu cầu dịch vụ chứ không phải sự cố (ví dụ yêu cầu cấp thêm tài khoản).
7. Người dùng không xác nhận đã khắc phục, phiếu được mở lại và xử lý tiếp.
8. Sự cố nghiêm trọng dẫn đến báo cáo phân tích nguyên nhân gốc và hành động phòng ngừa, thậm chí thay thế thiết bị hoặc nâng cấp hạ tầng.

---

## HT-03. QUY TRÌNH KIỂM KÊ HÀNG HÓA ĐỊNH KỲ VÀ XỬ LÝ CHÊNH LỆCH TỒN KHO TẠI CHI NHÁNH

**Phạm vi:** kiểm kê hàng hóa thực tế tại chi nhánh (khu vực trưng bày và kho phụ của cửa hàng) hoặc tại kho trung tâm, đối chiếu với tồn kho trên hệ thống và xử lý chênh lệch. Bắt đầu từ kế hoạch kiểm kê định kỳ, kết thúc khi số liệu được điều chỉnh và hồ sơ kiểm kê được lưu trữ.

**Lý do đây là quy trình hỗ trợ:** với danh mục hàng nghìn mã sản phẩm từ hàng trăm thương hiệu, và cam kết giao nhanh dựa trên tồn kho tại chi nhánh gần khách hàng nhất, độ chính xác tồn kho là điều kiện để quy trình bán hàng và giao hàng chạy đúng. Kiểm kê không tạo doanh thu nhưng bảo vệ tính đúng đắn của dữ liệu và tài sản.

### a) Tác nhân (Actor)

| Tác nhân | Vai trò trong quy trình |
|----------|-------------------------|
| Phòng Kế toán kho | Lập kế hoạch kiểm kê, kết xuất số liệu tồn sổ sách, đối chiếu, hạch toán điều chỉnh |
| Trưởng khối Vận hành | Phê duyệt kế hoạch kiểm kê và kết quả xử lý chênh lệch |
| Cửa hàng trưởng / Thủ kho | Chủ trì kiểm kê tại đơn vị, bố trí nhân sự, ký biên bản |
| Nhân viên cửa hàng / nhân viên kho | Thực hiện đếm thực tế, quét mã vạch, ghi phiếu kiểm kê |
| Tổ kiểm kê độc lập / Kiểm soát nội bộ | Giám sát, kiểm tra xác suất, chứng kiến đếm lại |
| Hệ thống quản lý kho và bán hàng | Cung cấp tồn sổ sách, ghi nhận kết quả đếm, tính chênh lệch, cập nhật sau điều chỉnh |
| Phòng Nhân sự | Tham gia khi có xử lý trách nhiệm cá nhân với chênh lệch do thất thoát |

### b) Mô tả quy trình bằng lời: các bước

1. Phòng Kế toán kho lập **kế hoạch kiểm kê** theo định kỳ (tháng, quý, cuối năm) hoặc kiểm kê đột xuất khi có dấu hiệu bất thường, khi thay đổi cửa hàng trưởng, hoặc trước và sau các đợt khuyến mãi lớn.
2. Trưởng khối Vận hành **phê duyệt kế hoạch**: danh sách chi nhánh, thời điểm, phạm vi mã hàng, thành phần tổ kiểm kê.
3. Kế toán kho **thông báo kế hoạch** đến các chi nhánh liên quan trước thời điểm kiểm kê để đơn vị chuẩn bị.
4. Cửa hàng trưởng chuẩn bị hiện trường: sắp xếp lại hàng hóa theo khu vực, tách riêng hàng chờ trả nhà cung cấp, hàng lỗi, hàng cận hạn sử dụng và hàng đã bán chờ giao.
5. Đến thời điểm kiểm kê, hệ thống **tạm khóa các giao dịch nhập và xuất** tại đơn vị hoặc chốt số liệu tại một mốc thời gian xác định để có tồn sổ sách làm cơ sở đối chiếu.
6. Kế toán kho **kết xuất số liệu tồn kho trên hệ thống** và tạo phiếu kiểm kê. Danh sách này không được phát cho người đếm để bảo đảm tính khách quan.
7. Nhân viên tiến hành **đếm thực tế** theo từng khu vực, mỗi khu vực do ít nhất hai người thực hiện, sử dụng máy quét mã vạch, ghi nhận số lượng và ghi chú tình trạng hàng (còn hạn, cận hạn, hư hỏng bao bì).
8. Kết quả đếm được **nhập vào hệ thống**; hệ thống tự động **so sánh với tồn sổ sách** và xuất danh sách các mã có chênh lệch.
9. Với các mã có chênh lệch, tổ kiểm kê tiến hành **đếm lại lần hai** dưới sự chứng kiến của Kiểm soát nội bộ hoặc Cửa hàng trưởng.
10. Nếu sau lần đếm lại số liệu khớp, mã hàng đó được ghi nhận là đếm sai và loại khỏi danh sách chênh lệch.
11. Nếu vẫn còn chênh lệch, bộ phận liên quan **xác minh nguyên nhân**: chứng từ nhập xuất chưa cập nhật, hàng đang luân chuyển giữa các chi nhánh, hàng tặng kèm khuyến mãi chưa trừ tồn, hàng dùng thử tại quầy, hàng hư hỏng chưa lập biên bản, hoặc thất thoát.
12. Tổ kiểm kê **lập biên bản kiểm kê** ghi rõ số lượng thừa, thiếu theo từng mã, giá trị chênh lệch, nguyên nhân xác định được và đề xuất hướng xử lý. Biên bản có chữ ký của các bên tham gia.
13. Kế toán kho **tổng hợp và trình duyệt**. Trưởng khối Vận hành cùng Kế toán trưởng xem xét: chênh lệch trong ngưỡng cho phép được duyệt điều chỉnh; chênh lệch vượt ngưỡng hoặc nghi ngờ thất thoát được chuyển sang **điều tra bổ sung**.
14. Sau khi có phê duyệt, Kế toán kho **thực hiện bút toán điều chỉnh** và cập nhật lại tồn kho trên hệ thống; hàng hư hỏng, hết hạn được xử lý theo quy định hủy hoặc trả nhà cung cấp.
15. Trường hợp xác định có trách nhiệm cá nhân, Phòng Nhân sự phối hợp xử lý theo quy chế lao động (nhắc nhở, bồi thường, kỷ luật).
16. Hệ thống **mở lại giao dịch nhập và xuất** tại đơn vị, hoạt động bán hàng trở lại bình thường.
17. Kế toán kho **lưu hồ sơ kiểm kê** và lập báo cáo tổng hợp: tỷ lệ chính xác tồn kho, giá trị chênh lệch theo chi nhánh, nhóm hàng có sai lệch lặp lại, làm đầu vào cho việc cải tiến quy trình nhập xuất và bố trí trưng bày.

### c) Đối tượng khách hàng của quy trình

- **Khách hàng nội bộ (chính):** Phòng Kế toán và Ban lãnh đạo, là bên cần số liệu tồn kho chính xác để lập báo cáo tài chính và ra quyết định nhập hàng.
- **Khách hàng nội bộ liên quan:** bộ phận Mua hàng và Kế hoạch (dự báo nhu cầu, đặt hàng nhà cung cấp), bộ phận Vận hành và Thương mại điện tử (hiển thị tình trạng còn hàng trên website và app), chi nhánh (bảo vệ trách nhiệm quản lý tài sản).
- **Khách hàng cuối (hưởng lợi gián tiếp):** khách hàng mua sắm trực tuyến và tại cửa hàng, vì tồn kho chính xác giúp tránh tình trạng đặt hàng thành công nhưng bị hủy đơn do thực tế hết hàng, bảo đảm cam kết giao nhanh.

### d) Các khả năng kết quả của quy trình

1. Kiểm kê khớp hoàn toàn, không phát sinh chênh lệch, biên bản ghi nhận và đóng đợt kiểm kê.
2. Có chênh lệch nhưng do đếm sai, số liệu khớp lại sau lần đếm thứ hai, không cần điều chỉnh sổ sách.
3. Chênh lệch do chứng từ chưa cập nhật, cần cập nhật bổ sung chứng từ, tồn kho khớp lại mà không phải hạch toán thất thoát.
4. Chênh lệch trong ngưỡng cho phép, được phê duyệt điều chỉnh tồn kho và hạch toán vào chi phí.
5. Chênh lệch vượt ngưỡng hoặc có dấu hiệu thất thoát, chuyển điều tra bổ sung, có thể dẫn tới kiểm kê lại toàn bộ, xử lý trách nhiệm cá nhân hoặc bồi thường.
6. Phát hiện hàng hư hỏng, hết hạn sử dụng, lập biên bản hủy hoặc trả nhà cung cấp, giảm tồn tương ứng.
7. Kiểm kê phải tạm dừng hoặc dời lịch do sự cố (mất kết nối hệ thống, thiếu nhân sự, trùng đợt cao điểm bán hàng).
8. Kết quả kiểm kê làm phát sinh đề xuất cải tiến: điều chỉnh quy trình nhập xuất, thay đổi cách trưng bày, tăng tần suất kiểm kê với nhóm hàng giá trị cao.

---

## 4. HAI QUY TRÌNH ĐƯỢC CHỌN ĐỂ MÔ HÌNH HÓA BẰNG BPMN

**Chọn: HT-01 (Tuyển dụng và đào tạo hội nhập nhân sự tuyến đầu) và HT-02 (Tiếp nhận và xử lý sự cố hệ thống CNTT).**

**Lý do lựa chọn:**

- **HT-01** có một tác nhân bên ngoài rõ ràng là ứng viên, nên khi vẽ sẽ thể hiện được **hai pool và luồng thông điệp** giữa doanh nghiệp với bên ngoài, đúng trọng tâm của BPMN cộng tác. Trong pool doanh nghiệp có nhiều lane (bộ phận đề xuất, tuyển dụng, nhân sự, đào tạo, CNTT), nhiều điểm rẽ nhánh quyết định (duyệt/không duyệt, đạt/không đạt phỏng vấn, nhận/từ chối offer, đạt/không đạt thử việc) và nhiều điểm kết thúc khác nhau.
- **HT-02** thể hiện được các cấu trúc nâng cao: **sự kiện bắt đầu kép** (người dùng báo lỗi hoặc hệ thống giám sát tự cảnh báo), **sự kiện biên theo thời gian** cho cam kết thời hạn xử lý, **luồng leo thang** qua ba cấp hỗ trợ, **vòng lặp quay lại** khi người dùng không xác nhận đã khắc phục, và nhánh phối hợp với nhà cung cấp bên ngoài.
- **HT-03 không được chọn** vì hai lý do: một là cấu trúc luồng đơn giản hơn (chủ yếu là một nhánh chính với một vòng lặp đếm lại), hai là **có rủi ro trùng phạm vi với nhóm quy trình cốt lõi** mà Quang và Phúc phụ trách nếu các bạn chọn quy trình nhập hàng hoặc quy trình xử lý đơn hàng và giao nhanh. Giữ HT-03 ở dạng mô tả chi tiết là đủ đáp ứng yêu cầu "mô tả tối thiểu 3 quy trình hỗ trợ".

**Ghi chú chuẩn bị cho bước vẽ (chưa vẽ ở giai đoạn này):**

| | HT-01 | HT-02 |
|---|---|---|
| Pool | Pool 1: Hasaki / Pool 2: Ứng viên | Pool 1: Hasaki / Pool 2: Nhà cung cấp dịch vụ bên ngoài |
| Lane trong pool Hasaki | Bộ phận đề xuất (Cửa hàng/Clinic), Tuyển dụng, Trưởng phòng Nhân sự & C&B, Đào tạo, CNTT | Người dùng nội bộ, Hỗ trợ cấp 1, Kỹ thuật cấp 2, Phát triển phần mềm cấp 3, Trưởng phòng CNTT |
| Sự kiện bắt đầu | Phát sinh nhu cầu nhân sự | Nhận thông báo sự cố (message) hoặc cảnh báo tự động |
| Điểm rẽ nhánh chính | Duyệt định biên; kết quả phỏng vấn; phản hồi offer; kết quả kiểm tra đào tạo; kết quả thử việc | Mức độ ưu tiên; xử lý được ở cấp 1 hay không; loại nguyên nhân (hạ tầng / phần mềm / bên thứ ba); người dùng xác nhận hay không |
| Sự kiện kết thúc | Ký hợp đồng chính thức / Từ chối tuyển / Chấm dứt sau thử việc / Hủy nhu cầu tuyển | Đóng phiếu thành công / Đóng phiếu với giải pháp tạm thời / Hủy phiếu |

---

## 5. Hai điểm cần thống nhất với nhóm

1. **Tên pháp nhân trong Chương 1.** Đầu việc ghi "Công ty TNHH Hasaki Beauty & S.P.A", trong khi pháp nhân hiện nay là **Công ty Cổ phần Hasaki Beauty & Clinic** (thành lập tháng 4/2016, chuyển đổi thương hiệu từ Hasaki Beauty & S.P.A sang Hasaki Beauty & Clinic). Nên trao đổi với Luân để Chương 1 nêu rõ mốc chuyển đổi này, tránh việc thầy hỏi lại.
2. **Tránh trùng phạm vi giữa các nhóm quy trình.** Nếu Quang và Phúc chọn quy trình nhập hàng hoặc quản lý tồn kho vào nhóm cốt lõi, nhóm hỗ trợ sẽ thay HT-03 bằng **HT-04 (đối chiếu và thanh toán công nợ nhà cung cấp)** hoặc **HT-05 (bảo trì cơ sở vật chất và thiết bị tại Clinic)**. Cần chốt sớm trước khi cả nhóm bước sang giai đoạn vẽ BPMN.
