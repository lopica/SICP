---
name: sicp-translation
description: >-
  Translate sections, exercises, and exercise solutions of the book "Structure
  and Interpretation of Computer Programs" (SICP) from English into Vietnamese,
  matching the established style of this repository (meaning-based prose, a
  bold/italic/code term-styling system, translated footnotes, a per-section list
  of glossary term tags, and a shared master glossary). Use this skill WHENEVER
  the user asks to dịch / dịch
  lại / translate / re-translate any SICP material — a numbered section like
  1.2.3 or 1.1.7, an exercise like "bài tập 1.14" / "exercise 1.16", a solution,
  the preface, or a chapter intro — even if they only give a section number or a
  sarabander URL and don't say the word "translate". Also use it when adding new
  terms to the glossary or checking term consistency across translated files.
---

# Dịch SICP sang tiếng Việt

This skill reproduces the translation workflow of this repository: turning a
chunk of the English SICP text into a Vietnamese markdown file that reads
naturally, applies a consistent term-styling system, and ends with the book's
translated footnotes plus a list of glossary term tags — all anchored to a shared
master glossary so the same English term is always translated the same way.

## Triết lý dịch (đọc trước khi bắt đầu)

The single most important thing: **this is not a word-by-word translation.** The
reader is a self-learner who wants to _understand_ SICP, not to admire a faithful
mirror of the English. So translate **meaning**, in natural Vietnamese, the way
you'd explain the idea to a Vietnamese programmer — but never drop information.
Every fact, step, caveat, and example in the source must survive into the
Vietnamese. Restructure sentences freely; do not invent or omit content.

When a sentence is awkward to render literally, rewrite it so a Vietnamese reader
follows the _idea_ on the first pass. Keep the warm, slightly informal teaching
voice you see in the existing files (e.g. "chúng ta", "ta thấy rằng", "Ví dụ").

**Voice reference (gold standard):** đối chiếu
`1.1.1-expressions.md` và `1-build-abstractions-with-procedures.md`. Nếu
câu bạn vừa viết ra đọc không giống nhịp của hai file đó (quá Tây, quá sát, quá
trang trọng, hoặc thêm "in order to" / "as we have seen" kiểu word-for-word) thì
viết lại.

## Quy trình

### 1. Lấy bản gốc tiếng Anh

The English source is the sarabander HTML edition. URL scheme — each dot in a
number is encoded as `_002e`:

- A whole section lives in **one** file: section `1.2` → `https://sarabander.github.io/sicp/html/1_002e2.xhtml`.
- A subsection is an **anchor** in that file: `1.2.3` → add `#g_t1_002e2_002e3`.
- An exercise is an anchor too: Exercise `1.14` → `#Exercise-1_002e14` (in the
  chapter file `1_002e2.xhtml`).

So to translate 1.2.3, fetch `1_002e2.xhtml` with WebFetch and ask for the full
text of the **1.2.3** subsection (and any exercises that belong to it). If the
user pastes the English directly, skip this step.

Capture _all_ of it: prose, every code block, every numeric output, tables, and
the math. Tables and figures (evaluation trees, iteration tables, diagrams) are
**not** retyped — see step 4.

### 2. Dịch phần thân bài

Translate the prose following the philosophy above. As you write, apply the
term-styling system from the glossary (step 3) inline — don't translate first and
re-style later; it's one pass.

### 3. Áp dụng quy ước kiểu chữ qua bảng thuật ngữ

This is what separates a finished translation from a draft. Read the master
glossary at **`GLOSSARY.md`** in the repository root _before_ you translate, and
apply it:

- **`**đậm**`** — thuật ngữ CS chuẩn mà bạn sẽ gặp trong bất kỳ sách giáo khoa
  khoa học máy tính nào (e.g. **quy trình**, **tiến trình**, **môi trường**,
  **đệ quy**).
- **`_nghiêng_`** — thuật ngữ mà _chính SICP_ định nghĩa hoặc đóng khung lại
  trong chương này. Dấu hiệu trong bản gốc: chữ in nghiêng, hoặc đi kèm cụm
  "we call this…", "is called…", "the … is" (e.g. _biểu thức kết hợp_,
  _quy tắc_, _mô hình sự thay thế_).
- **`` `code` ``** — anything that is literally code: Lisp keywords, procedure and
  variable names, operators, and literal data. So `define`, `+`, `*`, `x`, `3`,
  `(+ x 1)`, `sqrt` all get backticks, **including** single symbols and numbers
  when they're referring to the code object rather than counting in prose.
- **Mặc định: không style.** Nếu bạn lưỡng lự một từ có đáng đậm/nghiêng hay
  không, **để chữ thường**. Thêm style sau dễ hơn gỡ bỏ; over-styling làm bài
  loang lổ và lệch các file khác.

Rules that keep it consistent:

- If the English term is **already in `GLOSSARY.md`, use that exact Vietnamese
  word and that exact style — no exceptions.** Consistency across chapters matters
  more than finding a marginally nicer wording for one occurrence.
- **Khi nào thêm vào `GLOSSARY.md`** — chỉ thêm khi thoả ít nhất một trong hai:
  (a) bản gốc in đậm/nghiêng từ đó, hoặc dùng cụm "we call X…" / "X is called…"
  / "the X is…" để định nghĩa nó, hoặc (b) từ đó sẽ tái xuất ở các mục/chương
  sau. Tên biến/hàm trong code, và những từ thoáng qua không được sách định
  nghĩa, **không** thêm. Khi thêm, giữ bảng sắp xếp alphabet theo cột English
  và báo cho user biết đã thêm những từ nào.
- **Mật độ style** — đánh dấu ở **lần xuất hiện đầu tiên trong section**, và
  **lần đầu trong mỗi tiểu mục lớn**. Các lần lặp tiếp theo trong cùng đoạn / cùng
  tiểu mục để chữ thường. Đừng bold mọi lần lặp; cũng đừng chỉ bold đúng một lần
  duy nhất ở đầu file rồi quên các tiểu mục sau.

### 4. Code, toán học, và hình ảnh

- **Code blocks**: fence Lisp with ` ```lisp `. Keep the code itself **unchanged**
  (it's a programming language, not prose). Leave a blank line before and after
  each fence. Interpreter output examples stay verbatim too.
- **Math**: use LaTeX in `$...$` for inline math, e.g. `$\sqrt{x}$`, `$y^2 = x$`.
- **Tables, evaluation trees, diagrams, iteration tables**: these are saved as
  images, **not** reconstructed in markdown. Reference them as
  `![Chú thích tiếng Việt](./figures/figureN.png)`. If the source has such a
  visual and there is no corresponding image yet, insert the reference with the
  next figure number and **tell the user they need to add `figures/figureN.png`**
  (a screenshot/crop from the source) — don't try to redraw it as ASCII or a
  markdown table.

### 5. Cuối file: footnote (chú thích chân trang) rồi danh sách thuật ngữ

A translated **section** ends with **two** blocks, in this exact order.

**a. Footnote — dịch các chú thích chân trang của sách.** SICP có rất nhiều
footnote, và chúng là một phần nội dung thực sự của sách (giải thích, lịch sử,
sắc thái) — **không được bỏ**. Đây là chỗ nhiều bản dịch cũ trong repo đang
thiếu; bản dịch mới thì luôn phải có đủ. Dùng cú pháp footnote của markdown: đặt
mốc `[^n]` ngay tại vị trí tương ứng trong thân bài, rồi sau một dấu `---` liệt kê
nội dung từng footnote đã dịch. Đánh số lại từ `1` trong mỗi file (bản gốc đánh số
liên tục cả chương).

```
...số bước cần dùng tăng theo $\Theta(\log n)$.[^1]

---

[^1]: Chính xác hơn, số phép nhân cần thực hiện bằng...
[^2]: Bạn có thể thắc mắc tại sao lại có người quan tâm...
```

Nếu bản gốc của phần này không có footnote nào thì bỏ qua khối (a).

**b. Danh sách thuật ngữ — chỉ là tag, không phải bản dịch.** Sau footnote, thêm
một dấu `---` nữa rồi liệt kê các thuật ngữ mà file này có dùng, dưới dạng **tag
tiếng Anh trong backtick**, cách nhau bằng dấu cách:

```
---

`order of growth` `parameter` `operation` `linear recursive process` `golden ratio`
```

Đây **không** phải phần dịch — nó chỉ đánh dấu file dùng những thuật ngữ nào. Bản
dịch tiếng Việt của từng thuật ngữ **chỉ** nằm ở `GLOSSARY.md`, nguồn sự thật duy
nhất; vì vậy footer **không** lặp lại bản dịch, **không** có `<br />`, **không** in
đậm/nghiêng. Mỗi tag là từ khóa tiếng Anh khớp đúng cột English của `GLOSSARY.md`.
Liệt kê theo thứ tự thuật ngữ xuất hiện lần đầu trong bài, và chỉ những thuật ngữ
thực sự có mặt trong file. (Việc in đậm/nghiêng vẫn áp dụng ở **thân bài** như mục
3 — chỉ riêng danh sách tag này là không.)

**Bài tập không có danh sách thuật ngữ (b)** — xem mục bên dưới. Nếu đề bài hay
lời giải của bài tập có footnote thì vẫn dịch và giữ chúng theo khối (a).

### 6. Lưu file

Match the repository's naming and location:

- **Sections**: repo root, `<số>-<slug-tiếng-anh>.md`, e.g.
  `1.2.3-orders-of-growth.md`. The slug stays in English (kebab-case) like the
  existing files. The `# ` heading is the section number + a Vietnamese title.
- **Exercises**: `exercises/1.N.md`, heading `# Bài tập 1.N`.

## Bài tập (exercises)

An exercise file has two parts separated by `---`:

1. **Đề bài**: the translated problem statement (same prose philosophy and term
   styling from step 3). Include any code given in the problem, in ` ```lisp `
   fences.
2. **Lời giải**: the solution. The book itself has no answers; the source for
   answers is **https://sicp-solutions.net/** (look up the matching exercise).
   Translate the _explanation_ into Vietnamese and include the Lisp solution code.
   Where the existing files show a worked evaluation trace (see `exercises/1.9.md`),
   reproduce that trace as a ` ```lisp ` block. Keep code unchanged; translate the
   reasoning around it. Verify the code's logic makes sense rather than copying
   blindly — note to the user if a found solution looks wrong.

   **Kỷ luật độ dài & nội dung lời giải:**
   - Lời giải dài tối đa khoảng **3× độ dài đề bài**. Nếu nguồn trên
     sicp-solutions.net lê thê, **tóm tắt phần lập luận** — giữ lại logic cốt
     lõi và code, bỏ các đoạn lan man.
   - **Không tự thêm** bài học mở rộng, so sánh ngoài lề, hay "thú vị là…" mà
     bản gốc không có.
   - Code Lisp phải đúng cú pháp SICP/MIT Scheme và logic phải khớp với những
     gì bạn vừa diễn giải; nếu nguồn có code sai, sửa và ghi chú cho user.

Exercises **do not** carry the English term-tag list from step 5(b). If the
problem or solution does reference book footnotes, translate them and place them
at the end as in step 5(a).

## Bảng thuật ngữ (maintenance)

`GLOSSARY.md` at the repo root is the **single source of truth**. Always read it
first; always write new terms back to it. If you ever notice the same English term
translated two different ways in older files, flag it to the user — the glossary
is how that drift gets fixed going forward.

## Anti-patterns (đã gặp trong repo, đừng lặp lại)

- **Dịch tên định danh trong code.** `square`, `good-enough?`, `sqrt-iter` —
  giữ nguyên tiếng Anh. Chỉ dịch _comment_ và _prose xung quanh code_.
- **Bỏ footnote.** Bản gốc có `[^n]` mà bản dịch không có → sai. Footnote là
  nội dung sách, không phải trang trí.
- **Tag list lặp lại bản dịch.** Footer `` `procedure` (quy trình) `` hay
  `` `procedure`<br />**quy trình** `` đều sai — chỉ để tag tiếng Anh trong
  backtick, không gì khác.
- **Vẽ lại bảng/cây đánh giá bằng ASCII hoặc markdown table.** Phải tham chiếu
  `./figures/figureN.png` và báo user thêm ảnh.
- **Style một từ chỗ này, để chữ thường chỗ khác trong cùng file** (mà không
  theo quy tắc "lần đầu mỗi tiểu mục"). Quyết định một lần, áp dụng nhất quán.
- **Thêm thuật ngữ vào `GLOSSARY.md` cho mọi từ kỹ thuật bắt gặp.** Bảng sẽ
  phình ra và mất ý nghĩa. Áp ngưỡng ở mục 3.
- **Lời giải bài tập tự "mở rộng kiến thức"** vượt khỏi điều bài tập hỏi.
- **Dịch slug filename sang tiếng Việt.** Slug giữ tiếng Anh kebab-case
  (`tree-recursion`, không phải `de-quy-cay`).

## Tự kiểm tra trước khi xong

- [ ] Mọi thông tin trong bản gốc đều có trong bản dịch (không thêm, không thiếu).
- [ ] Văn phong tự nhiên, dễ hiểu, giọng giảng giải — không dịch máy móc.
- [ ] Thuật ngữ khớp `GLOSSARY.md`, đúng kiểu đậm / nghiêng / code.
- [ ] Code trong ` ```lisp `, giữ nguyên; toán học trong `$...$`.
- [ ] Hình/bảng tham chiếu ảnh `./figures/`, không vẽ lại.
- [ ] Mọi footnote `[^n]` trong bản gốc đã được dịch và đặt ở cuối bài (đừng quên — nhiều bản dịch cũ hay thiếu phần này).
- [ ] Phần thân bài kết thúc bằng danh sách **tag thuật ngữ tiếng Anh trong backtick**, khớp đúng cột English của `GLOSSARY.md`; không lặp lại bản dịch, không `<br />`, không in đậm/nghiêng. Bài tập không có danh sách này.
- [ ] Thuật ngữ mới (nếu có) đã được thêm vào `GLOSSARY.md`.
