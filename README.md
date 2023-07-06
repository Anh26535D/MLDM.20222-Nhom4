# Predict Student Performance from Game Play
Nhóm 4 - Nhập môn Học máy và Khai phá dữ liệu - 20222 - Đại học Bách Khoa Hà Nội
## Thành viên nhóm
* Đàm Việt Anh - 20204627 - anh.dv204627@sis.hust.edu.vn
* Vũ Việt Anh - 20200053 - anh.vv200053@sis.hust.edu.vn
* Phạm Quang Minh - 20204588 - minh.pq204588@sis.hust.edu.vn
* Nguyễn Trung Hiếu - 20204551 - hieu.nt204551@sis.hust.edu.vn
* Trịnh Quang Quân - 20200511 - quan.tq@sis.hust.edu.vn
### Lời cảm ơn
  Đây là tệp mã nguồn đồ án môn học Nhập môn Học máy và Khai phá dữ liệu do PGS. TS Thân Quang Khoát phụ trách. Lời đầu tiên, chúng em xin gửi lời cảm ơn đến giảng viên bộ môn là thầy Thân Quang Khoát, đã nhiệt tình giảng dạy và góp ý để chúng em hoàn thành bài tập lớn môn học. Những bài giảng trên nền tảng youtube của thầy là nguồn gợi ý thiết thực cho việc tìm các giải pháp cải thiện cho bài toán. Chúng em xin phép được gắn link youtube bài giảng của thầy tại đây: https://www.youtube.com/@thanquangkhoat4070. Cuối cùng, nhóm chúng em xin kính chúc thầy có thật nhiều sức khỏe, hành phúc và luôn thành công trong sự nghiệp giảng dạy của mình.
## Hướng dẫn 
* Đường link đến tập dữ liệu: https://www.kaggle.com/competitions/predict-student-performance-from-game-play/overview
* Mô tả:
  Học tập dựa trên trò chơi là một phương pháp giáo dục cho phép học sinh tương tác với nội dung giáo dục bên trong khung trò chơi, khiến nội dung trở nên thú vị và năng động. Mặc dù học tập dựa trên trò chơi đang được sử dụng ngày càng nhiều trong các môi trường giáo dục, nhưng vẫn có một số bộ dữ liệu mở hạn chế có sẵn để áp dụng khoa học dữ liệu và các nguyên tắc phân tích học tập nhằm cải thiện việc học tập dựa trên trò chơi. Hầu hết các nền tảng học tập dựa trên trò chơi không tận dụng đầy đủ khả năng truy tìm kiến thức để hỗ trợ từng học sinh. Các phương pháp truy tìm kiến thức đã được phát triển và nghiên cứu trong bối cảnh môi trường học tập trực tuyến và hệ thống dạy kèm thông minh, nhưng ít tập trung vào truy tìm kiến thức trong các trò chơi giáo dục.
  Do đó, Field Day Lab, là một phòng thí nghiệm nghiên cứu được tài trợ công khai tại Trung tâm Nghiên cứu Giáo dục Wisconsin, cùng với The Learning Agency Lab, tổ chức cuộc thi trên Kaggle với mong muốn dựa trên các mô hình học máy nhằm dự đoán hiệu suất của học sinh trong trò chơi, giúp các nhà phát triển cải thiện nền tảng học dựa trên trò chơi của họ.
Trò chơi với tên gọi Jo Wilder, là một trò chơi học tập ẩn chứa 18 câu hỏi trong diễn biến của trò chơi. 
 <b>Nhiệm vụ của người tham gia cuộc thi là dựa trên thông tin ghi lại trong quá trình chơi của người chơi, dự đoán người chơi này có thể đoán đúng được câu hỏi ẩn chứa trong trò chơi hay không.</b>
* Mã nguồn gồm các file chính:
  - data_preparation.ipynb: file chuẩn bị tập dữ liệu từ tập huấn luyện gốc
  - lgbm_BO_hyperparams_tunning.ipynb: file chạy Bayesian Optimization cho tập dữ liệu đã chuẩn bị
  - lgbm_boruta_feature_selection.ipynb: file chạy Boruta Feature Selection cho tập dữ liệu đã chuẩn bị
  - lgbm_train_and_inference.ipynb: file submit kết quả lên kaggle (sau khi tải các file cần thiết lên kaggle)
  - lgbm_validation.ipynb: file chạy LightGBM loại bỏ feature
  - pre_eda.ipynb: file eda dữ liệu gốc
