# Bản dịch Structure and Interpretation of Computer Programs

Đây là bản dịch tiếng việt cho quyển sách _Structure and Interpretation of Computer Programs_ lần tái bản thứ 2, phiên bản ngôn ngữ Lisp từ chương 1 đến chương 3. Đây là quyển sách đầu tiên được gợi ý học trong roadmap tự học khoa học máy tính tại: [teachyourselfcs](https://teachyourselfcs.com). Phần dịch có bao gồm cả bài tập và đáp án cho từng bài. Nguồn sách được lấy từ [sarabander](https://sarabander.github.io/sicp/html/index.xhtml).

Cuốn sách này mình tạm dịch là _Cấu trúc và cách thực thi của chương trình máy tính_, được 2 giảng viên trường MIT biên soạn và dạy trong môn học cùng tên. Hiện bản dịch vẫn đang trong giai đoạn phát triển.

## Một số lưu ý nếu bạn muốn đọc bản dịch này:

- Đây không phải là một bản dịch word-by-word, điều này có nghĩa là cách hành văn và câu từ sẽ không hoàn toàn sát nghĩa bản gốc, mà sẽ do chủ quan cách hiểu của người dịch, tuy nhiên về ý thì sẽ đầy đủ.
- Bản dịch sẽ có chú thích ở cuối các bản dịch các thuật ngữ tiếng anh mà được dịch lại tiếng việt trong bản đó theo cách hiểu dưới dạng:

  ```bash
      thuật ngữ tiếng việt: thuật ngữ tiếng anh gốc
      ...
  ```

- Ở nguồn sách gốc không bao gồm đáp án cho phần bài tập, nguồn dịch đáp án lấy từ: [sicp-solutions](https://sicp-solutions.net/).
- Bản dịch sẽ bao gồm các ghi chú của bản thân mình cho các chương của cuốn sách, được đặt tên là _MyNote-<tên chương>.md_. Nó là phần không thuộc về sách nên bạn có thể bỏ qua.

## Chú thích cách ghi chú

**thuật ngữ**: đây là các từ khóa quan trọng, cả ngành dùng.

_thuật ngữ_: đây là các từ khóa quan trọng, nhưng chỉ quyển sách này dùng

`tên`: đây là giá trị có trong code (tên biến, từ khóa của Lisp, hoặc dữ liệu)

## Cách chạy code Lisp

Để chạy code trong sách, bạn có thể làm qua 2 cách sau:

- Dùng trình phiên dịch ngôn ngữ Lisp dialect Schema bản web qua google (như mình hay xài [try.scheme.org](https://try.scheme.org/))

- Tải ide [DrRacket](https://racket-lang.org/download/) và cài package riêng cho quyển sách này là "SICP"

## Góp ý

Bạn có thể folk source về để chỉnh sửa cá nhân, hoặc nếu bạn muốn đóng góp ý kiến thì có thể tạo issue cho project này.
