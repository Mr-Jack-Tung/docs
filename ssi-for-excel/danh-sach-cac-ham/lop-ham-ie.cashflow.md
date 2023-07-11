---
description: Các hàm lấy thông tin từ báo cáo lưu chuyển tiền tệ
---

# Lớp hàm IE.CashFlow

## **Mô tả**

Các hàm thuộc nhóm này cho phép lấy 3 loại thông tin từ bảng LCTT:

* **Thông tin về bảng LCTT mới nhất:** Quý/Năm có bảng LCTT mới nhất (Year/Quarter), năm tài chính cuối có bảng LCTT năm
* **Chỉ tiêu tổng hợp mới nhất**: Một số hạng mục từ bảng LCTT quý cuối  hoặc năm gần nhất&#x20;
* **Toàn bộ Bảng LCTT**: Bảng LCTT của các năm hoặc quý đã nộp báo cáo                                                                         &#x20;

## Nhóm hàm lấy thông tin về bảng lưu chuyển tiền tệ mới nhất&#x20;

**Cú pháp**                                                                           &#x20;

Biểu thức lấy năm của bảng LCTT mới nhất của mã chứng khoán:

```
=IE.CashFlow.Year("Mã CK")
```

Biểu thức lấy quý và năm của bảng LCTT mới nhất của mã chứng khoán:&#x20;

```
=IE.CashFlow.Quarter("Mã CK")
```

**Trong đó:**

* **Mã CK:** là mã cổ phiếu niêm yết                                                                           &#x20;

## Nhóm hàm lấy các chỉ tiêu tổng hợp mới nhất từ bảng lưu chuyển tiền tệ

**Cú pháp**

Biểu thức lấy một chỉ tiêu tổng hợp mới nhất từ bảng LCTT**:**&#x20;

```
=FA.CashFlow.[Chỉ tiêu bảng CĐKT]("Mã CK", Năm báo cáo, Quý báo cáo) 
```

**Trong đó:**

* **Mã CK:** là mã cổ phiếu niêm yết
* **Năm báo cáo:** Năm hiển thị thông tin
* **Quý báo cáo:** Quý hiển thị thông tin. Quý I,II,III,IV tương ứng 1,2,3,4. Đặt bằng 5 nếu muốn lấy báo cáo theo năm
* **Chỉ tiêu bảng LCTT:** là một chỉ tiêu tương ứng trong bảng LCTT

**Ví dụ**

Để lấy giá trị lưu chuyển tiền tệ từ hoạt động tài chính năm 2022 quý 2 của mã SSI ta dùng công thức:&#x20;

```
=FA.CashFlow.CFF("SSI",2022,2)
```

## Hàm lấy toàn bộ bảng lưu chuyển tiền tệ

**Cú pháp**

Biểu thức lấy toàn bộ một hay nhiều bảng LCTT:&#x20;

```
=IE.CashFlow.Reports("Mã CK", Năm, Quý, Số lượng báo cáo) 
```

**Trong đó:**

* **Mã CK:** là mã cổ phiếu niêm yết&#x20;
* **Năm:** là năm tương ứng với bảng LCTT
* **Quý:** là quý tương ứng với báo cáo. Nếu Quý bằng 5 thì bảng LCTT là bảng LCTT năm&#x20;
* **Số lượng báo cáo:** là số bảng LCTT muốn lấy ra tính từ bảng LCTT ứng với các tham số Năm và Quý.&#x20;

**Ví dụ**

Để lấy 4 bảng LCTT theo quý, tính từ quý 2/2021 trở về trước của mã SSI, ta dùng công thức:

```
=IE.CashFlow.Reports("SSI", 2021, 2, 4)
```

{% hint style="info" %}
**Lưu ý**: do các loại hình doanh nghiệp khác nhau, nên có 1 số chỉ tiêu chỉ có ở loại hình doanh nghiệp này, mà không có ở các loại hình doanh nghiệp khác.
{% endhint %}

## IE.CashFlow.CFF

Lấy giá trị lưu chuyển tiền tệ từ hoạt động tài chính trong báo cáo Lưu chuyển tiền tệ

**Cú pháp**

```
=IE.CashFlow.CFF("Mã chứng khoán",Năm báo cáo, Quý báo cáo)
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin
* **Năm báo cáo:** Năm hiển thị thông tin
* **Quý báo cáo:** Quý hiển thị thông tin. Quý I,II,III,IV tương ứng 1,2,3,4. Đặt bằng 5 nếu muốn lấy báo cáo theo năm

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> giá trị lưu chuyển tiền tệ từ hoạt động tài chính trong báo cáo Lưu chuyển tiền tệ

**Ví dụ**

Bạn muốn biết giá trị lưu chuyển tiền tệ từ hoạt động tài chính của công ty SSI ở thời điểm quý 4 năm 2022, bạn dùng công thức

```
=IE.CashFlow.CFF("SSI",2022,4)
```

Hoặc gõ SSI ở một ô( ví dụ A1), năm báo cáo ở một ô(ví dụ A2), quý báo cáo ở một ô(ví dụ A3) và dùng công thức

```
=IE.CashFlow.CFF(A1,A2,A3)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán, năm báo cáo, quý báo cáo mà không cần gõ lại công thức

**Kết quả:**

2.671.613.358.430

## &#x20;IE.CashFlow.CFI

Lấy giá trị lưu chuyển tiền tệ ròng từ hoạt động đầu tư trong báo cáo Lưu chuyển tiền tệ

**Cú pháp**

```
=IE.CashFlow.CFI("Mã chứng khoán",Năm báo cáo, Quý báo cáo)
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin
* **Năm báo cáo:** Năm hiển thị thông tin
* **Quý báo cáo:** Quý hiển thị thông tin. Quý I,II,III,IV tương ứng 1,2,3,4. Đặt bằng 5 nếu muốn lấy báo cáo theo năm

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> giá trị lưu chuyển tiền tệ ròng từ hoạt động đầu tư trong báo cáo Lưu chuyển tiền tệ

**Ví dụ**

Bạn muốn biết giá trị lưu chuyển tiền tệ ròng từ hoạt động đầu tư của công ty SSI ở thời điểm quý 4 năm 2022, bạn dùng công thức

```
=IE.CashFlow.CFI("SSI",2022,4)
```

Hoặc gõ SSI ở một ô( ví dụ A1), năm báo cáo ở một ô(ví dụ A2), quý báo cáo ở một ô(ví dụ A3) và dùng công thức

```
=IE.CashFlow.CFI(A1,A2,A3)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán, năm báo cáo, quý báo cáo mà không cần gõ lại công thức

**Kết quả:**

2.671.613.358.430

## IE.CashFlow.CFO

Lấy giá trị lưu chuyển tiền tệ ròng từ các hoạt động sản xuất kinh doanh trong báo cáo Lưu chuyển tiền tệ

**Cú pháp**

```
=IE.CashFlow.CFO("Mã chứng khoán",Năm báo cáo, Quý báo cáo)
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin
* **Năm báo cáo:** Năm hiển thị thông tin
* **Quý báo cáo:** Quý hiển thị thông tin. Quý I,II,III,IV tương ứng 1,2,3,4. Đặt bằng 5 nếu muốn lấy báo cáo theo năm

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> giá trị lưu chuyển tiền tệ ròng từ các hoạt động sản xuất kinh doanh trong báo cáo Lưu chuyển tiền tệ

**Ví dụ**

Bạn muốn biết giá trị lưu chuyển tiền tệ ròng từ các hoạt động sản xuất kinh doanh của công ty SSI ở thời điểm quý 4 năm 2022, bạn dùng công thức

```
=IE.CashFlow.CFO("SSI",2022,4)
```

Hoặc gõ SSI ở một ô( ví dụ A1), năm báo cáo ở một ô(ví dụ A2), quý báo cáo ở một ô(ví dụ A3) và dùng công thức

```
=IE.CashFlow.CFO(A1,A2,A3)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán, năm báo cáo, quý báo cáo mà không cần gõ lại công thức

**Kết quả:**

2.671.613.358.430

## IE.CashFlow.DepreciationAmortisation

Lấy giá trị Khấu hao TSCĐ trong báo cáo lưu chuyển tiền tệ

**Cú pháp**

```
=IE.CashFlow.DepreciationAmortisation("Mã chứng khoán",Năm báo cáo, Quý báo cáo)
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin
* **Năm báo cáo:** Năm hiển thị thông tin
* **Quý báo cáo:** Quý hiển thị thông tin. Quý I,II,III,IV tương ứng 1,2,3,4. Đặt bằng 5 nếu muốn lấy báo cáo theo năm

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> giá trị Khấu hao TSCĐ trong báo cáo Lưu chuyển tiền tệ

**Ví dụ**

Bạn muốn biết giá trị Khấu hao TSCĐ của công ty SSI ở thời điểm quý 4 năm 2022, bạn dùng công thức

```
=IE.CashFlow.DepreciationAmortisation("SSI",2022,4)
```

Hoặc gõ SSI ở một ô( ví dụ A1), năm báo cáo ở một ô(ví dụ A2), quý báo cáo ở một ô(ví dụ A3) và dùng công thức

```
=IE.CashFlow.DepreciationAmortisation(A1,A2,A3)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán, năm báo cáo, quý báo cáo mà không cần gõ lại công thức

**Kết quả:**

2.671.613.358.430

## IE.CashFlow.DividendsPaid

Lấy giá trị Cổ tức đã trả trong báo cáo lưu chuyển tiền tệ

**Cú pháp**

```
=IE.CashFlow.DividendsPaid("Mã chứng khoán",Năm báo cáo, Quý báo cáo)
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin
* **Năm báo cáo:** Năm hiển thị thông tin
* **Quý báo cáo:** Quý hiển thị thông tin. Quý I,II,III,IV tương ứng 1,2,3,4. Đặt bằng 5 nếu muốn lấy báo cáo theo năm

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> giá trị Cổ tức đã trả trong báo cáo Lưu chuyển tiền tệ

**Ví dụ**

Bạn muốn biết giá trị Cổ tức đã trả của công ty SSI ở thời điểm quý 4 năm 2022, bạn dùng công thức

```
=IE.CashFlow.DividendsPaid("SSI",2022,4)
```

Hoặc gõ SSI ở một ô( ví dụ A1), năm báo cáo ở một ô(ví dụ A2), quý báo cáo ở một ô(ví dụ A3) và dùng công thức

```
=IE.CashFlow.DividendsPaid(A1,A2,A3)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán, năm báo cáo, quý báo cáo mà không cần gõ lại công thức

**Kết quả:**

2.671.613.358.430

## IE.CashFlow.InterestExpense

Lấy giá trị Chi phí lãi vay trong báo cáo lưu chuyển tiền tệ

**Cú pháp**

```
=IE.CashFlow.InterestExpense("Mã chứng khoán",Năm báo cáo, Quý báo cáo)
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin
* **Năm báo cáo:** Năm hiển thị thông tin
* **Quý báo cáo:** Quý hiển thị thông tin. Quý I,II,III,IV tương ứng 1,2,3,4. Đặt bằng 5 nếu muốn lấy báo cáo theo năm

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> giá trị Chi phí lãi vay trong báo cáo Lưu chuyển tiền tệ

**Ví dụ**

Bạn muốn biết giá trị Chi phí lãi vay của công ty SSI ở thời điểm quý 4 năm 2022, bạn dùng công thức

```
=IE.CashFlow.InterestExpense("SSI",2022,4)
```

Hoặc gõ SSI ở một ô( ví dụ A1), năm báo cáo ở một ô(ví dụ A2), quý báo cáo ở một ô(ví dụ A3) và dùng công thức

```
=IE.CashFlow.InterestExpense(A1,A2,A3)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán, năm báo cáo, quý báo cáo mà không cần gõ lại công thức

**Kết quả:**

2.671.613.358.430

## IE.CashFlow.InterestPaid

Lấy giá trị Chi phí lãi vay đã trả trong báo cáo lưu chuyển tiền tệ

**Cú pháp**

```
=IE.CashFlow.InterestPaid("Mã chứng khoán",Năm báo cáo, Quý báo cáo)
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin
* **Năm báo cáo:** Năm hiển thị thông tin
* **Quý báo cáo:** Quý hiển thị thông tin. Quý I,II,III,IV tương ứng 1,2,3,4. Đặt bằng 5 nếu muốn lấy báo cáo theo năm

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> giá trị Chi phí lãi vay đã trả trong báo cáo Lưu chuyển tiền tệ

**Ví dụ**

Bạn muốn biết giá trị Chi phí lãi vay đã trả của công ty SSI ở thời điểm quý 4 năm 2022, bạn dùng công thức

```
=IE.CashFlow.InterestPaid("SSI",2022,4)
```

Hoặc gõ SSI ở một ô( ví dụ A1), năm báo cáo ở một ô(ví dụ A2), quý báo cáo ở một ô(ví dụ A3) và dùng công thức

```
=IE.CashFlow.InterestPaid(A1,A2,A3)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán, năm báo cáo, quý báo cáo mà không cần gõ lại công thức

**Kết quả:**

2.671.613.358.430

## IE.CashFlow.Provisions

Lấy giá trị Chi phí dự phòng trong báo cáo lưu chuyển tiền tệ

**Cú pháp**

```
=IE.CashFlow.Provisions("Mã chứng khoán",Năm báo cáo, Quý báo cáo)
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin
* **Năm báo cáo:** Năm hiển thị thông tin
* **Quý báo cáo:** Quý hiển thị thông tin. Quý I,II,III,IV tương ứng 1,2,3,4. Đặt bằng 5 nếu muốn lấy báo cáo theo năm

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> giá trị Chi phí dự phòng trong báo cáo Lưu chuyển tiền tệ

**Ví dụ**

Bạn muốn biết giá trị Chi phí dự phòng của công ty SSI ở thời điểm quý 4 năm 2022, bạn dùng công thức

```
=IE.CashFlow.Provisions("SSI",2022,4)
```

Hoặc gõ SSI ở một ô( ví dụ A1), năm báo cáo ở một ô(ví dụ A2), quý báo cáo ở một ô(ví dụ A3) và dùng công thức

```
=IE.CashFlow.Provisions(A1,A2,A3)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán, năm báo cáo, quý báo cáo mà không cần gõ lại công thức

**Kết quả:**

2.671.613.358.430

## IE.CashFlow.Quarter

Lấy quý và năm có báo cáo lưu chuyển tiền tệ gần nhất

**Cú pháp**

```
=IE.CashFlow.Quarter("Mã chứng khoán")
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> Hiển thị quý và năm có báo cáo bảng cân đối kế toán gần nhất của doanh nghiệp

**Ví dụ**

Bạn muốn biết quý và năm có báo cáo bảng cân đối kế toán gần nhất của công ty SSI, bạn dùng công thức

```
=IE.CashFlow.Quarter("SSI")
```

Hoặc gõ SSI ở một ô( ví dụ A1) và dùng công thức

```
=IE.CashFlow.Quarter(A1)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán mà không cần gõ lại công thức

**Kết quả:**

Q4/2022

## IE.CashFlow.Reports

Hiển thị báo cáo lưu chuyển tiền tệ của doanh nghiệp

**Cú pháp**

```
=IE.CashFlow.Reports("Mã chứng khoán",Năm báo cáo, Quý báo cáo,Số lượng báo cáo)
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin
* **Năm báo cáo:** Năm cuối cùng hiển thị báo cáo
* **Quý báo cáo:** Quý cuối cùng hiển thị báo cáo. Quý I,II,III,IV tương ứng 1,2,3,4. Đặt bằng 5 nếu muốn lấy báo cáo theo năm
* **Số lượng báo cáo:** Số lượng báo cáo lấy về

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> báo cáo lưu chuyển tiền tệ của doanh nghiệp

**Ví dụ**

Bạn muốn hiển thị báo cáo lưu chuyển tiền tệ của công ty SSI từ quý 2 năm 2022 trở về với số lượng 3 báo cáo , bạn dùng công thức

```
=IE.CashFlow.Reports("SSI",2022,2,3)
```

Hoặc gõ SSI ở một ô( ví dụ A1), năm báo cáo ở một ô(ví dụ A2), quý báo cáo ở một ô(ví dụ A3), số lượng báo cáo lấy về ở một ô(ví dụ A3) và dùng công thức

```
=IE.CashFlow.Reports(A1,A2,A3,A4)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán, năm báo cáo, quý báo cáo, số lượng báo cáo lấy về mà không cần gõ lại công thức

## IE.CashFlow.TaxPaid

Lấy giá trị Thuế thu nhập doanh nghiệp đã trả trong báo cáo lưu chuyển tiền tệ

**Cú pháp**

```
=IE.CashFlow.TaxPaid("Mã chứng khoán",Năm báo cáo, Quý báo cáo)
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin
* **Năm báo cáo:** Năm hiển thị thông tin
* **Quý báo cáo:** Quý hiển thị thông tin. Quý I,II,III,IV tương ứng 1,2,3,4. Đặt bằng 5 nếu muốn lấy báo cáo theo năm

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> giá trị Thuế thu nhập doanh nghiệp đã trả trong báo cáo Lưu chuyển tiền tệ

**Ví dụ**

Bạn muốn biết giá trị Thuế thu nhập doanh nghiệp đã trả của công ty SSI ở thời điểm quý 4 năm 2022, bạn dùng công thức

```
=IE.CashFlow.TaxPaid("SSI",2022,4)
```

Hoặc gõ SSI ở một ô( ví dụ A1), năm báo cáo ở một ô(ví dụ A2), quý báo cáo ở một ô(ví dụ A3) và dùng công thức

```
=IE.CashFlow.TaxPaid(A1,A2,A3)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán, năm báo cáo, quý báo cáo mà không cần gõ lại công thức

## IE.CashFlow.Year

Lấy năm có báo cáo bảng cân đối kế toán gần nhất

**Cú pháp**

```
=IE.CashFlow.Year("Mã chứng khoán")
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> năm có báo cáo lưu chuyển tiền tệ gần nhất

**Ví dụ**

Bạn muốn biết năm gần nhất có báo cáo lưu chuyển tiền tệ của công ty SSI, bạn dùng công thức

```
=IE.CashFlow.Year("SSI")
```

Hoặc gõ SSI ở một ô( ví dụ A1) và dùng công thức

```
=IE.CashFlow.Year(A1)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán mà không cần gõ lại công thức

**Kết quả:**

2022
