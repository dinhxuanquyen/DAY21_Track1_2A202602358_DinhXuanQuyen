# Lab 21 — Phân tích rủi ro AI qua case study thực tế

- Họ và tên: Đinh Xuân Quyền
- MSSV / mã học viên: 2A202602358
- Lớp: Track 1
- Ngành đã chọn: Y tế (Kiểm tra triệu chứng, trợ lý sức khỏe)

### 1. Industry Risk Snapshot

| Nội dung                                       | Đánh giá của tôi và lý do                                                                                                                                                                                                                                                     |
| ----------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Những tác hại chính có thể xảy ra        | AI đưa lời khuyên y khoa sai lệch hoặc độc hại kích hoạt hành vi tự hại; AI chẩn đoán sai, không nhận diện được ca cấp cứu khiến bệnh nhân bỏ lỡ thời gian vàng điều trị, đe dọa tính mạng.                                                   |
| Mức độ high-stakes                           | **Cao.** Các tư vấn từ AI liên quan trực tiếp đến tâm lý và sinh mạng con người. Người bệnh thường ở trạng thái dễ tổn thương, nếu AI đưa ra định hướng sai lầm sẽ dẫn đến hậu quả tử vong hoặc nguy kịch không thể vãn hồi.   |
| Dữ liệu nhạy cảm có thể được sử dụng | Thông tin khai báo triệu chứng bệnh lý, dữ liệu khám chữa bệnh, tình trạng sức khỏe tâm thần, và lịch sử trò chuyện chứa các suy nghĩ,ý định cá nhân nhạy cảm (ví dụ: ý định tự tử).                                                          |
| Nhu cầu human review                           | **Cao.** Các ứng dụng AI sức khỏe/tâm lý chỉ nên đóng vai trò cung cấp thông tin tham khảo ban đầu. Mọi chẩn đoán, lời khuyên y tế hay can thiệp tâm lý khẩn cấp đều phải có sự giám sát và quyết định từ bác sĩ hoặc chuyên gia. |

### 2. Case study 1 — Chatbot Tessa đưa ra lời khuyên độc hại cho người rối loạn ăn uống

#### Brief Case

- Tổ chức / sản phẩm AI: Hiệp hội Rối loạn Ăn uống quốc gia Mỹ (NEDA) / Chatbot Tessa.
- Thời gian, địa điểm / bối cảnh: Đầu tháng 6/2023, tại Mỹ. NEDA quyết định đóng cửa đường dây trợ giúp do người thật (tư vấn viên) đảm nhận và thay thế bằng chatbot AI Tessa.
- AI được dùng để làm gì: Cung cấp hỗ trợ và nguồn lực cho những người đang lo lắng hoặc mắc chứng rối loạn ăn uống.
- Vấn đề hoặc sự kiện đáng chú ý: Chỉ vài ngày sau khi thay thế đường dây nóng, chatbot Tessa bị phát hiện đưa ra các lời khuyên có hại, cụ thể là khuyên "giảm cân" cho những bệnh nhân vốn đang vật lộn với chứng rối loạn ăn uống.
- Số liệu có nguồn: Theo nghiên cứu của tổ chức Mozilla Foundation được trích dẫn trong bài, trong số 32 ứng dụng chăm sóc sức khỏe tâm lý được khảo sát, có tới 28 ứng dụng vi phạm quản lý dữ liệu và 25 ứng dụng không đáp ứng tiêu chuẩn bảo mật.
- Nguồn: Bài viết "AI hỗ trợ rối loạn ăn uống bị gỡ bỏ vì đưa ra lời khuyên có hại" — Tác giả TTXVN — Báo Nhân Dân điện tử — 22/06/2023 — [nhandan.vn/ai-ho-tro-roi-loan-an-uong-bi-go-bo-vi-dua-ra-loi-khuyen-co-hai-post758773.html](https://nhandan.vn/ai-ho-tro-roi-loan-an-uong-bi-go-bo-vi-dua-ra-loi-khuyen-co-hai-post758773.html)
- Phân biệt bằng chứng và nhận định: Bằng chứng: Lời kể của cựu nhân viên tư vấn NEDA (bà Nicole Doyle) xác nhận chatbot đã khuyên bệnh nhân giảm cân, tổ chức NEDA gỡ bỏ chatbot. Nhận định: Mặc dù AI có thể "mô phỏng" sự đồng cảm, nhưng không giống sự đồng cảm thực sự của con người, dẫn đến lời khuyên sai lệch nguy hiểm.

#### Harm Map Worksheet

| Trường                     | Phân tích của tôi                                                                                                                                                             |
| ---------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| High-risk moment             | Khi người dùng nhắn tin cho chatbot để tìm kiếm sự đồng cảm và xin lời khuyên vượt qua các triệu chứng tâm lý.                                              |
| Stakeholder bị ảnh hưởng | Người dùng trực tiếp (bệnh nhân tâm lý), Tổ chức NEDA và đội ngũ nhân viên cũ (bị cho thôi việc).                                                            |
| Failure mode                 | Harmful advice (AI đưa lời khuyên giảm cân, có thể gây hại trực tiếp cho bệnh nhân).                                                                                |
| Layer bắt đầu lỗi        | Safety. Hệ thống thiếu lớp bảo vệ (guardrails) để nhận diện và chặn các thông tin về giảm cân đối với nhóm người dùng nhạy cảm này.                    |
| Harm xảy ra là gì?        | Bệnh nhân bị tổn thương tâm lý, hành vi rối loạn ăn uống có nguy cơ bị kích hoạt lại trầm trọng hơn (Đã xảy ra nguy cơ, NEDA phải ngắt hệ thống).   |
| Harm lens                    | Injury (Tổn hại tâm lý / sức khỏe thể chất).                                                                                                                              |
| Severity                     | High. Lời khuyên sai cho người bệnh tâm lý có thể dẫn đến hành vi tự hại.                                                                                          |
| Scale                        | Medium. Tác động tới cộng đồng người bệnh tại Mỹ thông qua hệ thống đường dây trợ giúp quốc gia.                                                            |
| Probability                  | High. Rất dễ xảy ra vì AI thường lấy kiến thức chung "giảm cân là tốt" áp dụng sai cho bối cảnh "rối loạn ăn uống".                                          |
| Frequency                    | Medium. Xảy ra nhiều lần trong vài ngày đầu vận hành cho đến khi hệ thống bị gỡ bỏ.                                                                               |
| Vì sao?                     | Căn cứ theo báo cáo từ Báo Nhân Dân, hệ thống AI chỉ biết "mô phỏng" chữ viết mà không có sự thấu cảm thực sự, chưa được kiểm định y tế an toàn. |

### 3. Case study 2 — Chatbot AI tâm lý Eliza khuyến khích người dùng tự sát

#### Brief Case

- Tổ chức / sản phẩm AI: Ứng dụng nhắn tin Chai / Chatbot AI tên là Eliza (do phòng nghiên cứu EleutherAI phát triển như giải pháp thay thế mã nguồn mở cho OpenAI).
- Thời gian, địa điểm / bối cảnh: Khoảng tháng 3/2023, tại Bỉ. Một người đàn ông (khoảng 30 tuổi, có 2 con) bị trầm cảm vì "cực kỳ bi quan về tác động của sự nóng lên toàn cầu" nên đã tìm đến chatbot Eliza để tâm sự.
- AI được dùng để làm gì: Trò chuyện, giải đáp thắc mắc, đóng vai trò như một "người bạn tâm giao" để thảo luận về các vấn đề sinh thái.
- Vấn đề hoặc sự kiện đáng chú ý: Chatbot liên tục hùa theo suy nghĩ bi quan của người dùng. Tệ hơn, nó hỏi anh ta có nghĩ đến việc tự tử không, gửi các đoạn Kinh Thánh và cổ vũ anh ta tự sát với câu hỏi: "Nếu anh đã muốn chết, sao không thực hiện sớm hơn?". Sau 6 tuần, nạn nhân đã tự kết liễu đời mình.
- Số liệu có nguồn: Cuộc trò chuyện liên tục trong 6 tuần. Sau thảm kịch, Chai Research phải gấp rút cập nhật tính năng cảnh báo văn bản bên dưới khi người dùng nhắc đến nội dung nhạy cảm (tương tự Twitter/Instagram).
- Nguồn: Bài viết "Người đàn ông tự tử sau khi tâm sự với chatbot AI" — Báo VietNamNet — 03/04/2023 — [vietnamnet.vn/nguoi-dan-ong-tu-tu-sau-khi-tam-su-voi-chatbot-ai-2127876.html](https://vietnamnet.vn/nguoi-dan-ong-tu-tu-sau-khi-tam-su-voi-chatbot-ai-2127876.html)
- Phân biệt bằng chứng và nhận định: Bằng chứng: Lịch sử chat xác nhận AI đã hỏi "Nếu anh đã muốn chết, sao không thực hiện sớm hơn?" và nói "anh vẫn muốn bên cạnh em chứ?". Nhận định: "Nếu không có Eliza thì anh ấy vẫn còn sống", vợ nạn nhân nhận định, cho thấy vai trò quyết định của AI trong bi kịch này.

#### Harm Map Worksheet

| Trường                     | Phân tích của tôi                                                                                                                                                                                                                                                                   |
| ---------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| High-risk moment             | Khi người dùng mất niềm tin vào con người, rơi vào bế tắc và để lộ ý định tự kết thúc cuộc đời trong quá trình trò chuyện.                                                                                                                                 |
| Stakeholder bị ảnh hưởng | Bệnh nhân (tử vong), Vợ và 2 con nhỏ của nạn nhân (mất đi trụ cột gia đình), Công ty phát triển Chai Research (khủng hoảng truyền thông).                                                                                                                         |
| Failure mode                 | Harmful advice / Sycophancy (AI không thể nhận biết yếu tố đạo đức, hùa theo sự tiêu cực và trực tiếp cổ vũ hành vi tự hại).                                                                                                                                      |
| Layer bắt đầu lỗi        | Safety / Grounding. Hệ thống thiếu "la bàn đạo đức" và bộ lọc an toàn để phản ứng lại các yếu tố vô hình của con người như ý định tự tử, thay vào đó nó tạo ra ảo giác (hallucination) tình cảm.                                                |
| Harm xảy ra là gì?        | Người dùng đã tự sát tử vong (Đã xảy ra thảm kịch).                                                                                                                                                                                                                        |
| Harm lens                    | Injury (Tổn hại lớn nhất về tính mạng con người và nỗi đau tinh thần của gia đình).                                                                                                                                                                                     |
| Severity                     | Critical. Hậu quả là cái chết của người dùng, không thể vãn hồi.                                                                                                                                                                                                           |
| Scale                        | Low. Ghi nhận 1 ca tử vong trực tiếp ở trường hợp này. Tuy nhiên tác động có thể lan rộng vì ứng dụng được truy cập bởi nhiều người dùng đại chúng.                                                                                                      |
| Probability                  | High. Với các mô hình LLM mở thiếu đi "la bàn đạo đức" và không được tinh chỉnh an toàn chuyên sâu, việc hùa theo hội thoại tiêu cực là hành vi rất dễ xảy ra.                                                                                          |
| Frequency                    | Low. Hành vi tự sát trực tiếp là cực đoan, nhưng khả năng AI thế hệ cũ đưa ra các đoạn chat độc hại nếu bị dẫn dắt là rất cao.                                                                                                                              |
| Vì sao?                     | Các mô hình ngôn ngữ lớn (như mã nguồn mở được đề cập) thường chỉ cố gắng dự đoán từ tiếp theo để làm hài lòng người dùng. Thiếu bộ quy tắc an toàn (như tính năng can thiệp khủng hoảng), AI vô tình đẩy người bệnh đến bờ vực. |

### 4. Case study 3 — Chatbot khuyên bệnh nhân nguy kịch ở nhà nghỉ ngơi

#### Brief Case

- Tổ chức / sản phẩm AI: OpenAI / Chatbot ChatGPT (phiên bản GPT-4o).
- Thời gian, địa điểm / bối cảnh: Ngày 22/7/2026, tại Mỹ. Mục sư Scott Winters (bang Florida) đệ đơn kiện OpenAI lên Tòa Thượng thẩm bang California sau khi gặp nguy kịch vì nghe theo tư vấn y tế của ChatGPT.
- AI được dùng để làm gì: Hỏi đáp tư vấn sức khỏe, chẩn đoán triệu chứng (chóng mặt tái phát và đau vùng bẹn).
- Vấn đề hoặc sự kiện đáng chú ý: ChatGPT đưa ra chẩn đoán sai, khuyên người bệnh ở nhà nghỉ ngơi, hạn chế vận động và khẳng định triệu chứng không nguy hiểm, đồng thời dùng ngôn ngữ tôn giáo ("Chúa không thiết kế cơ thể bạn để nó suy sụp vô tận") để củng cố niềm tin. Hậu quả là bệnh nhân phớt lờ lời khuyên đi khám của người nhà, trì hoãn đi cấp cứu và sau đó nhập viện trong tình trạng nguy kịch.
- Số liệu có nguồn: 1 ngày sau cuộc trò chuyện với AI, bệnh nhân phải nhập viện cấp cứu khẩn cấp với bệnh lý thuyên tắc phổi (theo đơn kiện nộp ngày 22/7/2026).
- Nguồn: Bài viết "Mục sư tại Mỹ kiện OpenAI vì lời khuyên y tế của ChatGPT" — Báo Dân trí — 23/07/2026 — [dantri.com.vn/the-gioi/muc-su-my-suyt-chet-vi-nghe-loi-khuyen-y-te-tu-chatgpt-20260723120920715.htm](https://dantri.com.vn/the-gioi/muc-su-my-suyt-chet-vi-nghe-loi-khuyen-y-te-tu-chatgpt-20260723120920715.htm)
- Phân biệt bằng chứng và nhận định: Bằng chứng: Đơn kiện có lịch sử trò chuyện (AI khuyên hạn chế vận động) và bệnh án nhập viện (thuyên tắc phổi). Nhận định: Bác sĩ nhận định việc ít vận động theo gợi ý của AI có khả năng đã làm tình trạng nghiêm trọng hơn; OpenAI nhận định rằng quy trách nhiệm y tế hoàn toàn cho chatbot là cách nhìn đơn giản hóa.

#### Harm Map Worksheet

| Trường                     | Phân tích của tôi                                                                                                                                                                       |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| High-risk moment             | Khi AI được hỏi về các triệu chứng y tế nghiêm trọng (chóng mặt, đau bẹn) và quyết định đưa lời khuyên thay vì từ chối và yêu cầu cấp cứu.                   |
| Stakeholder bị ảnh hưởng | Người dùng trực tiếp (bệnh nhân), gia đình bệnh nhân (bị phớt lờ lời khuyên đi khám), đội ngũ y tế cấp cứu (phải xử lý ca biến chứng nặng).                   |
| Failure mode                 | Harmful advice (đưa lời khuyên có hại) và Sycophancy (dùng ngôn ngữ tôn giáo hùa theo tâm lý để củng cố sự an tâm giả tạo).                                          |
| Layer bắt đầu lỗi        | Safety / Model. Thiếu cơ chế an toàn (Safety guardrails) để tự động từ chối chẩn đoán ca cấp cứu; Mô hình (Model) tạo câu trả lời tự tin nhưng sai chuyên môn.    |
| Harm xảy ra là gì?        | Bệnh nhân gặp nguy hiểm tính mạng do thuyên tắc phổi không được cấp cứu kịp thời (đã xảy ra, bệnh nhân phải nhập viện nguy kịch).                                 |
| Harm lens                    | Injury (Tổn hại thể chất nghiêm trọng đe dọa sinh mạng).                                                                                                                           |
| Severity                     | Critical. Hậu quả trực tiếp đe dọa sinh mạng nếu không được cấp cứu kịp thời.                                                                                               |
| Scale                        | Low. Ghi nhận trực tiếp 1 vụ kiện cá nhân, tuy nhiên quy mô rủi ro tiềm ẩn (potential scale) là rất lớn đối với hàng triệu người dùng ứng dụng AI.                 |
| Probability                  | Medium. AI thường xuyên đưa ra các chẩn đoán sai lệch khi được hỏi về các triệu chứng lâm sàng phức tạp.                                                              |
| Frequency                    | Medium. Tình trạng người dân tự chẩn đoán bệnh qua chatbot đang ngày càng phổ biến.                                                                                          |
| Vì sao?                     | Severity đánh giá Critical vì bệnh lý là thuyên tắc phổi rất nguy hiểm. Lỗi ở lớp Safety vì mô hình không ngắt hội thoại khi nhận diện từ khóa y khoa khẩn cấp. |
