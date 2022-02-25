# Bài toán.
- Failure prediction (Dự đoán thất bại) là một chủ đề chính trong predictive maintenance (bảo trì dự đoán) trong nhiều ngành công nghiệp. Các hãng hàng không đặc biệt quan tâm đến việc dự đoán trước các hỏng hóc của thiết bị để có thể tăng cường hoạt động và giảm tình trạng chậm trễ chuyến bay.

- Việc quan sát tình trạng và sức khỏe của động cơ thông qua các cảm biến và dữ liệu đo từ xa được giả định là để tạo điều kiện thuận lợi cho loại bảo trì này bằng cách dự đoán Time-To-Failure (TTF - Thời gian Không hỏng hóc) hoặc Remaining Useful Life (RUL - Tuổi thọ Hữu ích Còn lại) của thiết bị đang sử dụng. Sử dụng các phép đo cảm biến của động cơ máy bay, chúng ta có thể dự đoán TTF của động cơ.

- Một công ty hàng không, cố gắng tận dụng historical data của các cảm biến thiết bị để đưa ra quyết định dựa trên dữ liệu về kế hoạch bảo trì của mình. Dựa trên phân tích này, công ty sẽ có thể ước tính thời gian hư hỏng của động cơ và tối ưu hóa các hoạt động bảo trì của nó cho phù hợp.

# Data
- Các text files chứa các động cơ chạy đến hỏng của động cơ máy bay được mô phỏng.
- Cài đặt hoạt động và 21 phép đo cảm biến. Giả định rằng mô hình suy thoái tiến triển của động cơ được phản ánh trong các phép đo cảm biến của nó.

- Training Data: Dữ liệu động cơ chạy đến lỗi. download training
- Test Data: Dữ liệu vận hành động cơ mà không có sự kiện hỏng hóc được ghi lại. download test data
- Ground Truth Data: Các chu kỳ thực còn lại cho mỗi động cơ trong test data. download truth data


Note:
- col_names = ['id', 'cycle', 'setting1', 'setting2', 'setting3', 's1', 's2', 's3', 's4', 's5', 's6', 's7', 's8', 's9', 's10', 's11', 's12', 's13', 's14', 's15', 's16', 's17', 's18', 's19', 's20', 's21']
+ id: là ID động cơ, nằm trong khoảng từ 1 đến 100.
+ cycle: chu kỳ cho mỗi chuỗi động cơ, bắt đầu từ 1 đến số chu kỳ đã xảy ra lỗi (training data)
+ setting 1 to setting 3: cài đặt hoạt động động cơ.
+ s1 to s21: các phép đo cảm biến.


# Approach:
- Bằng cách khám phá các giá trị cảm biến của động cơ máy bay theo thời gian, thuật toán machine learning có thể tìm hiểu mối quan hệ giữa các giá trị cảm biến và những thay đổi trong giá trị cảm biến với các lỗi lịch sử để dự đoán các lỗi hỏng hóc trong tương lai. 


# Goals:

- Regression Modeling algorithms được sử dụng để dự đoán số chu kỳ còn lại trước khi động cơ bị hỏng.
- Binary Classification được sử dụng để dự đoán xem động cơ có bị lỗi trong cửa sổ chu kỳ cụ thể hay không
- Multiclass classification được sử dụng để dự đoán trong khoảng thời gian hoặc khoảng thời gian chu kỳ nào một động cơ sẽ bị lỗi.
