**Giới thiệu về dữ liệu**

Dữ liệu từ Điều tra xã hội chung 2016 (GSS16) Sự miêu tả GSS thu thập dữ
liệu về xã hội Mỹ đương đại để theo dõi và giải thích các xu hướng và
hằng số về thái độ, hành vi và thuộc tính. Hàng trăm xu hướng đã được
theo dõi kể từ năm 1972. Ngoài ra, kể từ khi GSS áp dụng các câu hỏi từ
các cuộc khảo sát trước đó, các xu hướng có thể được theo dõi trong tối
đa 70 năm. GSS chứa cốt lõi tiêu chuẩn gồm các câu hỏi về nhân khẩu học,
hành vi và thái độ, cộng với các chủ đề được quan tâm đặc biệt. Trong số
các chủ đề được đề cập là quyền tự do dân sự, tội phạm và bạo lực, lòng
khoan dung giữa các nhóm, đạo đức, ưu tiên chi tiêu quốc gia, sức khỏe
tâm lý, tính di động xã hội, căng thẳng và các sự kiện đau buồn.

Chi tiết Dữ liệu đến từ NORC tại Đại học Chicago. Dữ liệu đã được sửa
đổi để phục vụ tốt hơn cho các mục tiêu giáo dục cơ bản về khoa học dữ
liệu. Chỉ có 9 trong số 935 biến ban đầu được chọn cho tập dữ liệu này.

Đối tượng nghiên cứu

Trong nhiệm vụ này, chúng tôi phân tích dữ liệu từ GSS 2016, sử dụng nó
để ước tính giá trị dân số các thông số quan tâm về người lớn ở Hoa Kỳ.
Định dạng GSS16 chứa 2867 hàng và 9 cột.

Các trường được sử dụng để nghiên cứu

-   harass5: Trả lời câu hỏi \"Trong 5 năm qua, bạn có bị cấp trên hoặc
    đồng nghiệp quấy rối tại nơi làm việc không, ví dụ, bạn có bị bắt
    nạt, lạm dụng thể chất hoặc tâm lý không?\" Các câu trả lời có thể
    là Có, Không và Không áp dụng.

-   emalmin: Số thư điện tử Số phút dành cho email hàng tuần; thêm vào
    số giờ trong emailhrs (ví dụ: emailmin = 30 trong 2,5 giờ trên
    email).

-   emailhr: thư điện tử Số giờ dành cho email hàng tuần.

-   educ: Số năm đi học.

-   polviews: Quan điểm chính trị. Trả lời câu hỏi "Ngày nay chúng ta
    nghe nói nhiều về phe tự do và phe bảo thủ. Tôi sẽ cho bạn thấy một
    thang điểm bảy mà trên đó các quan điểm chính trị mà mọi người có
    thể nắm giữ được sắp xếp từ cực kỳ tự do--điểm 1--đến cực kỳ bảo
    thủ-- điểm 7. Bạn sẽ đặt mình ở đâu trên thang điểm này?" Các câu
    trả lời có thể là Cực kỳ tự do, Tự do, Hơi tự do, Trung bình, Hơi
    bảo thủ, Bảo thủ, Cực kỳ bảo thủ.

-   Advfront: Trả lời cho câu hỏi \"Ngay cả khi nó không mang lại lợi
    ích ngay lập tức, nghiên cứu khoa học nhằm nâng cao tri thức là cần
    thiết và cần được chính phủ liên bang hỗ trợ.\" Các câu trả lời có
    thể là Rất đồng ý, Đồng ý, Không biết, Không đồng ý và Rất không
    đồng ý.

-   snapchat: người trả lời sẽ trả lời câu hỏi có sử dụng Snapchat hay
    không.

-   instagram: người trả lời sẽ trả lời câu hỏi có sử dụng Instagram hay
    không.

-   Wrkstat: Tình trạng công việc.

**Phát biểu bài toán:**

Bài toán được đặt ra để trả lời câu hỏi về mức độ sử dụng email dựa trên
công việc; tần suất sử dụng một số mạng xã hội như Snapchat, Instagram;
số năm đi học; quan điểm về chính trị, nghiên cứu khoa học; và việc có
bị quấy rối, bắt nạt hay không.

**Giới thiệu lý thuyết:**

**Mô hình GLM (Generalized Linear Model)** là một họ các mô hình thống
kê mạnh mẽ và linh hoạt được sử dụng để mô hình hóa mối quan hệ giữa
biến phụ thuộc và các biến độc lập trong các tình huống không phải là
phân phối chuẩn. GLM mở rộng mô hình hồi quy tuyến tính thông thường để
bao gồm các phân phối khác và các hàm liên kết không tuyến tính để xác
định mối quan hệ giữa biến phụ thuộc và biến độc lập.

Mô hình GLM bao gồm ba thành phần chính:

-   Hàm Liên kết (Link function): Đây là hàm xác định mối quan hệ giữa
    giá trị kỳ vọng của biến phụ thuộc và tổng trọng số của biến độc
    lập. Hàm liên kết cần phải là một hàm liên tục, đồng biến và có đạo
    hàm.

-   Phân phối (Distribution): Đây là phân phối xác định biểu diễn phân
    phối của biến phụ thuộc. Các phân phối thường được sử dụng trong GLM
    bao gồm phân phối Poisson (cho mô hình đếm), phân phối Gaussian (cho
    mô hình hồi quy tuyến tính), phân phối Bernoulli (cho mô hình
    logistic), và nhiều phân phối khác.

-   Hàm liên hệ (Link function): Đây là một ánh xạ giữa giá trị kỳ vọng
    của biến phụ thuộc và tổng trọng số của biến độc lập. Ví dụ, trong
    mô hình hồi quy tuyến tính, hàm liên hệ thường là hàm đồng biến
    (identity function) để duy trì mối quan hệ tuyến tính. Trong trường
    hợp của mô hình logistic, hàm liên hệ là hàm logit.

Mô hình GLM có thể được sử dụng cho nhiều loại dữ liệu và mục tiêu khác
nhau, bao gồm:

-   Hồi quy tuyến tính (Linear Regression): Sử dụng khi biến phụ thuộc
    là liên tục và phân phối Gaussian.

-   Hồi quy logistic (Logistic Regression): Sử dụng khi biến phụ thuộc
    là nhị phân (0/1) và phân phối Bernoulli. Thường được sử dụng trong
    dự đoán xác suất của một sự kiện.

-   Hồi quy Poisson (Poisson Regression): Sử dụng khi biến phụ thuộc là
    số lượng đếm và phân phối Poisson. Thường được sử dụng trong việc mô
    hình hóa tần suất của các sự kiện.

-   Hồi quy nhị thức âm (Negative Binomial Regression): Sử dụng khi biến
    phụ thuộc là số lượng đếm và phân phối negative binomial. Thường
    được sử dụng khi dữ liệu có phương sai không ổn định hơn so với phân
    phối Poisson.

**Lý thuyết Bayes Generalized Linear Model (Bayes GLM)** là một phương
pháp thống kê kết hợp lý thuyết Bayes và mô hình tuyến tính tổng quát
(Generalized Linear Model - GLM) để ước tính tham số và dự đoán trong mô
hình tuyến tính mà đầu vào không phải là dữ liệu có phân phối chuẩn.

Để hiểu rõ hơn về Bayes GLM, chúng ta cần nắm vững hai khái niệm chính:
GLM và lý thuyết Bayes.

Generalized Linear Model (GLM):

Mô hình tuyến tính tổng quát (GLM) là một phương pháp cho phép xây dựng
mô hình tuyến tính giữa biến phụ thuộc và một tập các biến độc lập,
nhưng cho phép biến phụ thuộc không phải là một biến phân phối chuẩn.
GLM bao gồm ba thành phần chính: hàm liên kết (link function), phân phối
của biến phụ thuộc và hàm dự đoán.

**Lý thuyết Bayes:**

Lý thuyết Bayes là một lý thuyết trong xác suất thống kê dựa trên Định
lý Bayes, giúp chúng ta cập nhật kiến thức về một sự kiện dựa trên dữ
liệu mới. Lý thuyết Bayes thường sử dụng phân phối xác suất để thể hiện
sự không chắc chắn và cập nhật kiến thức dựa trên dữ liệu.

Khi kết hợp cả hai khái niệm này, Bayes GLM là một phương pháp ước tính
tham số trong mô hình tuyến tính tổng quát bằng cách sử dụng lý thuyết
Bayes. Thay vì sử dụng phương pháp cực đại hóa hàm hợp lý (Maximum
Likelihood Estimation - MLE) như trong GLM truyền thống, Bayes GLM sử
dụng phân phối xác suất a priori để mô tả sự không chắc chắn về các tham
số mô hình. Khi có dữ liệu mới, phân phối a priori này sẽ được cập nhật
thành phân phối hậu nghiệm (posterior distribution) dựa trên lý thuyết
Bayes.

Cách thức thực hiện Bayes GLM thường liên quan đến việc sử dụng phương
pháp MCMC (Markov Chain Monte Carlo) để xấp xỉ phân phối hậu nghiệm.
Điều này có thể phức tạp và đòi hỏi kiến thức sâu về xác suất thống kê
và lập trình.

**Hàm phạt trong các mô hình hồi quy**

Trong các mô hình hồi quy, hàm phạt (regularization) được sử dụng để
kiểm soát overfitting bằng cách thêm một thành phần phạt vào hàm mất
mát. Hàm phạt giúp giảm thiểu các trọng số của mô hình, từ đó làm giảm
sự phức tạp của mô hình và cân bằng giữa việc đánh đổi giữa sự khớp tốt
với dữ liệu huấn luyện và khả năng tổng quát hóa cho dữ liệu mới. Hai
hàm phạt phổ biến trong các mô hình hồi quy là Ridge và Lasso

Ridge Regression (L2 Regularization): Trong Ridge Regression, một thành
phần phạt được thêm vào hàm mất mát là tổng bình phương của các trọng số
(hệ số) của mô hình. Biểu thức của hàm mất mát trong Ridge Regression
là:

$$J(\theta) = Mất\ mát\ ban\ đầu*\ \alpha*\left\| \theta \right\|^{2}$$

Trong đó:

$J(\theta)$: Hàm mất mát

$\alpha$: Tham số điều chỉnh mức độ phạt

$\theta$: Vector trọng số của mô hình hồi quy

$\left\| \theta \right\|^{2}$: Chuẩn L2 của vector trọng số

**Lasso Regression (L1 Regularization)**: Lasso cũng thêm một thành phần
phạt vào hàm mất mát, nhưng ở đây là tổng trị tuyệt đối của các trọng số
của mô hình

$$J(\theta) = Mất\ mát\ ban\ đầu*\ \alpha*\left\| \theta \right\|_{1}$$

Trong đó:

$J(\theta)$: Hàm mất mát

$\alpha$: Tham số điều chỉnh mức độ phạt

$\theta$: Vector trọng số của mô hình hồi quy

$\left\| \theta \right\|_{1}$: Chuẩn L1 của vector trọng số

**Các metrics để đánh giá mô hình GLM**

**Mean Squared Error (MSE)**: Đây là một trong những metric phổ biến
nhất trong mô hình hồi quy. Nó tính toán trung bình của bình phương sai
giữa giá trị dự đoán và giá trị thực tế

Công thức:
$MSE = \ \frac{1}{n}*\sum_{}^{}{{(y}_{i} - \ {\widehat{y}}_{i})}^{2}$

Trong đó:

$n$: Số mẫu của dữ liệu

$y_{i}$: Giá trị thực tế thứ i

$\widehat{y}$: Giá trị dự đoán của mô hình

Đặc điểm của MSE:

-   Giá trị MSE càng nhỏ, mô hình càng tốt vì nó cho biết các dự đoán dự
    đoán gần với giá trị thực tế.

-   MSE có thể bị ảnh hưởng bởi các giá trị ngoại lai (outliers) vì
    chúng có thể gây ra sai số bình phương lớn.

-   MSE không có đơn vị cụ thể vì nó được tính bằng bình phương của đơn
    vị gốc (ví dụ, nếu dữ liệu đơn vị là đô la, thì MSE có đơn vị \"đô
    la bình phương\").

MSE thường được sử dụng cùng với các metric khác để đánh giá và so sánh
mô hình hồi quy.

**Root Mean Squared Error (RMSE)**: Đây là căn bậc hai của MSE và thường
được sử dụng để đo lường sai số trung bình theo đơn vị gốc

Công thức: $RMSE = \ \sqrt{MSE}$

**Mean Absolute Error (MAE)**: MAE tính trung bình giá trị tuyệt đối của
sai số giữa giá trị dự đoán và giá trị thực tế

Công thức:
$MAE = \ \frac{1}{n}*\ \sum_{}^{}\left| {(y}_{i} - \ {\widehat{y}}_{i} \right|$

**Coefficient of Determination (R²):** R² đo lường mức độ biến thiên của
biến phụ thuộc mà mô hình có thể giải thích. Giá trị R² nằm trong khoảng
\[0, 1\], và giá trị càng gần 1 thì mô hình càng tốt:

Công thức:
$R^{2} = 1 - \ \left( \frac{\sum_{}^{}{{(y}_{i} - \ {\widehat{y}}_{i})}^{2}}{\sum_{}^{}{{(y}_{i} - \ \overline{y})}^{2}} \right)$

Trong đó:

$n$: Số mẫu của dữ liệu

$y_{i}$: Giá trị thực tế thứ i

${\widehat{y}}_{i}$: Giá trị dự đoán của mô hình

$\overline{y}$: Giá trị trung bình của mô hình

**Random Forest** là một thuật toán học máy dựa trên việc xây dựng nhiều
cây quyết định (Decision Trees) độc lập và kết hợp kết quả từ các cây
này để đưa ra dự đoán cuối cùng. Nó giúp cải thiện hiệu suất dự đoán và
ổn định mô hình bằng cách giảm thiểu overfitting và tăng tính tổng quát
hóa. Dưới đây là chi tiết về thuật toán Random Forest:

-   Tạo dữ liệu mẫu (Bootstrapping): Để xây dựng mỗi cây quyết định
    trong Random Forest, chúng ta sẽ tạo ra một tập dữ liệu mẫu từ tập
    dữ liệu huấn luyện bằng cách lấy ngẫu nhiên và có thay thế các mẫu.
    Quá trình này được gọi là bootstrapping.

-   Xây dựng cây quyết định: Với mỗi tập dữ liệu mẫu, ta sẽ xây dựng một
    cây quyết định độc lập bằng cách phân chia dữ liệu theo các thuộc
    tính và giá trị để tối ưu hóa một hàm mục tiêu, thường là tối thiểu
    hóa sai số hoặc tối ưu hóa Gini index (trong trường hợp cây phân
    loại). Quá trình này tiếp tục cho đến khi một điều kiện dừng được
    đáp ứng, chẳng hạn như độ sâu tối đa của cây.

-   Kết hợp dự đoán từ các cây: Khi đã xây dựng các cây quyết định,
    chúng ta có thể sử dụng chúng để đưa ra dự đoán cho các mẫu dữ liệu
    mới. Dự đoán từ mỗi cây đóng vai trò như một phiếu bầu cho một lớp
    (trong trường hợp phân loại) hoặc một giá trị (trong trường hợp hồi
    quy).

-   Kết hợp kết quả từ các cây: Để đưa ra dự đoán cuối cùng, chúng ta
    kết hợp kết quả từ tất cả các cây trong Random Forest. Trong trường
    hợp phân loại, kết quả cuối cùng thường là lớp có số phiếu bầu nhiều
    nhất từ các cây. Trong trường hợp hồi quy, kết quả cuối cùng thường
    là trung bình hoặc trung vị của các dự đoán từ các cây.

Một trong những lợi ích quan trọng của Random Forest là khả năng kiểm
soát overfitting. Bằng cách sử dụng nhiều cây quyết định độc lập, thuật
toán giảm khả năng mô hình bị overfitting vào dữ liệu huấn luyện. Random
Forest có thể được áp dụng cho cả các vấn đề phân loại và hồi quy. Nó
cũng có thể xử lý cả dữ liệu dạng số và dữ liệu dạng danh mục. Thuật
toán Random Forest đã được chứng minh là một công cụ mạnh mẽ trong học
máy và có thể được sử dụng trong nhiều ứng dụng khác nhau như phân loại
hình ảnh, dự đoán giá cổ phiếu, dự đoán bệnh tật, và nhiều lĩnh vực
khác.
