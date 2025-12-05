---
title: "Blog 3"
date: 2025-09-09
weight: 1
chapter: false
pre: " <b> 3.3. </b> "
---


# Đẩy nhanh đổi mới khoa học dữ liệu: Cách Bayer Crop Science sử dụng các dịch vụ AWS AI/ML để xây dựng dịch vụ MLOps thế hệ tiếp theo của họ

bởi Lance Smith, Jake Malmad, Karthik Prabhakar, Kenton Blacutt, và Nicole Brown vào ngày 08 tháng 7 năm 2025 trong Amazon API Gateway, Amazon EventBridge, Amazon Q, Amazon Q Business, Amazon Q Developer, Amazon SageMaker, Amazon SageMaker Data & AI Governance, Artificial Intelligence, Customer Solutions, Generative AI | Permalink | Comments | Share

Dân số thế giới đang tăng với tốc độ nhanh chóng. Dân số toàn cầu ngày càng tăng đòi hỏi các giải pháp sáng tạo để sản xuất thực phẩm, sợi và nhiên liệu, đồng thời khôi phục các nguồn tài nguyên thiên nhiên như đất và nước và giải quyết vấn đề biến đổi khí hậu. Bayer Crop Science ước tính nông dân cần tăng sản lượng cây trồng 50% vào năm 2050 để đáp ứng những nhu cầu này. Để hỗ trợ sứ mệnh của họ, Bayer Crop Science đang hợp tác với nông dân và các đối tác để thúc đẩy và mở rộng quy mô nông nghiệp tái sinh—một tương lai nơi canh tác có thể sản xuất nhiều hơn trong khi khôi phục môi trường.

Nông nghiệp tái sinh là một triết lý canh tác bền vững nhằm cải thiện sức khỏe đất bằng cách kết hợp thiên nhiên để tạo ra các hệ sinh thái lành mạnh. Nó dựa trên ý tưởng rằng nông nghiệp nên khôi phục đất bị suy thoái và đảo ngược sự xuống cấp, thay vì duy trì các điều kiện hiện tại. Bộ phận Crop Science tại Bayer tin rằng nông nghiệp tái sinh là nền tảng cho tương lai của canh tác. Tầm nhìn của họ là sản xuất nhiều thực phẩm hơn 50% bằng cách khôi phục thiên nhiên và mở rộng quy mô nông nghiệp tái sinh. Để biến sứ mệnh này thành hiện thực, Bayer Crop Science đang thúc đẩy việc training model với Amazon SageMaker và đẩy nhanh tài liệu hóa code với Amazon Q.

Trong bài viết này, chúng tôi trình bày cách Bayer Crop Science quản lý các hoạt động khoa học dữ liệu quy mô lớn bằng cách training models cho nhu cầu phân tích dữ liệu của họ và duy trì tài liệu code chất lượng cao để hỗ trợ các nhà phát triển. Thông qua các giải pháp này, Bayer Crop Science dự kiến giảm tới 70% thời gian onboarding nhà phát triển và cải thiện tới 30% năng suất của nhà phát triển.

## Thách thức

Bayer Crop Science phải đối mặt với thách thức mở rộng quy mô mô hình dự đoán genomic để tăng tốc độ ra thị trường. Công ty cũng cần các nhà khoa học dữ liệu tập trung vào việc xây dựng các foundation models (FMs) có giá trị cao, thay vì lo lắng về việc xây dựng và thiết kế giải pháp. Trước khi xây dựng giải pháp Decision Science Ecosystem của họ, việc cung cấp một môi trường khoa học dữ liệu có thể mất nhiều ngày cho một nhóm dữ liệu trong Bayer Crop Science.

## Tổng quan về giải pháp

Decision Science Ecosystem (DSE) của Bayer Crop Science là một giải pháp machine learning operations (MLOps) thế hệ tiếp theo được xây dựng trên AWS để đẩy nhanh việc ra quyết định dựa trên dữ liệu cho các nhóm khoa học dữ liệu ở quy mô lớn trên toàn tổ chức. Các dịch vụ AWS hỗ trợ Bayer Crop Science trong việc tạo ra một hệ thống ra quyết định được kết nối có thể truy cập được cho hàng nghìn nhà khoa học dữ liệu. Công ty đang sử dụng giải pháp cho generative AI, tiến bộ trong pipeline sản phẩm, phân tích hình ảnh địa không gian của dữ liệu đồng ruộng, và mô hình dự đoán genomic quy mô lớn sẽ cho phép Bayer Crop Science trở nên dựa vào dữ liệu nhiều hơn và tăng tốc độ ra thị trường. Giải pháp này hỗ trợ nhà khoa học dữ liệu ở mọi bước, từ ý tưởng đến đầu ra của model, bao gồm toàn bộ hồ sơ quyết định kinh doanh được thực hiện bằng DSE. Các bộ phận khác trong Bayer cũng đang bắt đầu xây dựng một giải pháp tương tự trên AWS dựa trên sự thành công của DSE.

DSE của các nhóm Bayer Crop Science tích hợp liền mạch với SageMaker, một dịch vụ được quản lý hoàn toàn cho phép các nhà khoa học dữ liệu nhanh chóng build, train và deploy các machine learning (ML) models cho các use case khác nhau để họ có thể đưa ra quyết định dựa trên dữ liệu một cách nhanh chóng. Điều này thúc đẩy sự hợp tác trong Bayer Crop Science giữa cung ứng sản phẩm, R&D và thương mại. Chiến lược khoa học dữ liệu của họ không còn cần data engineering tự phục vụ, mà thay vào đó cung cấp một nguồn lực hiệu quả để thúc đẩy data engineering nhanh ở quy mô lớn. Bayer Crop Science chọn SageMaker vì nó cung cấp một trải nghiệm gắn kết duy nhất nơi các nhà khoa học dữ liệu có thể tập trung vào việc xây dựng các models có giá trị cao, mà không phải lo lắng về việc xây dựng và thiết kế chính tài nguyên đó. Với sự trợ giúp của các dịch vụ AWS, các nhóm đa chức năng có thể sắp xếp nhanh chóng để giảm chi phí vận hành bằng cách giảm thiểu sự dư thừa, giải quyết lỗi sớm và thường xuyên, và nhanh chóng xác định các vấn đề trong các workflows tự động. Giải pháp DSE sử dụng SageMaker, Amazon Elastic Kubernetes Service (Amazon EKS), AWS Lambda, và Amazon Simple Storage Service (Amazon S3) để đẩy nhanh đổi mới tại Bayer Crop Science và tạo ra trải nghiệm người dùng end-to-end liền mạch, được tùy chỉnh.

Sơ đồ sau minh họa kiến trúc DSE.

## Hướng dẫn giải pháp

Bayer Crop Science có hai thách thức chính trong việc quản lý các hoạt động khoa học dữ liệu quy mô lớn: duy trì tài liệu code chất lượng cao và tối ưu hóa tài liệu hiện có trên nhiều repositories. Với Amazon Q, Bayer Crop Science đã giải quyết cả hai thách thức, giúp họ onboard các nhà phát triển nhanh hơn và cải thiện năng suất của nhà phát triển.

Use case đầu tiên của công ty tập trung vào việc tự động tạo tài liệu code chất lượng cao. Khi một nhà phát triển push code lên GitHub repository, một webhook—một giao tiếp nhẹ, hướng sự kiện tự động gửi dữ liệu giữa các ứng dụng bằng HTTP—kích hoạt một Lambda function thông qua Amazon API Gateway. Function này sau đó sử dụng Amazon Q để phân tích các thay đổi code và tạo tài liệu toàn diện cũng như tóm tắt thay đổi. Tài liệu được cập nhật sau đó được lưu trữ trong Amazon S3. Cùng Lambda function cũng tạo một pull request với bản tóm tắt các thay đổi code do AI tạo ra. Để duy trì tính bảo mật và linh hoạt, Bayer Crop Science sử dụng Parameter Store, một khả năng của AWS Systems Manager, để quản lý prompts cho Amazon Q, cho phép cập nhật nhanh chóng mà không cần triển khai lại, và AWS Secrets Manager để xử lý an toàn các repository tokens.

Tự động hóa này giảm đáng kể thời gian các nhà phát triển dành cho việc tạo tài liệu và mô tả pull request. Tài liệu được tạo cũng được đưa vào Amazon Q, để các nhà phát triển có thể nhanh chóng trả lời các câu hỏi họ có về một repository và onboard vào các dự án.

Use case thứ hai giải quyết thách thức duy trì và cải thiện chất lượng tài liệu code hiện có. Một AWS Batch job, được kích hoạt bởi Amazon EventBridge, xử lý code repository. Amazon Q tạo tài liệu mới cho mỗi file code, sau đó được lập index cùng với source code. Hệ thống cũng tạo tài liệu cấp cao cho mỗi module hoặc chức năng và so sánh tài liệu do AI tạo ra với tài liệu hiện có do con người viết. Quy trình này giúp Bayer Crop Science có thể đánh giá và nâng cao chất lượng tài liệu của họ một cách có hệ thống theo thời gian.

Để cải thiện khả năng tìm kiếm, Bayer Crop Science đã thêm tên repository làm custom attributes trong Amazon Q index và thêm prefix chúng vào nội dung được lập index. Cải tiến này cải thiện độ chính xác và tính liên quan của các tìm kiếm tài liệu. Nhóm phát triển cũng triển khai các chiến lược để xử lý API throttling và sự biến động trong các phản hồi AI, duy trì tính mạnh mẽ trong môi trường production. Bayer Crop Science đang xem xét phát triển một management plane để hợp lý hóa việc thêm các repositories mới và tập trung hóa việc quản lý settings, tokens và prompts. Điều này sẽ tiếp tục nâng cao khả năng mở rộng và tính dễ sử dụng của hệ thống.

Các tổ chức muốn tái tạo thành công của Bayer Crop Science có thể triển khai việc tạo tài liệu được kích hoạt bởi webhook tương tự, sử dụng Amazon Q Business cho cả việc tạo và đánh giá chất lượng tài liệu, và tích hợp giải pháp với các quy trình version control và code review hiện có. Bằng cách sử dụng các dịch vụ AWS như Lambda, Amazon S3, và Systems Manager, các công ty có thể tạo một kiến trúc có thể mở rộng và quản lý được cho nhu cầu tài liệu của họ. Amazon Q Developer cũng giúp các tổ chức đẩy nhanh hơn nữa các mốc thời gian phát triển của họ bằng cách cung cấp các đề xuất code theo thời gian thực và trải nghiệm chat thế hệ tiếp theo tích hợp sẵn.

"Một trong những bài học chúng tôi học được trong 10 năm qua là chúng tôi muốn viết ít code hơn. Chúng tôi muốn tập trung thời gian và đầu tư của mình chỉ vào những thứ mang lại giá trị khác biệt cho Bayer, và chúng tôi muốn tận dụng mọi thứ mà AWS cung cấp sẵn. Một phần mục tiêu của chúng tôi là giảm các chu kỳ phát triển cần thiết để chuyển một model từ giai đoạn proof-of-concept, sang production, và cuối cùng là áp dụng trong kinh doanh. Đó là nơi có giá trị."

– Will McQueen, VP, Head of CS Global Data Assets and Analytics tại Bayer Crop Science.

## Tóm tắt

Cách tiếp cận của Bayer Crop Science phù hợp với các thực hành MLOps hiện đại, cho phép các nhóm khoa học dữ liệu tập trung nhiều hơn vào các tác vụ modeling có giá trị cao thay vì các quy trình tài liệu hóa tốn thời gian và quản lý hạ tầng. Bằng cách áp dụng các thực hành này, các tổ chức có thể giảm đáng kể thời gian và nỗ lực cần thiết cho tài liệu hóa code trong khi cải thiện chất lượng code tổng thể và sự hợp tác trong nhóm.

Tìm hiểu thêm về hành trình generative AI của Bayer Crop Science, và khám phá cách Bayer Crop Science đang thiết kế lại các thực hành bền vững thông qua công nghệ tiên tiến.

## Về Bayer

Bayer là một doanh nghiệp toàn cầu với năng lực cốt lõi trong các lĩnh vực khoa học đời sống về chăm sóc sức khỏe và dinh dưỡng. Phù hợp với sứ mệnh của mình, "Sức khỏe cho tất cả, Không còn đói nghèo," các sản phẩm và dịch vụ của công ty được thiết kế để giúp con người và hành tinh phát triển bằng cách hỗ trợ các nỗ lực hiểu rõ các thách thức lớn do dân số toàn cầu tăng trưởng và già đi đặt ra. Bayer cam kết thúc đẩy phát triển bền vững và tạo ra tác động tích cực với các hoạt động kinh doanh của mình. Đồng thời, Bayer hướng đến việc tăng sức mạnh kiếm tiền và tạo giá trị thông qua đổi mới và tăng trưởng. Thương hiệu Bayer đại diện cho sự tin cậy, độ tin cậy và chất lượng trên toàn thế giới. Trong năm tài chính 2023, Tập đoàn có khoảng 100.000 nhân viên và có doanh thu 47,6 tỷ euro. Chi phí R&D trước các khoản mục đặc biệt lên tới 5,8 tỷ euro. Để biết thêm thông tin, truy cập www.bayer.com.

## Về tác giả

**Lance Smith** là Senior Solutions Architect và là một phần của bộ phận ngành Healthcare and Life Sciences toàn cầu tại AWS. Ông đã dành 2 thập kỷ qua giúp các công ty khoa học đời sống áp dụng công nghệ để theo đuổi sứ mệnh giúp đỡ bệnh nhân của họ. Ngoài công việc, ông thích du lịch, đi bộ đường dài và dành thời gian với gia đình.

**Kenton Blacutt** là AI Consultant trong nhóm Amazon Q Customer Success. Ông làm việc trực tiếp với khách hàng, giúp họ giải quyết các vấn đề kinh doanh thực tế với các công nghệ AWS tiên tiến. Trong thời gian rảnh, ông thích đi du lịch và thỉnh thoảng chạy marathon.

**Karthik Prabhakar** là Senior Applications Architect trong nhóm AWS Professional Services. Trong vai trò này, ông hợp tác với khách hàng để thiết kế và triển khai các giải pháp tiên tiến cho các hệ thống kinh doanh quan trọng của họ, tập trung vào các lĩnh vực như khả năng mở rộng, độ tin cậy, và tối ưu hóa chi phí trong các dự án chuyển đổi số và hiện đại hóa.

**Jake Malmad** là Senior DevOps Consultant trong nhóm AWS Professional Services, chuyên về infrastructure as code, security, containers, và orchestration. Là một DevOps consultant, ông sử dụng chuyên môn này để hợp tác với khách hàng, thiết kế và triển khai các giải pháp cho tự động hóa, khả năng mở rộng, độ tin cậy, và bảo mật trên nhiều loại dự án áp dụng cloud và chuyển đổi.

**Nicole Brown** là Senior Engagement Manager trong nhóm AWS Professional Services có trụ sở tại Minneapolis, MN. Với hơn 10 năm kinh nghiệm chuyên môn, cô đã lãnh đạo các nhóm đa ngành, toàn cầu trong các ngành healthcare và life sciences. Cô cũng là người ủng hộ phụ nữ trong công nghệ và hiện đang giữ vị trí hội đồng quản trị trong Women at Global Services affinity group.