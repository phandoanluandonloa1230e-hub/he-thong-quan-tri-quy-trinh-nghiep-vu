# **Báo Cáo Phân Tích Và Mô Hình Hóa Quy Trình Order-To-Delivery (O2D) Tại** 

# **Hasaki.vn** 

Lưu ý học thuật: Nội dung dưới đây được xây dựng dựa trên các chính sách công khai của Hasaki về đặt hàng, thanh toán trực tuyến, chính sách vận chuyển (dịch vụ NowFree 2H và giao hàng toàn quốc 48H) và đổi trả sản phẩm, kết hợp với các thông lệ quản trị quy trình nghiệp vụ (Business Process Management - BPM) và chuỗi cung ứng trong bán lẻ thương mại điện tử<sup>1</sup> . Một số bước xử lý nội bộ về hệ thống quản lý đơn hàng (OMS), quản lý kho (WMS), phân công shipper và kiểm soát chất lượng đóng gói được giả định hợp lý nhằm phục vụ mục đích mô hình hóa BPMN và phân tích vận hành<sup>1</sup> . 

## **Chương 2. Hệ thống quy trình nghiệp vụ Order-to-Delivery (O2D)** 

### **2.1. Thông tin chung** 

Tên quy trình: Quy trình từ Đặt hàng đến Giao hàng (Order-to-Delivery Process - O2D)<sup>1</sup> . Nhóm quy trình: Quy trình cốt lõi (Core Process)<sup>1</sup> . 

Trong mô hình kinh doanh thương mại điện tử (TMĐT) và bán lẻ đa kênh (Omnichannel) mỹ phẩm của Hasaki, quy trình Order-to-Delivery (O2D) đóng vai trò là chuỗi giá trị cốt lõi khép kín<sup>1</sup> . Quy trình bao phủ toàn bộ vòng đời của một giao  dịch: bắt đầu từ khi khách hàng duyệt tìm sản phẩm và tạo đơn hàng trên kênh số (Website Hasaki.vn / App Hasaki), đi qua các bước kiểm tra thanh toán, phân luồng dữ liệu tại hệ thống OMS, xử lý lấy hàng và đóng gói tại kho (Fulfillment), cho đến khi đơn hàng được điều phối vận chuyển và giao tận tay người nhận thành công<sup>1</sup> . Sự mượt mà và tối ưu của quy trình O2D trực  tiếp quyết định tỷ lệ đáp ứng cam kết thời gian (SLA NowFree 2H / 48H), chi phí vận hành logistics và chỉ số hài lòng của khách hàng (CSAT)<sup>1</sup> . 

### **2.2. Các tác nhân tham gia** 

Quy trình Order-to-Delivery là sự kết nối liên tục giữa người dùng, hạ tầng công nghệ và lực lượng vận hành logistics: 

- Khách hàng: Tìm kiếm sản phẩm, tạo giỏ hàng, áp dụng mã ưu đãi/Phiếu mua hàng, chọn phương thức vận chuyển/thanh toán, xác nhận đặt hàng và tiếp nhận kiện hàng<sup>3</sup> . 

- Giao diện Website/Ứng dụng Hasaki (Frontend): Hiển thị danh mục, kiểm tra điều kiện áp dụng dịch vụ 2H theo khu vực địa lý, tiếp nhận thông tin người dùng và khởi tạo giao diện thanh toán<sup>3</sup> . 

- Hệ thống OMS & ERP (Backend System): Tiếp nhận dữ liệu đơn hàng, tự động chạy thuật toán Anti-Fraud, kiểm tra tồn kho khả dụng thời gian thực, thực hiện khóa giữ tồn kho (Inventory Lock) và phân luồng đơn hàng về kho gần nhất<sup>1</sup> . 

- Cổng thanh toán trung gian (VNPAY / Ngân hàng): Xác thực tài khoản, thực hiện giao dịch 

   - tài chính cho các hình thức trả trước (VNPAY-QR, Ví VNPAY, Thẻ ATM/Visa/Mastercard)<sup>2</sup> . 

- Nhân viên Kho & Fulfillment (WMS): Nhận lệnh xuất kho trên hệ thống, thực hiện lấy hàng (Picking), kiểm tra chất lượng/hạn sử dụng (QC) và đóng gói niêm phong kiện hàng (Packing)<sup>1</sup> . 

- Bộ phận Điều phối & Vận chuyển (Dispatch & Shipper): Phân công đơn hàng cho Shipper nội bộ (đối với đơn NowFree 2H) hoặc bàn giao cho đơn vị vận chuyển đối tác (đối với đơn giao thường 48H/giao tỉnh)<sup>1</sup> . 

- Bộ phận Chăm sóc khách hàng (Hasaki Care / Hotline 1800 6324): Hỗ trợ khách hàng điều chỉnh thông tin, hủy đơn trước khi xuất kho hoặc xử lý các sự cố phát sinh trong quá trình vận chuyển<sup>7</sup> . 

### **2.3. Khách hàng của quy trình** 

Khách hàng của quy trình là tất cả người tiêu dùng thực hiện mua sắm hàng hóa trực tuyến qua Website Hasaki.vn hoặc ứng dụng di động Hasaki trên toàn quốc, bao gồm cả khách hàng nội thành thuộc phạm vi phục vụ NowFree 2H và khách hàng các tỉnh thành nhận hàng qua dịch vụ giao hàng nhanh<sup>1</sup> . 

### **2.4. Kết quả có thể xảy ra** 

Kết thúc quy trình Order-to-Delivery, hệ thống và bộ phận vận hành ghi nhận một trong các kết quả nghiệp vụ sau: 

- Đơn hàng được giao thành công cho khách hàng đúng cam kết thời gian (NowFree 2H hoặc 48H)<sup>1</sup> . 

- Đơn hàng giao thành công nhưng trễ so với mốc thời gian cam kết do sự cố khách quan (ùn tắc giao thông, thời tiết)<sup>1</sup> . 

- Đơn hàng bị chuyển đổi từ dịch vụ giao 2H sang giao hàng thông thường do địa chỉ không đáp ứng hoặc tồn kho kho gần nhất bị gián đoạn<sup>1</sup> . 

- Đơn hàng bị tự động hủy bởi hệ thống OMS do không hoàn tất thanh toán trực tuyến, vi phạm chính sách Anti-Fraud (mua đi bán lại), hoặc phát sinh lệch tồn kho thực tế<sup>1</sup> . 

- Đơn hàng bị hủy theo yêu cầu chủ động của khách hàng thông qua tổng đài hỗ trợ CSKH<sup>7</sup> . 

- Giao hàng thất bại do không liên hệ được khách hàng hoặc khách từ chối nhận hàng, đơn hàng được chuyển sang quy trình hoàn hàng về kho<sup>1</sup> . 

### **2.5. Mô tả quy trình bằng lời** 

Quy trình O2D khởi động khi khách hàng truy cập hệ thống Web/App Hasaki, tìm kiếm sản phẩm và tiến hành đặt hàng<sup>3</sup> . Tại màn hình thanh toán,  khách hàng nhập thông tin địa chỉ<sup>3</sup> . Hệ thống Frontend tự động định vị địa chỉ: nếu thuộc vùng phục vụ nội thành TP.HCM/Hà Nội, hệ thống cho phép chọn dịch vụ "Giao hàng nhanh NowFree 2H", ngược lại sẽ mặc định chọn "Vận chuyển giao hàng nhanh 48H"<sup>3</sup> . Khách hàng chọn phương  thức thanh toán COD hoặc Thanh toán trực tuyến qua VNPAY (bắt buộc thanh toán trực tuyến đối với đơn hàng trị giá trên 5.000.000 VNĐ) và bấm nút Đặt hàng<sup>2</sup> . 

Đối với đơn trả trước, giao diện chuyển hướng sang VNPAY để xác thực giao dịch<sup>2</sup> . Ngay khi 

thanh toán thành công (hoặc khi chọn COD), dữ liệu đơn hàng được đẩy sang hệ thống OMS<sup>1</sup> . 

Tại đây, OMS thực hiện kiểm tra tự động hai điều kiện: (1) Quét thuật toán Anti-Fraud kiểm tra hạn mức mua sắm để ngăn chặn hành vi thu gom mua đi bán lại, và (2) Kiểm tra tồn kho khả dụng thực tế tại chi nhánh/kho phụ trách địa bàn giao hàng<sup>1</sup> . Nếu không đạt, đơn hàng bị tự động hủy<sup>1</sup> . Nếu hợp lệ, OMS tiến hành khóa giữ tồn  kho tạm thời, gửi email/SMS xác nhận đơn 

cho khách hàng, đồng thời chuyển lệnh xuất kho sang ứng dụng WMS của bộ phận kho<sup>1</sup> . Tại kho, nhân viên kho tiếp nhận lệnh lấy hàng (Picking Ticket), di chuyển trong kho để lấy đúng sản phẩm, kiểm tra các tiêu chuẩn chất lượng như tem nhãn, bao bì, hạn sử dụng (QC), sau đó chuyển sang khu vực đóng gói (Packing)<sup>1</sup> . Sau khi niêm  phong kiện hàng và dán nhãn vận chuyển, dữ liệu đơn hàng được đẩy sang bộ phận điều phối<sup>1</sup> . 

Đối với đơn 2H NowFree, hệ thống tự động phân công Shipper nội bộ gần nhất<sup>1</sup> . Shipper quét mã đơn hàng, nhận hàng và tiến hành di chuyển đến địa chỉ khách hàng<sup>1</sup> . Đối với đơn giao thường, kiện hàng được bàn giao cho đối tác chuyển phát nhanh<sup>1</sup> . Shipper liên hệ khách hàng và thực hiện giao hàng<sup>1</sup> . Nếu khách hàng kiểm tra,  đồng ý nhận và thanh toán (nếu là đơn COD), Shipper cập nhật trạng thái "Giao hàng thành công" trên ứng dụng mobile, đơn hàng khép lại<sup>1</sup> . Trường hợp không thể liên hệ hoặc khách từ chối nhận, Shipper cập nhật lý do thất bại, chuyển kiện hàng về kho để xử lý quy trình hoàn trả<sup>1</sup> . 

## **Chương 3. Mô hình hóa quy trình BPMN** 

### **3.1. Phương pháp thu thập thông tin** 

Mô hình BPMN của quy trình Order-to-Delivery được xây dựng dựa trên sự hợp nhất giữa các quy định vận hành công khai của Hasaki và thông lệ BPM chuỗi cung ứng TMĐT: Bằng chứng thu thập: 

   - Quy trình checkout và chính sách đặt hàng trên Website Hasaki.vn<sup>3</sup> . 

   - Điều kiện áp dụng và phạm vi phục vụ dịch vụ giao hàng NowFree 2H<sup>4</sup> . 

   - Quy định thanh toán qua cổng VNPAY và chính sách hoàn tiền khi hủy đơn<sup>2</sup> . 

   - Quy định giao dịch chung, quy định chống mua đi bán lại và quy định hạn mức số lượng sản phẩm<sup>7</sup> . 

   - Quy trình xử lý đơn hàng tại kho và bàn giao cho đơn vị vận chuyển<sup>1</sup> . 

- Tài liệu tham khảo nghiệp vụ: 

   - Chính sách giao hàng, đóng gói và chính sách đổi trả sản phẩm 30 ngày của Hasaki<sup>2</sup> . 

   - . 

   - Chuẩn mô hình hóa quy trình nghiệp vụ BPMN 2.0 dành cho e-Fulfillment và Logistics<sup>1</sup> 

- Giả định mô hình hóa: 

   - Các bước nghiệp vụ nội bộ kho (Picking, QC, Packing) và thuật toán phân công Shipper tự động được chuẩn hóa theo quy trình vận hành e-Logistics tiên tiến<sup>1</sup> . 

### **3.2. Đề xuất các Lane** 

Quy trình Order-to-Delivery được phân chia thành 5 Lane nghiệp vụ để đảm bảo tính minh bạch về vai trò: 

- Lane 1: Khách hàng (Customer) – Người khởi tạo đơn hàng, thực hiện thanh toán và nhận sản phẩm<sup>1</sup> . 

- Lane 2: Giao diện Web/App Hasaki (Frontend System) – Tiếp nhận tương tác, kiểm tra khu 

vực giao 2H và cung cấp giao diện thanh toán<sup>3</sup> . 

- Lane 3: Hệ thống OMS & Cổng Thanh toán (Backend & Payment) – Xác thực tài 

   - khoản/thanh toán, quét rủi ro gian lận, khóa giữ tồn kho và xác nhận đơn<sup>1</sup> . 

- Lane 4: Bộ phận Kho & Fulfillment (Warehouse) – Thực hiện lấy hàng, kiểm tra chất lượng QC và đóng gói niêm phong kiện hàng<sup>1</sup> . 

- Lane 5: Bộ phận Điều phối & Shipper (Dispatch & Delivery) – Phân công Shipper/Đối tác vận chuyển, thực hiện chặng giao hàng cuối và xác nhận kết quả<sup>1</sup> . 

### **3.3. Gợi ý các Activity** 

Nhằm đảm bảo sơ đồ BPMN trực quan và thể hiện trọn vẹn chuỗi O2D, quy trình bao gồm 13 Activity cốt lõi: 

1. Đặt hàng và nhập thông tin địa chỉ trên Web/App<sup>3</sup> . 

2. Lựa chọn phương thức vận chuyển (NowFree 2H hoặc Giao thường) và Thanh toán<sup>3</sup> . 

3. Xác thực giao dịch tài chính qua cổng VNPAY (đối với đơn trả trước)<sup>2</sup> . 

4. Quét kiểm tra thuật toán Anti-Fraud và hạn mức mua sắm<sup>7</sup> . 

5. Kiểm tra tồn kho khả dụng và thực hiện khóa giữ hàng tạm thời<sup>1</sup> . 

6. Tự động xác nhận đơn hàng và gửi thông báo SMS/Email<sup>3</sup> . 

7. Tiếp nhận lệnh xuất kho và thực hiện lấy hàng (Picking)<sup>1</sup> . 

8. Kiểm tra chất lượng sản phẩm, hạn sử dụng và tem niêm phong (QC)<sup>1</sup> . 

9. Đóng gói sản phẩm và dán nhãn vận chuyển (Packing)<sup>1</sup> . 

10. Phân công Shipper nội bộ (đơn 2H) hoặc bàn giao Đơn vị vận chuyển (đơn thường)<sup>1</sup> . 

11. Vận chuyển hàng và liên hệ khách hàng tại địa điểm giao<sup>1</sup> . 

12. Cập nhật trạng thái giao hàng thành công trên hệ thống<sup>1</sup> . 

13. Thu hồi kiện hàng giao thất bại và thực hiện quy trình hoàn hàng về kho<sup>1</sup> . 

### **3.4. Gateway đề xuất** 

- Mô hình quy trình O2D sử dụng 6 Gateway quyết định (Exclusive Gateways) chính: 

   - Gateway 1: Địa chỉ nhận hàng có đáp ứng điều kiện dịch vụ NowFree 2H không? (Nếu Có 

      - -> Hiển thị tùy chọn 2H; Nếu Không -> Chọn giao thường 48H)<sup>3</sup> . 

   - Gateway 2: Giao dịch thanh toán trực tuyến qua VNPAY có thành công không? (Nếu 

      - Thành công/COD -> Chuyển sang OMS; Nếu Thất bại -> Chờ thanh toán lại hoặc Hủy)<sup>2</sup> . 

   - Gateway 3: Đơn hàng có đạt điều kiện Anti-Fraud (không vượt hạn mức, không mua đi bán lại) không? (Nếu Hợp lệ -> Kiểm tra tồn kho; Nếu Vi phạm -> Tự động hủy đơn)<sup>7</sup> . 

   - Gateway 4: Tồn kho thực tế tại chi nhánh/kho phụ trách có đủ không? (Nếu Đủ -> Khóa giữ hàng và Xác nhận; Nếu Khuyết thiếu -> Hủy đơn và hoàn tiền)<sup>1</sup> . 

   - Gateway 5: Sản phẩm sau khi lấy hàng có đạt tiêu chuẩn chất lượng QC không? (Nếu Đạt -> Đóng gói; Nếu Lỗi -> Thực hiện lấy đổi sản phẩm khác)<sup>1</sup> . 

   - Gateway 6: Khách hàng có đồng ý nhận hàng và thanh toán không? (Nếu Đồng ý -> Xác nhận giao thành công; Nếu Từ chối/Không liên hệ được -> Chuyển hoàn kho)<sup>1</sup> . 

### **3.5. Bộ câu hỏi phỏng vấn** 

Bộ câu hỏi thu thập dữ liệu phục vụ phân tích và tối ưu quy trình O2D được chia thành 4 nhóm nghiệp vụ: 

Câu hỏi định tính có cấu trúc: 

   1. Thời gian tối đa cho phép kể từ khi đơn hàng được xác nhận trên OMS đến khi kho hoàn tất đóng gói cho đơn 2H là bao nhiêu phút<sup>1</sup> ? 

   2. Tiêu chí tự động phân công Shipper cho đơn NowFree 2H dựa trên bán kính khoảng cách hay tải trọng đơn hàng thực tế<sup>1</sup> ? 

   3. Quy trình xử lý hoàn tiền trả trước cho khách hàng được kích hoạt tự động hay thủ công khi đơn O2D bị hủy tại bước kho<sup>2</sup> ? 

   4. Khi phát hiện sản phẩm bị lỗi QC tại bước đóng gói mà kho hết hàng thay thế, hệ thống xử lý điều chuyển kho hay hủy đơn<sup>1</sup> ? 

   5. Đơn hàng giao thất bại bao nhiêu lần thì Shipper được phép tạo lệnh chuyển hoàn về kho<sup>1</sup> ? 

- Câu hỏi định tính không cấu trúc: 

   1. Những điểm nghẽn lớn nhất gây rủi ro trễ cam kết SLA giao hàng 2 giờ trong các đợt cao điểm khuyến mãi là gì<sup>1</sup> ? 

   2. Áp lực của nhân viên đóng gói khi phải vừa đảm bảo tốc độ xuất hàng vừa tuân thủ quy cách đóng gói chống va đập mỹ phẩm là gì<sup>1</sup> ? 

   3. Tình trạng lệch dữ liệu tồn kho giữa ứng dụng WMS tại cửa hàng và hệ thống OMS bán hàng online phát sinh từ những lý do chính nào<sup>1</sup> ? 

   4. Phản ứng của khách hàng như thế nào khi đơn giao 2H bị chuyển sang giao thường do thời tiết hoặc quá tải vận chuyển<sup>1</sup> ? 

   5. Việc phối hợp giữa bộ phận CSKH và bộ phận Điều phối giao hàng khi khách hàng muốn đổi địa chỉ giao ngay lúc Shipper đang đi giao diễn ra ra sao<sup>1</sup> ? 

- Câu hỏi định lượng có cấu trúc: 

   1. Tỷ lệ đơn hàng NowFree 2H hoàn tất toàn bộ chuỗi O2D đúng cam kết thời gian đạt bao nhiêu %<sup>1</sup> ? 

   2. Thời gian trung bình để hoàn thành công đoạn Lấy hàng - QC - Đóng gói cho một đơn hàng online là bao nhiêu phút<sup>1</sup> ? 

   3. Tỷ lệ đơn hàng giao thất bại phải chuyển hoàn về kho (RTO) chiếm bao nhiêu % tổng đơn hàng O2D<sup>1</sup> ? 

   4. Bao nhiêu % đơn hàng bị hủy ở chặng xử lý kho do lỗi sai lệch tồn kho hệ thống<sup>1</sup> ? 

   5. Chi phí vận chuyển bình quân trên một đơn hàng thành công của dịch vụ NowFree 2H là bao nhiêu<sup>1</sup> ? 

- Câu hỏi định lượng không cấu trúc: 

   1. Mức độ biến động của thời gian chặng giao hàng cuối (Last-mile delivery) trong các khung giờ cao điểm ùn tắc giao thông là bao nhiêu phút<sup>1</sup> ? 

   2. Tỷ lệ kiện hàng bị hư hỏng, vỡ hỏng trong quá trình vận chuyển của Shipper nội bộ so với đối tác giao hàng thứ ba là bao nhiêu %<sup>1</sup> ? 

   3. Chi phí xử lý và vận hành một đơn hàng chuyển hoàn (Return Handling Cost) mất trung bình bao nhiêu VNĐ<sup>1</sup> ? 

   4. Tỷ lệ khách hàng đánh giá 5 sao cho trải nghiệm nhận hàng NowFree 2H trên ứng dụng là bao nhiêu %<sup>1</sup> ? 

5. Bán kính giao hàng tối ưu giúp Shipper đảm bảo chỉ số đúng giờ đạt trên 98% là bao nhiêu km<sup>1</sup> ? 

## **Chương 4. Phân tích quy trình** 

### **4.1. Phân tích giá trị gia tăng** 

Phương pháp phân tích giá trị gia tăng (VA/BVA/NVA) giúp bóc tách từng mắt xích trong toàn bộ quy trình O2D để xác định mức độ đóng góp hiệu quả: 

|**Hoạt động trong quy trình**<br>**O2D**|**Phân loại**|**Giải thích nghiệp vụ**|
|---|---|---|
|Tạo đơn hàng và chọn sản<br>phẩm|VA|Khách hàng chủ động thiết<br>lập nhu cầu mua sắm sản<br>phẩm<sup>3</sup>.|
|Áp dụng ưu đãi / Mã giảm<br>giá|VA|Tạo giá trị tài chính trực<br>tiếp, tăng mức độ hài lòng<br>của khách hàng<sup>3</sup>.|
|Quét kiểm tra Anti-Fraud<br>trên OMS|BVA|Hoạt động kiểm soát rủi ro,<br>bảo vệ hệ sinh thái giá và<br>ngân sách khuyến mãi<sup>7</sup>.|
|Kiểm tra và khóa giữ tồn<br>kho tự động|BVA|Đảm bảo tính chính xác của<br>dữ liệu chuỗi cung ứng,<br>tránh bán vượt tồn kho<sup>1</sup>.|
|Lấy hàng tại kho (Picking)|VA|Hoạt động vật lý trực tiếp<br>chuẩn bị hàng hóa cho<br>khách<sup>1</sup>.|
|Kiểm tra chất lượng & tem<br>nhãn (QC)|BVA|Hoạt động đảm bảo chất<br>lượng, hạn chế rủi ro hàng<br>lỗi hoặc hết hạn đến tay<br>khách<sup>1</sup>.|
|Đóng gói kiện hàng<br>(Packing)|VA|Bảo vệ hàng hóa chống hư<br>hỏng trong quá trình vận<br>chuyển và tăng tính chuyên<br>nghiệp<sup>1</sup>.|



|Phân công Shipper / Điều<br>phối|BVA|Tối ưu hóa nguồn lực vận<br>chuyển để đáp ứng cam kết<br>SLA<sup>1</sup>.|
|---|---|---|
|Vận chuyển & Giao hàng<br>tận tay|VA|Hoạt động tạo giá trị cốt lõi,<br>đưa sản phẩm tới người<br>nhận<sup>1</sup>.|
|Chờ Shipper nhận hàng tại<br>kho|NVA|Thời gian lãng phí nằm chờ,<br>không mang lại giá trị cho<br>người dùng<sup>1</sup>.|
|Chuyển hoàn hàng về kho<br>khi giao thất bại|NVA|Tổn thất chi phí và thời gian<br>do giao giao dịch không<br>thành công<sup>1</sup>.|



Phân tích sâu cho thấy, quy trình O2D của Hasaki được thiết kế rất tối ưu khi tập trung nguồn lực vào các hoạt động VA như Đóng gói chất lượng cao và Giao hàng siêu tốc NowFree 2H<sup>1</sup> . Tuy nhiên, các giai đoạn đệm như "Chờ Shipper nhận hàng tại kho" thuộc nhóm NVA là điểm nghẽn có thể loại bỏ bằng công nghệ điều phối thời gian thực<sup>1</sup> . 

### **4.2. Phân tích lãng phí** 

Áp dụng các nguyên tắc Lean Logistics giúp phát hiện các dạng lãng phí vận hành trong chuỗi O2D: 

|**Loại lãng phí Lean**|**Biểu hiện thực tế trong**<br>**quy trình O2D**|**Hướng cải tiến nghiệp vụ**<br>**đề xuất**|
|---|---|---|
|Move (Di chuyển)|Nhân viên kho phải di<br>chuyển quãng đường dài<br>qua nhiều kệ hàng để lấy lẻ<br>từng đơn<sup>1</sup>.|Ứng dụng phương pháp lấy<br>hàng theo lô (Batch Picking)<br>và tối ưu sơ đồ kho<sup>1</sup>.|
|Hold (Thời gian chờ)|Đơn hàng đã đóng gói xong<br>phải nằm chờ Shipper đến<br>lấy hoặc chờ phân công<sup>1</sup>.|Thuật toán phân công<br>Shipper trước khi kho hoàn<br>tất đóng gói (Dynamic<br>Dispatch)<sup>1</sup>.|
|Overdo (Thao tác thừa)|Kiểm tra thông tin đơn hàng<br>2 lần độc lập tại khâu Pick<br>hàng và khâu Pack hàng<sup>1</sup>.|Tích hợp máy quét mã vạch<br>Barcode/QR cầm tay để tự<br>động hóa khâu QC<sup>1</sup>.|



|Defect (Lỗi sản phẩm)|Lấy nhầm tông màu mỹ|Áp dụng quét mã vạch sản|
|---|---|---|
||phẩm hoặc giao sai sản|phẩm bắt buộc trước khi|
||phẩm do nhãn hàng tương|cho phép cho vào thùng|
||tự nhau<sup>1</sup>.|đóng gói<sup>1</sup>.|



Lãng phí về di chuyển (Move) và chờ đợi (Hold) tại kho đóng góp tới hơn 40% tổng thời gian xử lý nội bộ của quy trình O2D<sup>1</sup> . Loại bỏ các lãng phí  này là chìa khóa để đảm bảo cam kết NowFree 2H luôn đạt tỷ lệ cao<sup>1</sup> . 

### **4.3. Phân tích nguyên nhân theo Fishbone** 

Các sự cố dẫn đến trễ hẹn SLA giao hàng hoặc hủy đơn O2D được phân tích qua 5 nhóm nguyên nhân gốc rễ: 

Về phương diện Con người (Personnel & Operations): Nhân viên kho mới chưa thuộc sơ đồ vị trí sản phẩm dẫn đến thời gian tìm hàng kéo dài<sup>1</sup> . Shipper  nội bộ chưa tối ưu được lộ trình di 

chuyển khi phải giao nhiều đơn cùng lúc<sup>1</sup> . Ngoài ra,  thái độ phục vụ hoặc việc Shipper thiếu kiên 

nhẫn chờ đợi khách hàng cũng khiến tỷ lệ giao thất bại gia tăng<sup>1</sup> . 

Về phương diện Quy trình (Process & Rules): Quy trình kiểm tra QC qua nhiều bước thủ công làm chậm tốc độ xuất kho<sup>1</sup> . Việc thiếu quy trình cho  phép khách hàng tự điều chỉnh địa chỉ hoặc hẹn lại giờ giao trực tiếp trên app buộc mọi thao tác phải thông qua trung gian CSKH làm kéo dài thời gian xử lý<sup>7</sup> . 

Về phương diện Hệ thống & Công nghệ (System & Technology): Độ trễ đồng bộ tồn kho giữa cửa hàng bán lẻ và OMS trực tuyến dẫn đến hiện tượng "đơn ảo" (đã thanh toán nhưng kho hết hàng)<sup>1</sup> . Hệ thống phân công Shipper tự động đôi khi  định vị sai vị trí thời gian thực của Shipper dẫn đến việc phân đơn cho người ở quá xa kho<sup>1</sup> . 

Về phương diện Vận chuyển & Hạ tầng (Logistics & External): Tình trạng ùn tắc giao thông giờ cao điểm, thời tiết mưa lớn bão lũ gây ảnh hưởng trực tiếp đến thời gian di chuyển của Shipper<sup>1</sup> . Việc tìm địa chỉ nhà trong các hẻm phức tạp tại TP.HCM/Hà Nội tốn nhiều thời gian của lực lượng giao hàng<sup>1</sup> . 

Về phương diện Khách hàng (Customer Factors): Khách hàng không nghe máy khi Shipper gọi giao hàng<sup>1</sup> . Khách nhập sai thông tin số điện thoại  hoặc địa chỉ nhận<sup>3</sup> . Khách đổi ý không muốn mua hàng đột xuất tại thời điểm Shipper đã mang hàng đến nơi<sup>1</sup> . 

### **4.4. Phân tích định lượng** 

Phân tích định lượng mô hình hóa chuỗi thời gian, KPI chất lượng và chi phí vận hành cho một đơn hàng O2D chuẩn (tiêu chuẩn NowFree 2H): 

Thời gian xử lý chặng O2D NowFree 2H tiêu chuẩn: 

|**Hoạt động thành phần trong O2D**|**Thời gian xử lý tiêu chuẩn**|
|---|---|
|Khách hàng đặt hàng & Xác thực thanh toán<br>online|3 phút<sup>2</sup>|



|OMS kiểm tra Anti-Fraud, khóa tồn kho &<br>Chuyển WMS|2 phút<sup>1</sup>|
|---|---|
|Nhân viên kho lấy hàng theo đơn (Picking)|8 phút<sup>1</sup>|
|Kiểm tra QC chất lượng & Kiểm tra hạn sử<br>dụng|3 phút<sup>1</sup>|
|Đóng gói niêm phong & Dán nhãn giao hàng|5 phút<sup>1</sup>|
|Phân công Shipper & Shipper nhận hàng tại<br>kho|6 phút<sup>1</sup>|
|Shipper di chuyển chặng cuối & Giao hàng<br>tận tay|65 phút<sup>1</sup>|
|Cập nhật hệ thống & Khép lại đơn hàng<br>O2D|2 phút<sup>1</sup>|
|Tổng thời gian hoàn tất chuỗi O2D (SLA<br>cam kết <= 120 phút)|94 phút<sup>1</sup>|
|Chỉ số chất lượng vận hành O2D (KPIs):||



|**Chỉ số đo lường hiệu năng O2D**|**Giá trị mục tiêu / Giả định**|
|---|---|
|Tỷ lệ giao hàng đúng hạn cam kết SLA<br>(On-Time Delivery Rate)|96,5%<sup>1</sup>|
|Tỷ lệ hoàn tất đơn hàng O2D (Order<br>Fulfllment Rate)|98,2%<sup>1</sup>|
|Tỷ lệ giao hàng thất bại phải hoàn về kho<br>(RTO Rate)|1,8%<sup>1</sup>|
|Tỷ lệ hàng hóa bị hư hỏng / vỡ hỏng trong<br>vận chuyển|< 0,2%<sup>1</sup>|



Tỷ lệ giao sai / thiếu sản phẩm (Picking Error < 0,1%<sup>1</sup> Rate) 

Chi phí vận hành logistics trên một đơn hàng O2D (NowFree 2H): 

|**Khoản mục chi phí cấu thành chuỗi O2D**|**Chi phí ước tính (VNĐ / đơn hàng)**|
|---|---|
|Chi phí xử lý dữ liệu OMS & Hạ tầng công<br>nghệ|1.500|
|Chi phí nhân công kho (Pick, QC, Pack)|8.000<sup>1</sup>|
|Chi phí vật tư đóng gói (Thùng carton, băng<br>keo, chống sốc)|3.500<sup>1</sup>|
|Chi phí trả thưởng / Phí vận chuyển cho<br>Shipper|22.000<sup>1</sup>|
|Chi phí CSKH & Quản lý vận hành|2.000<sup>1</sup>|
|Tổng chi phí vận hành O2D trực tiếp|~ 37.000 VNĐ|



### **4.5. Kiến nghị cải tiến** 

Để tiếp tục duy trì vị thế dẫn đầu về tốc độ giao hàng và tối ưu chi phí chuỗi cung ứng O2D, Hasaki có thể tập trung triển khai 4 nhóm giải pháp chiến lược: 

Đồng bộ tồn kho đa kênh theo thời gian thực (Real-time Omnichannel Inventory Sync): Nâng cấp hạ tầng API kết nối giữa OMS và phần mềm quản lý tại toàn bộ hệ thống cửa hàng<sup>1</sup> . Việc này triệt tiêu hoàn toàn rủi ro hủy đơn do lỗi hết hàng ảo, giúp OMS tự động chuyển đơn về chi nhánh gần khách hàng nhất có sẵn hàng<sup>1</sup> . 

Tối ưu hóa công tác kho bằng phương pháp Batch Picking & Wave Picking: Áp dụng thuật toán gom nhiều đơn hàng có cùng khu vực kệ hàng để nhân viên kho lấy cùng một lúc, sau đó mới phân loại tại bàn đóng gói<sup>1</sup> . Giải pháp này giúp giảm  50% quãng đường di chuyển của nhân viên kho, rút ngắn thời gian chuẩn bị hàng từ 16 phút xuống còn dưới 8 phút<sup>1</sup> . 

Tích hợp thuật toán Định tuyến & Phân công Shipper thông minh (AI Dynamic Routing): Sử dụng trí tuệ nhân tạo để phân tích vị trí Shipper, mật độ giao thông và số lượng đơn hàng theo cụm địa chỉ<sup>1</sup> . Hệ thống sẽ tự động đề xuất lộ trình di  chuyển tối ưu nhất cho Shipper, nâng tỷ lệ giao đúng hẹn 2H lên trên 98,5%<sup>1</sup> . 

Cung cấp công cụ Tự quản lý đơn hàng cho Khách hàng (Customer Self-Service Portal): Cho phép khách hàng theo dõi vị trí Shipper theo thời gian thực (Live Tracking) trên ứng dụng 

Hasaki, đồng thời chủ động bấm nút "Hẹn lại giờ giao" hoặc "Thay đổi ghi chú giao hàng" trực 

tiếp cho Shipper mà không cần gọi qua hotline CSKH<sup>1</sup> . Điều này giúp giảm tỷ lệ giao thất bại (RTO) và tiết kiệm chi phí vận hành cho bộ phận CSKH<sup>1</sup> . 

#### **Works cited** 

1. converted-document (6).docx 

- - - 

- 2. Đổi trả - Hoàn tiền tại Hasaki, <u>htps://hotro.hasaki.vn/doi tra hoan tien.html</u> 

3. Hướng dẫn thanh toán trực tuyến VNPAY - Hasaki.vn, 

   - - - - - - 

   - <u>htps://hotro.hasaki.vn/huong dan thanh toan truc tuyen vnpay.html</u> 

4. Hướng dẫn đặt hàng 2H tại Hasaki, 

   - - - - 

   - <u>htps://hotro.hasaki.vn/huong dan dat hang 2h.html</u> 

- - - 

- 5. Hướng dẫn đặt hàng tại Hasaki, <u>htps://hotro.hasaki.vn/huong dan dat hang.html</u> 

- - 

- 6. Phiếu mua hàng tại Hasaki,  htps://hotro.hasaki.vn/phieu <u>mua hang.html</u> 

- - - 

- 7. Đặt hàng tại Hasaki,  htps://hotro.hasaki.vn/dat <u>hang tai hasaki.html</u> 

8. Xin chào! Chúng tôi có thể giúp gì cho bạn? - Hasaki.vn, 

   - - - - 

   - <u>htps://hotro.hasaki.vn/quy dinh giao dich chung.html</u> 

