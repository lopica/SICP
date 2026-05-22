### 1. Xây dựng các trừu tượng qua các quy trình

> Các hoạt động cuả tâm trí bao gồm:
>
> - Kết hợp các ý tưởng đơn giản thành một
> - Đặt chúng cạnh nhau để thấy quan hệ giữa chúng
> - Bỏ qua một số đặc tính của chúng
>   Đây là cách nhiều ý tưởng tổng quát được tạo ra
>
> --- John Locke - An Essay Concerning Human Understanding

Chúng ra sẽ học về **tiến trình** tính toán của máy tính. Các **tiến trình** tính toán là các thực thể vô hình trong máy tình của chúng ta. Khi chúng hoạt động, chúng kiểm soát các thứ trừu tượng khác gọi là dữ liệu. Sự thực thi của tiến trình được dẫn dắt bởi một khung các quy tắc mà ta gọi là **chương trình**. Người ta tạo chương trình để dẫn dắt tiến trình. Hay nói theo cách ví von, chúng ta triệu hồi linh hồn của máy tính qua phép thuật của chúng ta.

Một tiến trình tính toán giống như một pháp sư nghĩ về một linh hồn. Nó không thể thấy hoặc chạm vào. Nó không được tạo từ các vật chất hữu hình. Tuy nhiên, nó rất thật, nó có thể thực hiện các công việc thông minh, nó có thể trả lời các câu hỏi, Nó có thể tác động đến thế giới bằng cách giải ngân tiền ở một ngân hàng hoặc điều khiển một cánh tay robot trong một nhà máy. Các chương trình chúng ta dùng để triệu hồi tiến trình giống như các phép thuật của pháp sư. Chúng được tổng hợp cẩn thận từ các biểu thức ký hiệu bý ẩn và các ngôn ngữ lập trình bý truyền để miêu tả các nhiệm vụ chúng ta muốn các tiến trình thực thi.

Một tiến trình tính toán, trong một chiếc máy tính hoạt động bình thường, thực thi chương trình đúng và chính xác. Do đó, như các phù thủy tập sự các lập trình viên mới cần học để hiểu và đoán trước hậu quả của các phép triệu hồi của mình. Kể cả các lỗi nhỏ tron chương trình có gây ra các hậu quả phức tạp và không thể doán trước.

May mắn thay, học một chương trình thì có thể coi là ít nguy hiểm hơn học phép thuật, bởi vì các linh hồn mà chúng ta cần phải dùng đến được cất giữ một cách an toàn và thuận tiện. Tuy nhiên, lập trình trong thực tế yêu cần sự sát sao, sự thành thục và hiểu biết. Một lỗi nhỏ trong một chương trình thiết kê có sự hỗ trợ của máy tính (CAD) có thể tạo ra sự sụp đổ của một chiếc máy bay hoặc sự tự hủy của một con robot công nghiệp.

Các chuyên gia kỹ sư phần mềm có khả năng tổ chức phần mềm để họ có cơ sở tin tưởng rằng các tiến trình sẽ hoạt động như mong muốn. Họ có thể hình dung trước hành vi của hệ thống. Họ biết cách tổ chức hệ thống, sao cho các vấn đề không thể đoán trước sẽ không gây hậu quả lớn, và nếu vấn đề có xuất hiện, họ có thể debug chúng trong chương trình.Một hệ thống tính toán thiết kế tốt, giống như một ôtô thiết kế tốt hoặc một lò phản ứng hạt nhân, được thiết kế theo nguyên tắc mô đun, do đó các phần có thể dễ dàng thêm mới, thay thế hoặc gỡ lỗi độc lập.

## Lập trình với Lisp

Chúng ta cần một ngôn ngữ phù hợp để miêu tả các tiến trình, và chúng ta sẽ dùng Lisp cho mục đích đó. Giống như các suy nghĩ hằng ngày của chúng ta được thể hiện qua ngôn ngữ tự nhiên (như tiếng anh, tiếng pháp, tiếng nhật), các mô tả về các hiện tượng có thể định lượng thông qua các ký hiệu toán học, các suy nghĩ về quy trình của chúng ta sẽ được thể hiện qua Lisp. Lisp được phát minh vào cuối các năm 1950 như là một cách chuyên nghiệp giải thích việc sử dụng của các biểu thức logic khác, gọi là các phương trình đệ quy. Ngôn gữ được ấp ủ bởi John McCarthy và được dựa trên báo cáo của anh ấy "Recursive Functions of Symbolic Expressions and Their Computation by Machine".

Mặc dù có khởi đầu như là cách thể hiện toán học, Lisp là một ngôn ngữ lập trình thực thụ. Trình phiên dịch của Lisp là một cỗ máy mang các tiến trình của chúng ta được miêu tả trong ngôn ngữ Lisp. Trình phiên dịch Lisp đầu tiên được triển khai bởi John McCarthy với sự giúp đỡ của các đồng nghiệp và học sinh của nhóm trí tuệ nhân tạo tại phòng nghiên cứu và thí nghiệm về điện MIT và trung tâm tính toán MIT. Lisp, cái tên được viết tắt từ LISt Processing, được thiết kế để cung cấp khả năng điều khiển các ký tự để giải quyết các vấn đề của lập trình như là sự khác biệt ký hiệu và tích hợp các biểu thức đại số. Các đối tượng dữ liệu mới được thêm vào như atoms và lists, khiến nó khác biệt với các ngôn ngữ khác cùng thời.

Lisp không phải là sản phẩm của một sự thiết kế phối hợp, Thay vào đó, nó được phát triển không chính thức trong một thử nghiệm phản hồi của nhu cầu người dùng và sự cân nhắc triển khai thực tế. Sự phát triển không chính thức này tiếp tục qua các năm, và cộng đồng người dùng có truyền thống chống lại các nỗ lực để ban hành bất kỳ định nghĩa chính thức nào cho ngôn ngữ. Sự phát triển này, cùng với sự linh hoạt và đẹp đẽ của của ý tưởng ban đầu, đã cho phép Lisp, ngôn ngữ mà già thứ 2 thế giới chỉ sau Fortan, tiếp tục thích nghi để tích hợp các ý tưởng hiện đại nhất về thiết kế hệ thống. Do đó, Lisp hiện tại có rất nhiều phiên bản, cùng chia sẻ các chức năng gốc, và cũng khác nhau rất nhiều. Phiên bản được dùng trong quyển sách này là Scheme.

Bởi vì tính chất thử nghiệm và tính nhấn mạnh vào kiểm soát ký tự, Lisp ban đầu rất kém hiệu quả cho các tác vụ tính toán số, ít nhất là so với Fortran. Qua các năm, trình biên dịch Lisp được phát triển để dịch chương trình sang mã máy
khi cho việc tính toán trở nên hiệu quả, Và cho các úng dụng đặc biệt, Lisp đã được dùng với sự hiểu quả. Mặc dù Lisp chưa vượt qua được tiếng xấu xưa, Lisp hiện tại (ý là thời điểu viết sách này là nhưng năm 2005). Lisp hiện được dùng trong rất nhiều ứng dụng mà hiệu năng không phải là vấn đề chính. Ví dụ, Lisp đã trở thành ngôn ngữ được lựa chọn cho các ngôn ngữ shell của hệ điều hành và là ngôn ngữ mở rộng cho trình soạn thảo và hệ thống cad.

Nếu Lisp không phải là ngôn ngữ phổ biến, tại sao lại dùng nó như là khung cho các cuộc thảo luận của chúng ta về lập trình? Bởi vì ngôn ngữ này có các chức năng đặc biệt khiến nó trở thành phương tiện tuyệt với để học các cấu trúc lập trình và cấu trúc dữ liệu quan trọng, và liên hệ chúng với tính năng ngôn ngữ hỗ trợ chúng. Một trong các tính năng nổi bật của Lisp là khả năng miêu tả các tiến trình, gọi là các **quy trình**, chúng có thể được được biểu diễn hoặc được thay đổi như dữ liệu trong Lisp. Điều này quan trọng bởi có một kĩ thuật mạnh để thiết kế chương trình mà phụ thuộc và khả năng làm mở đi khoảng cách truyền thống giữa các dữ liệu bị động và các tiến trình chủ động. Và rồi chúng ta sẽ tìm hiểu, khả năng linh hoạt của Lisp trong việc xử lý các quy trình như dữ liệu khiến nó là một trong các ngôn ngữ lập trình thuận tiện nhất để khám phá các kĩ thuật này. Khả năng thể hiện các quy trình như dữ liệu cũng khiến Lisp trở thành ngôn ngữ tuyệt vời để viết các chương trình mà cần phải thay đổi các chương trình khác như dữ liệu, như là các trình phiên dịch và biên dịch hỗ trợ các ngôn ngữ máy tính. Và ngoài tất cả các điều trên, lập trình Lisp khá thú vị.

---

**tiến trình**: process <br />
**chương trình**: program <br />
**quy trình**: procedure <br />
