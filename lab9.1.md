# [Bài toán: Animal Race](https://www.notion.so/B-i-to-n-Animal-Race-e7be36b366fd43d998b9b06535ae8853)
Credit: [Nguyen Thinh Khang](https://github.com/thinhkhang97)

---
Trong 1 khu rừng nọ, vào mua Thu hằng năm đều tổ chức 1 cuộc đua thú. Chỉ có những **động vật 4 chân** mới có thể tham gia cuộc đua này. Mỗi con vật sẽ có tốc độ chạy ngẫu nhiên và khác nhau. Năm nay có 3 giống loài được tham gia cuộc đua là **Tiger, Elephant và Horse**. Trong quá trình cuộc thi được tổ chức, sẽ có 1 phần thi dành cho khán giả, khán giả sẽ đoán xem loài nào sẽ là quán quân năm nay. Là một lập trình viên, bạn hãy thiết kế 1 chương trình giả lập cuộc đua để đoán xem loài nào sẽ vô địch năm nay. Tốc độ (m/s) của các loài vật được mô tả bên dưới.

- Tiger: Tốc độ (S) phụ thuộc vào cân nặng (W) theo tỉ lệ 0.06, cân nặng trung bình của 1 con tiger dao động từ 250 - 400 kg
- Elephant: Tốc độ (S) tỉ lệ thuận với chiều dài sải chân (T) theo tỉ lệ 6.0, sải chân của 1 con voi dao động từ 3-4m
- Horse: Tốc độ của ngựa dao động từ 15-24m/s.

Mỗi cuộc đua, mỗi loài sẽ cử 2 đại diện tham gia, các con vật sẽ chạy cùng lúc và cùng 1 điểm xuất phát, độ dài đường đua là 10km, chỉ cần 1 con của loài dành chiến thắng thì cả loài sẽ thắng.

Để tăng khả năng chính xác, chương trình của bạn sẽ phải chạy giả lập nhiều lần để kết quả gần đúng nhất. Do đó tính năng giả lập cuộc sẽ phải chạy ít nhất 10 lần và loài nào có số lần thắng nhiều nhất sẽ là loài được chọn.