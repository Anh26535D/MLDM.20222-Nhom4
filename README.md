# Predict Student Performance from Game Play
[Competition link](https://www.kaggle.com/competitions/predict-student-performance-from-game-play/overview)

## Description

Learning through games is an educational method that allows students to interact with educational content within the framework of a game, making the content interesting and dynamic. Although game-based learning is increasingly used in educational environments, there are still limited open datasets available for applying data science and learning analysis principles to improve game-based learning. Most game-based learning platforms do not fully harness the potential of knowledge tracing to support each student. Knowledge tracing methods have been developed and researched in the context of online learning environments and intelligent tutoring systems, but there has been little focus on knowledge tracing in educational games.

Therefore, Field Day Lab, a publicly funded research laboratory at the Wisconsin Center for Education Research, along with The Learning Agency Lab, organizes this competition on Kaggle with the goal of using machine learning models to predict students' performance in games. This aims to help developers improve their game-based learning platforms.

The game named Jo Wilder is a hidden educational game containing 18 questions within its gameplay. **Participants' task in the competition is to predict whether a player can correctly answer the hidden questions in the game based on the recorded information during the player's gameplay.**


## Prerequisites
 - Python 3.9 or later.

## Installation
1. **Clone project**
  ```
    git clone 
  ```
2. **Install python libraries**
  ```
    pip install -r requirements.txt
  ```

## File structure
  - data_preparation.ipynb: file chuẩn bị tập dữ liệu từ tập huấn luyện gốc
  - lgbm_BO_hyperparams_tunning.ipynb: file chạy Bayesian Optimization cho tập dữ liệu đã chuẩn bị
  - lgbm_boruta_feature_selection.ipynb: file chạy Boruta Feature Selection cho tập dữ liệu đã chuẩn bị
  - lgbm_train_and_inference.ipynb: file submit kết quả lên kaggle (sau khi tải các file cần thiết lên kaggle)
  - lgbm_validation.ipynb: file chạy LightGBM loại bỏ feature
  - pre_eda.ipynb: file eda dữ liệu gốc
* Thứ tự chạy file (chú ý các file csv ở đây không đảm bảo chạy sẽ ra y hệt do tính ngẫu nhiên của BO và BORUTA, các file chỉ là file được sử dụng để submit cuối cùng lên cuộc thi - trừ file hyperparams_tunning.csv với lí do bên dưới)
  - data_preparation.ipynb sẽ sinh ra 3 file huấn luyện pickle gồm train_0_4.pkl, train_13_22.pkl, train_5_12.pkl
  - lgbm_validation.ipynb sẽ sinh ra 1 file FEATURES_Q.csv, đây là file chứa các đặc trưng sẽ sử dụng cho bước tiếp theo
  - lgbm_boruta_feature_selection.ipynb lấy các đặc trưng từ FEATURES_Q.csv, sau đó chạy sẽ được bộ đặc trưng lọc lượt 2 (chú ý code hiện tại chưa save tự động lại mà chỉ in ra, do đó tạm thời cần copy thủ công) ra file BORUTA_FEATURES.csv
  - lgbm_BO_hyperparams_tunning.ipynb lấy file FEATURES_Q.csv để sinh ra tham số (chú ý code hiện tại chưa save tự động format chuẩn, do đó cần tự chỉnh lại format file sinh ra thủ công) ở file hyperparams_tunning.csv. Sau đó, cần dựa vào bộ tham số tùy chỉnh bằng tay cũ (đã có sẵn ở các file) để tinh chỉnh lại các tham số thủ công 1 lần nữa cho từng câu hỏi (18 câu hỏi), chú ý BO không đảm bảo sinh ra cùng 1 bộ tham số cho các lần chạy khác nhau.
  - lgbm_train_and_inference.ipynb. file này cần được sử dụng trên kaggle. Vào trang chủ của cuộc thi theo đường dẫn bên trên, chọn new note book, sau đó upload file này lên. Ngoài ra, cần upload các file huấn luyện pickle ở bước 1, file BORUTA_FEATURES.csv ở bước 3, và file hyperparams_tunning.csv ở bước 4 (tùy chọn có thể không dùng, do vấn đề thời gian, nhóm chưa dùng bộ tham số này để submit được, mà mới chỉ dùng đặc trưng từ BORUTA).

## Contributors
* Đàm Việt Anh - 20204627 - anh.dv204627@sis.hust.edu.vn
* Vũ Việt Anh - 20200053 - anh.vv200053@sis.hust.edu.vn
* Phạm Quang Minh - 20204588 - minh.pq204588@sis.hust.edu.vn
* Nguyễn Trung Hiếu - 20204551 - hieu.nt204551@sis.hust.edu.vn
* Trịnh Quang Quân - 20200511 - quan.tq20200511@sis.hust.edu.vn
