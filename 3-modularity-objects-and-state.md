### 3. Tính mô đun, đối tượng và trạng thái

> Μὴ δύνασθαι ἐμβῆναι δὶς ἐς τὸν αὐτὸν ποταμόν.
> (Không thể bước vào cùng một dòng sông hai lần.)
>
> — Heraclitus

> Bản chất của các sự vật là cụm lại thành bó.
>
> — Plutarch

Chúng ta sẽ gọi một hệ thống **mô đun** nếu ta có thể xây dựng nó, sửa đổi nó và gỡ lỗi từng phần của nó riêng biệt, mà không cần hiểu toàn bộ hệ thống. Tính **mô đun** như vậy đòi hỏi những ranh giới tổ chức rõ ràng để phân tách các phần khác nhau của **chương trình**.

Một chiến lược mạnh để phân tổ **chương trình** lớn là xây dựng mô hình theo cấu trúc của hệ thống được mô phỏng. Với mỗi đối tượng trong hệ thống thực, ta tạo ra một _đối tượng tính toán_ tương ứng. Với mỗi hành động trong hệ thống thực, ta định nghĩa một phép tính trong **chương trình**. Hy vọng của ta là cấu trúc của **chương trình** sẽ đủ giống cấu trúc của hệ thống được mô phỏng, nên khi hệ thống thay đổi, **chương trình** cũng chỉ cần thay đổi cục bộ tương ứng.

Để mô phỏng theo kiểu này, ta muốn mỗi đối tượng tính toán có _trạng thái cục bộ_ riêng của mình — thứ có thể thay đổi theo diễn biến thời gian. Vì trạng thái của các đối tượng thay đổi, các **biến** trạng thái mô tả chúng cũng phải thay đổi. Đây là lúc ta cần một phép tính mới: **phép gán**, cho phép ta thay đổi giá trị của một **biến**.

Nhưng việc đưa **phép gán** vào ngôn ngữ kéo theo cái giá phải trả. Trước đây, ta đã mô tả việc tính toán bằng _mô hình sự thay thế_ đơn giản và thanh lịch. Sau khi đưa **phép gán** vào, mô hình đó không còn đủ nữa. Ta sẽ cần một mô hình tính toán phức tạp hơn để thay thế nó.

Ngoài ra, khi nhiều đối tượng có trạng thái cục bộ tương tác với nhau, các vấn đề về thứ tự thời gian và sự đồng bộ trở nên cực kỳ phức tạp. Ta sẽ xem xét những vấn đề này ở cuối chương, khi thảo luận về **tiến trình** đồng thời và xử lý song song.

---

[`process`](GLOSSARY.md#process) [`procedure`](GLOSSARY.md#procedure) [`program`](GLOSSARY.md#program) [`variable`](GLOSSARY.md#variable) [`state variables`](GLOSSARY.md#state-variables) [`module`](GLOSSARY.md#module) [`substitution model`](GLOSSARY.md#substitution-model)
