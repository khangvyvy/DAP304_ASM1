# Phân tích bài thi
## Mô tả
Đây là một công cụ đơn giản cho phép bạn phân tích kết quả của các bài thi dựa trên một bảng điểm được cung cấp và các câu trả lời của sinh viên. Công cụ này sẽ giúp bạn:

* Xác định số lượng học sinh hợp lệ và không hợp lệ.
* Tính toán điểm trung bình, điểm cao nhất và thấp nhất.
* Xác định số lượng học sinh đạt điểm cao (ví dụ: trên 80 điểm).
* Phân tích các câu hỏi được bỏ qua nhiều nhất và câu hỏi mà học sinh trả lời sai nhiều nhất.
* Lưu kết quả phân tích vào một tệp mới.
## Hướng dẫn sử dụng
**1. Cài đặt Jupyter Notebook:** Đảm bảo rằng bạn đã cài đặt Jupyter Notebook trên máy tính của mình.  
**2. Đặt tệp kết quả bài thi trắc nghiệm trong cùng thư mục với tệp Python.**  
**3. Mở tệp _DAP304_asm1_vynkFX231230@funix.edu.vn_ trong Jupyter Notebook và chạy mã.**  
**4. Nhập tên file:** Nhập tên file chứa bảng điểm và câu trả lời của sinh viên. Tên file là "class+ _số lớp_ + .txt".  
**Ví dụ:** class1.txt.  
**5. Xem kết quả:** Kết quả phân tích sẽ được hiển thị trên màn hình và được lưu vào một tệp mới có tên là class#_grades.txt.  

## Định dạng file đầu vào
* Bảng điểm và câu trả lời của sinh viên phải được lưu trong một file văn bản (.txt).
* Mỗi dòng đại diện cho một học sinh.
* Dòng đầu tiên là mã học sinh (8 chữ số bắt đầu bằng N).
* 25 dòng tiếp theo là câu trả lời của học sinh cho 25 câu hỏi trắc nghiệm (A, B, C, D hoặc bỏ qua bằng cách để trống).

## Giải thích mã
**Hàm** `find_most_skipped`:

* Tìm các câu hỏi bị bỏ qua nhiều nhất.
* Tham số:  
  - skipped_questions: Danh sách số lượng lần mỗi câu hỏi bị bỏ qua.  
  - line_count: Tổng số dòng hợp lệ trong tệp kết quả bài thi.  
* Trả về:  
  - Danh sách các câu hỏi bị bỏ qua nhiều nhất bao gồm:  
    - Số thứ tự câu hỏi.
    - Số lượng lần bị bỏ qua.  
    -  Tỷ lệ phần trăm bị bỏ qua.
    
**Hàm** `find_most_wrong`:

* Tìm các câu hỏi có nhiều câu trả lời sai nhất.
* Tham số:
  - wrong_answers: Danh sách số lượng lần mỗi câu hỏi có câu trả lời sai.
  - line_count: Tổng số dòng hợp lệ trong tệp kết quả bài thi.
* Trả về:
  - Danh sách các câu hỏi có nhiều câu trả lời sai nhất bao gồm:
     - Số thứ tự câu hỏi.
     - Số lượng câu trả lời sai.
     - Tỷ lệ phần trăm câu trả lời sai.
     
**Hàm** `analyze_file`:

* Phân tích tệp kết quả bài thi và hiển thị kết quả.
* Tham số:
  - file_name: Tên tệp kết quả bài thi.
* Hoạt động:
   - Mở tệp kết quả bài thi và kiểm tra lỗi.
   - Khởi tạo các biến để theo dõi số lượng bài thi hợp lệ và không hợp lệ, điểm số, v.v.
   - Lặp qua từng dòng trong tệp và xử lý câu trả lời của học sinh.
   - Tính toán các số liệu thống kê như điểm trung bình, điểm cao nhất, điểm thấp nhất, v.v.
   - Hiển thị kết quả phân tích trên dòng lệnh.
   - Ghi kết quả chi tiết (mã học sinh và điểm số) vào tệp _grades.txt trong cùng thư mục.
