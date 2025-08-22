### Mục Lục

* **Chương 1:** Hàm Phức và Biến Đổi Laplace
    * 1.1. Số Phức
    * 1.2. Nhân Tử $e^{j\phi}$ trong Phân Tích Tín Hiệu
    * 1.3. Hàm Biến Phức
    * 1.4. Phép Biến Đổi Laplace Thuận
    * 1.5. Các Tính Chất Cơ Bản của Biến Đổi Laplace
    * 1.6. Phép Biến Đổi Laplace Ngược
    * 1.7. Ứng Dụng của Phép Biến Đổi Laplace
    * 1.8. Bài Tập Chương 1
* **Chương 2:** Phương Trình Vi Phân
    * 2.1. Khái Niệm và Phân Loại Phương Trình Vi Phân
    * 2.2. Phương Trình Vi Phân Tuyến Tính Cấp 1
    * 2.3. Phương Trình Vi Phân Tuyến Tính Cấp 2 với Hệ Số Hằng
    * 2.4. Bài Tập Chương 2
* **Chương 3:** Giới Thiệu Về Lý Thuyết Xác Suất
    * 3.1. Phép Thử, Không Gian Mẫu, và Biến Cố
    * 3.2. Định Nghĩa và Tính Chất của Xác Suất
    * 3.3. Xác Suất Có Điều Kiện, Xác Suất Kết Hợp và Sự Kiện Độc Lập
    * 3.4. Công Thức Xác Suất Đầy Đủ và Định Lý Bayes
    * 3.5. Bài Tập Chương 3
* **Chương 4:** Biến Ngẫu Nhiên và Các Phân Bố
    * 4.1. Khái Niệm Biến Ngẫu Nhiên
    * 4.2. Biến Ngẫu Nhiên Rời Rạc
    * 4.3. Biến Ngẫu Nhiên Liên Tục
    * 4.4. Kỳ Vọng, Phương Sai và Các Tính Chất
    * 4.5. Các Phân Bố Xác Suất Thông Dụng
* **Chương 5:** Sử Dụng Phần Mềm Trong Mô Phỏng Quá Trình Ngẫu Nhiên
* **Chương 6:** Hàm Sinh Xác Suất
* **Chương 7:** Nhiều Biến Ngẫu Nhiên

***

### Chương 1: Hàm Phức và Biến Đổi Laplace

Mục tiêu: Cung cấp các kiến thức nền tảng về số phức, hàm biến phức và phép biến đổi Laplace, ứng dụng trong phân tích mạch điện tử và xử lý tín hiệu.

#### 1.1. Số Phức
Số phức là một phần mở rộng của số thực, được biểu diễn dưới dạng **$z=a+jb$**.
* **$a$** là phần thực (real part), **$b$** là phần ảo (imaginary part).
* **$j=\sqrt{-1}$** là đơn vị ảo, được dùng trong điện tử để tránh nhầm lẫn với dòng điện (i).

Số phức cũng có thể biểu diễn dưới dạng cực: **$z=re^{j\theta}$**.
* **$r=\sqrt{a^2+b^2}$** là mô-đun (độ lớn).
* **$\theta=tan^{-1}(b/a)$** là pha (góc).

#### 1.2. Nhân Tử $e^{j\phi}$ trong Phân Tích Tín Hiệu
Nhân tử này rất quan trọng trong phân tích tín hiệu dựa trên công thức Euler: **$e^{j\phi}=\cos\phi+j\sin\phi$**. Nó cho phép biểu diễn tín hiệu tuần hoàn dưới dạng phức, hữu ích trong lĩnh vực điện tử.
* Ý nghĩa: $e^{j\phi}$ biểu diễn sự dịch pha của tín hiệu.

#### 1.3. Hàm Biến Phức
Hàm biến phức $f(z)$ là hàm có biến $z$ là số phức ($z=x+jy$).
* Một hàm biến phức có thể tách thành phần thực $u(x,y)$ và phần ảo $v(x,y)$: **$f(z)=u(x,y)+jv(x,y)$**.
* **Điều kiện khả vi (Cauchy-Riemann)**: Hàm $f(z)$ khả vi nếu thỏa mãn: $\frac{\partial u}{\partial x} = \frac{\partial v}{\partial y}$ và $\frac{\partial u}{\partial y} = -\frac{\partial v}{\partial x}$.

#### 1.4. Phép Biến Đổi Laplace Thuận
Phép biến đổi Laplace chuyển đổi hàm thời gian $f(t)$ sang miền tần số phức $F(s)$.
* Định nghĩa: **$F(s)=\mathcal{L}\{f(t)\} = \int_{0}^{\infty} f(t)e^{-st} dt$**.
* Điều kiện tồn tại: $f(t)$ phải tuyệt đối hội tụ và giảm theo cấp số mũ.

#### 1.5. Các Tính Chất Cơ Bản của Biến Đổi Laplace
* **Tính Tuyến Tính:** $\mathcal{L}\{af(t)+bg(t)\} = aF(s)+bG(s)$.
* **Dịch Thời Gian:** $\mathcal{L}\{f(t-a)u(t-a)\} = e^{-as}F(s)$.
* **Dịch Tần Số:** $\mathcal{L}\{e^{at}f(t)\} = F(s-a)$.
* **Đạo Hàm:** $\mathcal{L}\{f'(t)\} = sF(s)-f(0)$.

#### 1.6. Phép Biến Đổi Laplace Ngược
Phép biến đổi Laplace ngược tìm hàm thời gian $f(t)$ từ $F(s)$.
* Phương pháp thực tế: Phân tích $F(s)$ thành phân thức riêng và sử dụng bảng biến đổi để tìm hàm $f(t)$ tương ứng.
    * **Ví dụ:** Tìm biến đổi Laplace ngược của $F(s) = \frac{1}{(s+1)(s+2)}$. Phân tích thành phân thức: $F(s) = \frac{A}{s+1} + \frac{B}{s+2}$. Giải ra $A=1, B=-1$. Vậy $f(t)=e^{-t}u(t)-e^{-2t}u(t)$.

#### 1.7. Ứng Dụng của Phép Biến Đổi Laplace
Phép biến đổi Laplace được dùng để phân tích mạch điện tử. Nó giúp chuyển phương trình vi phân mô tả mạch sang miền tần số, nơi phép toán trở nên đơn giản hơn.
* **Ví dụ:** Phân tích mạch RC bằng cách biến đổi phương trình vi phân sang miền Laplace, sau đó giải phương trình và biến đổi ngược để tìm đáp ứng thời gian.

#### 1.8. Bài Tập Chương 1
(Tham khảo các bài tập từ file "PP full.pdf").

***

### Chương 2: Phương Trình Vi Phân

Mục tiêu: Nắm vững các phương pháp giải phương trình vi phân tuyến tính cấp 1 và cấp 2, ứng dụng trong phân tích mạch điện và hệ thống điều khiển.

#### 2.1. Khái Niệm và Phân Loại Phương Trình Vi Phân
Phương trình vi phân là một phương trình chứa đạo hàm của một hàm số chưa biết.
* **Bậc:** là bậc cao nhất của đạo hàm trong phương trình.
* **Phân loại:**
    * **Theo loại đạo hàm:** Thông thường (ODE) - chỉ có một biến độc lập, hoặc Từng phần (PDE) - có nhiều biến độc lập.
    * **Theo tính tuyến tính:** Tuyến tính (không chứa lũy thừa hay tích của hàm và đạo hàm) hoặc Phi tuyến.
    * **Theo tính thuần nhất:** Thuần nhất (vế phải = 0) hoặc Không thuần nhất (vế phải ≠ 0).
* **Ứng dụng:** Mô tả mối quan hệ giữa điện áp, dòng điện trong mạch RC, RL, RLC.

#### 2.2. Phương Trình Vi Phân Tuyến Tính Cấp 1
Phương trình có dạng tổng quát: $\frac{dy}{dx} + P(x)y = Q(x)$.
* **Phương pháp giải:** Sử dụng **nhân tử tích phân** $\mu(x)=e^{\int P(x)dx}$.
* **Các bước giải:**
    1.  Tìm nhân tử tích phân $\mu(x)$.
    2.  Nhân cả hai vế của phương trình với $\mu(x)$.
    3.  Tích phân hai vế để tìm nghiệm.
    4.  Sử dụng điều kiện ban đầu (nếu có) để tìm hằng số.

#### 2.3. Phương Trình Vi Phân Tuyến Tính Cấp 2 với Hệ Số Hằng
Phương trình có dạng tổng quát: $ay'' + by' + cy = g(x)$.

**2.3.1. Phương Trình Thuần Nhất ($g(x)=0$)**
* **Phương pháp giải:** Sử dụng **phương trình đặc trưng** $ar^2+br+c=0$.
* **Nghiệm tổng quát:**
    * Hai nghiệm phân biệt $r_1, r_2$: $y=C_1e^{r_1x}+C_2e^{r_2x}$.
    * Nghiệm kép $r_1=r_2=r$: $y=(C_1+C_2x)e^{rx}$.
    * Nghiệm phức $r=\alpha\pm j\beta$: $y=e^{\alpha x}(C_1\cos(\beta x)+C_2\sin(\beta x))$.

**2.3.2. Phương Trình Không Thuần Nhất ($g(x)\ne 0$)**
* **Nghiệm tổng quát:** $y=y_h+y_p$.
    * $y_h$ là nghiệm của phương trình thuần nhất (đã giải ở trên).
    * $y_p$ là nghiệm riêng, được tìm bằng **phương pháp hệ số bất định**.

#### 2.4. Bài Tập Chương 2
(Tham khảo các bài tập từ file "PP full.pdf").

***

### Chương 3: Giới Thiệu Về Lý Thuyết Xác Suất

Mục tiêu: Giới thiệu các khái niệm cơ bản về xác suất, bao gồm các định nghĩa, công thức và ứng dụng trong phân tích lỗi và tín hiệu điện tử.

#### 3.1. Phép Thử, Không Gian Mẫu, và Biến Cố
* **Phép thử:** Một hành động hoặc một thí nghiệm có thể lặp lại nhiều lần.
* **Không gian mẫu (S):** Tập hợp tất cả các kết quả có thể xảy ra của một phép thử.
* **Biến cố (A):** Một tập con của không gian mẫu S.

#### 3.2. Định Nghĩa và Tính Chất của Xác Suất
* **Định nghĩa:** Xác suất của biến cố A, ký hiệu $P(A)$, là thước đo khả năng biến cố đó xảy ra.
* **Tính chất:**
    * $0 \le P(A) \le 1$.
    * $P(S)=1$.
    * $P(A \cup B) = P(A) + P(B) - P(A \cap B)$.
    * **Biến cố bổ trợ:** $P(A^c) = 1 - P(A)$.

#### 3.3. Xác Suất Có Điều Kiện và Sự Kiện Độc Lập
* **Xác suất có điều kiện:** $P(A|B) = \frac{P(A \cap B)}{P(B)}$ (với $P(B)>0$).
* **Sự kiện độc lập:** Hai biến cố A và B độc lập nếu $P(A \cap B) = P(A)P(B)$.

#### 3.4. Công Thức Xác Suất Đầy Đủ và Định Lý Bayes
* **Công thức xác suất đầy đủ:** $P(A) = \sum_{i=1}^{n} P(A|B_i)P(B_i)$. Công thức này được dùng khi không gian mẫu được phân hoạch thành các biến cố $B_i$.
* **Định lý Bayes:** $P(B_i|A) = \frac{P(A|B_i)P(B_i)}{P(A)}$. Định lý này cho phép cập nhật xác suất của một sự kiện khi có thông tin mới.

#### 3.5. Bài Tập Chương 3
(Tham khảo các bài tập từ file "PP full.pdf").

***

### Chương 4: Biến Ngẫu Nhiên và Các Phân Bố

Mục tiêu: Hiểu về biến ngẫu nhiên, các đặc trưng thống kê như kỳ vọng và phương sai, và các phân bố xác suất thông dụng trong điện tử.

#### 4.1. Khái Niệm Biến Ngẫu Nhiên
Biến ngẫu nhiên là một hàm gán giá trị số cho mỗi kết quả của một phép thử ngẫu nhiên.
* **Biến ngẫu nhiên rời rạc:** Chỉ nhận các giá trị đếm được, ví dụ: số bit lỗi trong một gói tin.
* **Biến ngẫu nhiên liên tục:** Nhận các giá trị trong một khoảng liên tục, ví dụ: điện áp nhiễu trong mạch.

#### 4.2. Biến Ngẫu Nhiên Rời Rạc
* **Hàm khối xác suất (PMF):** $p(x) = P(X=x)$, mô tả xác suất mỗi giá trị rời rạc xảy ra.

#### 4.3. Biến Ngẫu Nhiên Liên Tục
* **Hàm mật độ xác suất (PDF):** $f(x)$, thỏa mãn $\int_{-\infty}^{\infty} f(x) dx=1$.

#### 4.4. Kỳ Vọng và Phương Sai
* **Kỳ vọng (E[X]):** Giá trị trung bình của biến ngẫu nhiên.
* **Phương sai (Var[X]):** Đo lường mức độ phân tán của các giá trị so với kỳ vọng.

#### 4.5. Các Phân Bố Xác Suất Thông Dụng
* **Phân bố Bernoulli:** Dùng cho các phép thử chỉ có hai kết quả (thành công/thất bại).
* **Phân bố Uniform:** Tất cả các giá trị đều có xác suất như nhau.
* **Phân bố Binomial:** Số lần thành công trong một loạt phép thử độc lập.
* **Phân bố Gaussian (Chuẩn):** Phân bố quan trọng nhất, mô tả nhiều hiện tượng tự nhiên và kỹ thuật, đặc biệt là nhiễu trong hệ thống điện tử.

***

### Chương 5: Sử Dụng Phần Mềm trong Mô Phỏng Quá Trình Ngẫu Nhiên

Mục tiêu: Hiểu cách sử dụng phần mềm (như MATLAB hoặc Python) để mô phỏng và phân tích các quá trình ngẫu nhiên.
* **Tạo mẫu ngẫu nhiên:** Sử dụng các hàm tích hợp trong phần mềm để tạo ra các mẫu tuân theo một phân bố xác suất cụ thể (ví dụ: `randn` để tạo mẫu nhiễu Gauss).
* **Thu thập kết quả:** Mô phỏng các quá trình thực tế như kênh truyền, tính toán BER (Bit Error Rate).
* **Vẽ đồ thị:** Sử dụng biểu đồ tần suất (histogram) để ước lượng hàm PDF thực nghiệm và so sánh với lý thuyết. Sử dụng biểu đồ CDF và QQ-plot để kiểm tra tính đúng đắn của mô hình. 

***

### Chương 6: Hàm Sinh Xác Suất

Mục tiêu: Nắm vững khái niệm và ứng dụng của hàm sinh xác suất.
* **Hàm sinh mô-men (MGF):** Là một công cụ toán học để tìm kỳ vọng và phương sai của một biến ngẫu nhiên.
* **Hàm đặc trưng:** Là một phiên bản phức của hàm sinh mô-men, luôn tồn tại và hữu ích cho biến ngẫu nhiên liên tục.

***

### Chương 7: Nhiều Biến Ngẫu Nhiên

Mục tiêu: Hiểu cách mô tả và xử lý các mô hình có nhiều biến ngẫu nhiên, áp dụng trong phân tích tín hiệu đa chiều và hệ thống phức tạp.
* **Véc-tơ ngẫu nhiên:** Một tập hợp các biến ngẫu nhiên, ví dụ: nhiệt độ, độ ẩm và áp suất đo được bởi cảm biến thời tiết.
* **Phân phối đồng thời:** Mô tả xác suất (hoặc mật độ) mà nhiều biến ngẫu nhiên cùng nhận các giá trị cụ thể.
* **Các đặc trưng thống kê:**
    * **Ma trận hiệp phương sai:** Mô tả sự biến thiên và mối quan hệ tuyến tính giữa các biến ngẫu nhiên.
    * **Hệ số tương quan:** Đo lường mức độ phụ thuộc tuyến tính giữa hai biến.
* **Định lý giới hạn trung tâm (CLT):** Khi kích thước mẫu đủ lớn, phân phối của trung bình mẫu sẽ xấp xỉ phân phối chuẩn, bất kể phân phối ban đầu của biến ngẫu nhiên là gì. Định lý này rất quan trọng trong thống kê và xử lý tín hiệu.

***
