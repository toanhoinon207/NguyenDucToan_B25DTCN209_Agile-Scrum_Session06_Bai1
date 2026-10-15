# 1. Acceptance Criteria

| Story | AC# | Loại | Given | When | Then |
|:---:|---|---|---|---|---|
| 1 | **AC1.1** | Happy | Độc giả đủ điều kiện mượn và sách đang có sẵn. | Độc giả chọn đặt mượn sách online. | Hệ thống xác nhận đặt mượn thành công và giữ sách trong 48 giờ. |
| 1 | **AC1.2** | Negative | Độc giả xem một cuốn sách không còn bản có sẵn. | Độc giả chọn đặt mượn sách đó. | Hệ thống từ chối yêu cầu và thông báo sách hiện không có sẵn. |
| 1 | **AC1.3** | Edge | Độc giả đủ điều kiện và cuốn sách chỉ còn đúng 1 bản có sẵn. | Độc giả đặt mượn cuốn sách đó thành công. | Hệ thống xác nhận đặt mượn và chuyển trạng thái sách thành không còn bản có sẵn để đặt mượn. |
| 1 | **AC1.4** | Ràng buộc nghiệp vụ | Độc giả đã mượn đủ 5 cuốn sách. | Độc giả đặt mượn thêm một cuốn sách. | Hệ thống từ chối yêu cầu và thông báo đã đạt giới hạn mượn sách. |
| 2 | **AC2.1** | Happy | Độc giả đã đặt trước một cuốn sách và cuốn sách vừa có sẵn để nhận. | Hệ thống ghi nhận sách đã có sẵn. | Độc giả nhận được thông báo sách đã có sẵn và thời hạn nhận sách là 48 giờ. |
| 2 | **AC2.2** | Negative | Độc giả đã đặt trước một cuốn sách nhưng sách vẫn chưa có sẵn. | Độc giả kiểm tra trạng thái đặt trước. | Hệ thống hiển thị sách chưa có sẵn và không gửi thông báo sách đã sẵn sàng nhận. |
| 2 | **AC2.3** | Edge | Độc giả nhận thông báo sách đã có sẵn và thời hạn giữ sách còn đúng 48 giờ kể từ thời điểm thông báo. | Độc giả xem thông báo. | Thông báo hiển thị rõ thời hạn nhận sách là 48 giờ kể từ thời điểm sách được xác nhận có sẵn. |
| 2 | **AC2.4** | Ràng buộc nghiệp vụ | Độc giả đã nhận thông báo sách có sẵn nhưng thời hạn giữ sách 48 giờ đã kết thúc. | Độc giả kiểm tra trạng thái đặt trước. | Hệ thống thông báo thời hạn giữ sách đã hết và không hiển thị yêu cầu đó là còn trong thời gian giữ chỗ. |
| 3 | **AC3.1** | Happy | Độc giả đang mượn 3 cuốn sách và chưa có vi phạm điều kiện mượn. | Độc giả mượn thêm 1 cuốn sách đang có sẵn. | Hệ thống chấp nhận yêu cầu và tổng số sách đang mượn là 4 cuốn. |
| 3 | **AC3.2** | Negative | Độc giả đang mượn đủ 5 cuốn sách. | Độc giả yêu cầu mượn thêm 1 cuốn. | Hệ thống từ chối yêu cầu và thông báo đã đạt giới hạn 5 cuốn. |
| 3 | **AC3.3** | Edge | Độc giả đang mượn 4 cuốn sách. | Độc giả yêu cầu mượn thêm 1 cuốn. | Hệ thống chấp nhận yêu cầu và tổng số sách đang mượn không vượt quá 5 cuốn. |
| 3 | **AC3.4** | Ràng buộc nghiệp vụ | Độc giả đang mượn 5 cuốn sách, trong đó có 1 cuốn đã được trả và việc trả sách đã được xác nhận. | Độc giả yêu cầu mượn thêm 1 cuốn. | Hệ thống chấp nhận yêu cầu nếu các điều kiện mượn khác đều được đáp ứng, vì độc giả hiện chỉ còn mượn 4 cuốn. |

# 2. Câu hỏi làm rõ

## Story 1
- Khi độc giả đặt thành công, thời gian giữ sách 48 giờ bắt đầu ngay lúc đặt hay khi sách được xác nhận có sẵn?
- Nếu nhiều độc giả đặt cùng lúc và chỉ còn một bản sách, hệ thống ưu tiên người đặt trước theo thời điểm nào?

## Story 2

- Thông báo được gửi qua email, SMS hay thông báo trên hệ thống?
- Khi nào bắt đầu tính 48 giờ giữ sách: từ lúc sách có sẵn hay từ lúc độc giả nhận được thông báo?

## Story 3

- Giới hạn chính thức là 5 cuốn mỗi độc giả hay một con số khác?
- Sách đã đặt mượn online nhưng chưa đến quầy nhận có được tính vào giới hạn 5 cuốn không?

# 3. Definition of Done (DoD)

- Code đã được review bởi ít nhất một thành viên khác trong nhóm.
- Các bài kiểm thử liên quan đã được thực hiện và đạt yêu cầu.
- Không còn lỗi nghiêm trọng hoặc lỗi mức cao chưa được xử lý.
- Chức năng đã được tích hợp thành công vào phiên bản chung của sản phẩm.
- Tài liệu liên quan đã được cập nhật đầy đủ.
- Chức năng được kiểm thử trên môi trường kiểm thử phù hợp.

### Story 1 chưa Done vì code vẫn chưa được review theo DOD chung của nhóm. Story chỉ được coi là Done khi đáp ứng cả AC riêng của story và toàn bộ tiêu chí DoD áp dụng chung.