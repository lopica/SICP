### Lời mở đầu của lần xuất bản thứ 1

> Máy tính cũng như cây vĩ cầm. Bạn có thể tưởng tượng một người mới chơi nhạc cụ này, giữa máy nghe nhạc và vĩ cầm, > họ sẽ nói tiếng vĩ cầm nghe rất tệ. Chương trình máy tính cũng như cách chơi cây vĩ cầm vậy. Nó có âm hay đặc trưng > riêng, và nó không thể chơi được nhiều thứ, cho đến khi ta học cách dùng chúng.
>
> --- Marvin Minsky - Why Programming Is a Good Medium for Expressing
> Poorly-Understood and Sloppily-Formulated Ideas

_Cấu trúc và cách thực thi của chương trình máy tính_ là môn học mở đầu cho ngành khoa học máy tính tại đại học MIT. Nó cũng là môn học bắt buộc với ngành kĩ sư điện. Chúng ta vẫn đang được thấy môn học này phát triển kể từ năm 1978. Và chúng ta cũng đã thấy môn học này được dạy từ mùa thu 1980, với 600 - 700 học sinh tham gia mỗi năm. Phần lớn các học sinh này chưa từng được đào tạo bài bản về tính toán, mặc dù nhiều người trong số họ đã từng sử dụng máy tính, lập trình hay thậm chí thiết kế phần cứng.

Chúng tôi thiết kế môn học này nhằm giải quyết 2 vấn đề lớn. Thứ nhất, đó là tư duy sử dụng ngôn ngữ lập trình, thay vì là cách ra lệnh cho máy tính làm việc thì đó là một cách thức chuyên nghiệp mới để trình bày phương pháp luận. Do đó, chương trình máy tính nên được viết để cho người đọc, và việc dùng cho cả máy tính để thực thi chỉ là phụ. Thứ hai, đó là kĩ năng kiểm soát độ phức tạp của các hệ thống phần mềm lớn, khi mà hàm lượng kiến thức trong nó rất cao (nghiệp vụ)

Kỳ vọng của chúng tôi đối với học sinh học môn học này là:

- Nắm được các kĩ thuật kiểm soát độ phức tạp của hệ thống lớn
- Có khả năng biết cái gì không cần đọc, cái gì cần hiểu ngay lập tức
- Có khả năng sửa đổi chương trình, mà vẫn giữ kiểu viết của chương trình cũ

Những kỹ năng này không hề đặc thù cho ngành khoa học máy tính. Chúng đều được sử dụng trong các kiểu thiết kế kĩ thuật phổ biến khác. Chúng ta kiểm soát sự phức tạp bằng cách tạo ra các thứ trừu tượng để giấu đi phần chi tiết. Chúng ta kiểm soát sự phức tạp bằng cách tạo các giao diện theo quy ước để kết hợp các tiêu chuẩn. Chúng ta kiểm soát sự phức tạp bằng cách tạo ra ngôn ngữ mới nhằm miêu tả thiết kế đó, nhấn mạnh cái quan trọng và làm mờ những cái khác.

Chúng tôi tin rằng khoa học máy tính không không phải là về máy tính hay khoa học, mà là về chúng ta nghĩ và cách chúng ta trình bày chúng. Cuộc cách mạng máy tính là cuộc cách mạng về cách chúng ta nghĩ và cách chúng ta trình bày chúng. Điều này được thể hiện thông qua lĩnh vực nghiên cứu mới là **nhận thức quy trình luận**. Nếu như toán nghiên cứu kiến thức để trả lời câu hỏi "là gì?", tính toán máy tính lại trả lời câu hỏi "bằng cách nào?"

Để dạy quyển sách này, chúng tôi sẽ dùng 1 **phiên bản** của ngôn ngữ lập trình Lisp. Chúng tôi chưa bao giờ chính thức dạy lập trình, bởi vì chúng tôi không cần phải làm vậy. Chúng tôi chỉ đơn giản là cứ dùng nó, và các học sinh sẽ bắt kịp trong vài ngày. Đây là một trong các lợi ích lớn của các ngôn ngữ lập trình giống Lisp: chúng có rất ít cách để tạo các biểu thức tổng hợp, và gần như không có cấu trúc cú pháp. Tất cả các chức năng chính có thể nắm được trong 1 tiếng, như các luật trong cờ vua vậy. Sau một khoảng thời gian ngắn, chúng ta sẽ quên đi các chi tiết cú pháp của ngôn ngữ (bởi chúng không có gì cả) để nắm bắt các vấn đề chính - tìm hiểu tại sao chúng ta cần tính toán, làm sao chúng ta chia nhỏ các vấn đề thành các phần nhỏ hơn có thể quản lý, và làm sao để chúng ta làm việc với các phần đó. Một lợi thế nữa của Lisp mà nó hỗ trợ rất nhiền chiến lược mở rộng cho việc phân tách **mô đun** của các chương trình hơn bất kỳ ngôn ngữ nào chúng ta biết. Chúng ta có thể tạo các sự trừu tượng cho quy trình và dữ liệu, chúng ta có thể dùng các hàm bậc cao để thể hiện các cách dùng phổ biến, chúng ta có thể mô hình hóa biến cục bộ dùng phép gán và đổi dữ liệu, chúng ta có thể kết nối các phần của chương trình với các **dòng chảy** và trì hoãn thực thi, và chúng ta có thể dễ dàng phát triển các ngôn ngữ nhúng. Tất cả đã được nhúng trong một môi trường tương tác với sự hỗ trợ tuyệt vời cho việc phát triển dần các thiết kế chương trình, xây dựng chương trình, kiểm thử và gỡ lỗi. Chúng tôi muốn cảm ơn cả thể hệ các phù thủy Lisp, bắt đầu với John McCarthy, người đã thiết kế một công cụ tuyệt vời và có sức mạnh tuyệt vời và vẻ đẹp chưa từng có.

Scheme, phiên bản Lisp mà chúng ta sử dụng, là một nỗ lực để kết hợp sức mạnh và vẻ đẹp của Lisp với Algol. Từ Lisp chúng ta có sức mạnh siêu ngôn ngữ từ cú pháp đơn giản, cách biểu diễn chung của chương trình như là các đối tượng dữ liệu, các dữ liệu rác được thu dọn và các dữ liệu được cấp pháp trên heap. Từ Algog chúng ta có **phạm vi ngữ cảnh** và **cấu trúc khối**, đó là những món quà từ các nhà thiết kế ngôn ngữ lập trình tiên phong trong ủy ban Algol. Chúng tôi muốn được trích dẫn John Reynolds và Peter Landin về góc nhìn của họ về mối quan hệ của phép tính lamda đến cấu trúc của ngôn ngữ lập trình. Chúng ta cũng nhận ra chúng ta đã nợ các nhà toán học đã khai phá phần kiến thức này nhiều thập kỷ trước khi các máy tính ra đời. Các người tiên phong này bao gồm Alonzo Church, Barkley Rosser, Stephen Kleene, và Haskell Curry.

---

_Cấu trúc và cách thực thi của chương trình máy tính_: Structure and Interpretation of Computer Programs <br />
**nhận thức quy trình luận**: procedural epistemology <br />
**phiên bản**: dialect <br />
**mô đun**: module <br />
**dòng chảy**: stream <br />
**phạm vi ngữ cảnh**: lexical scoping <br />
**cấu trúc khối**: block structure <br />
