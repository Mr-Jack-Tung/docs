---
description: >-
  Tập hợp các hàm lấy thông tin liên quan đến giao dịch nước ngoài của mã cổ
  phiếu trong quá khứ
---

# Lớp hàm IE.Foreign

## **Cú pháp**

```
=IE.EOD.[Trường thông tin]("Mã CK hoặc Mã Index")
```

**Trong đó:**

* **Mã CK:** là mã của những chứng khoán niêm yết
* **Mã Index:** là tên Index tương ứng, ví dụ: VNINDEX, HNXINDEX, UPINDEX, VN30, HNX30, …&#x20;
* **Trường thông tin:** là tên trường tương ứng với một thông tin nhất định về Index hoặc thị trường phiên hiện tại"

## **Ví dụ**

Muốn xem giá đóng cửa trong các ngày giao dịch của mã SSI trong khoảng thời gian từ ngày 11/04/2023 đến ngày 21/04/2023 ta dùng công thức:&#x20;

```
=IE.EOD.Close("SSI","11/04/2023","21/04/2023") 
```

Muốn xem giá cao nhất trong các ngày giao dịch của mã SSI trong khoảng thời gian từ ngày 11/04/2023 đến ngày 21/04/2023 ta dùng công thức:

```
=IE.EOD.High("SSI","11/04/2023","21/04/2023")
```

## IE.Foreign.BuyValue

Lấy giá trị nước ngoài mua của 1 mã hoặc index trong 1 khoảng thời gian

**Cú pháp**

```
=IE.Foreign.BuyValue("Mã CK", "Ngày bắt đầu", "Ngày kết thúc")
```

**Trong đó**:

* **Mã CK:** Mã chứng khoán cần lấy thông tin hoặc index (VNINDEX, HNXINDEX, UPINDEX, VN30, HNX30,...)&#x20;
* **Ngày bắt đầu**: Ngày bắt đầu lấy dữ liệu, định dạng "dd/MM/yyyy"
* **Ngày kết thúc:** Ngày kết thúc lấy dữ liệu, định dạng "dd/MM/yyyy"

**Giá trị trả về:**

Một chuỗi các giá trị trong đó mỗi phần tử là giá trị nước ngoài mua ứng với 1 ngày giao dịch trong khoảng thời gian.

## IE.Foreign.BuyVolume

Lấy khối lượng nước ngoài mua của 1 mã hoặc index trong 1 khoảng thời gian

**Cú pháp**

```
=IE.Foreign.BuyVolume("Mã CK", "Ngày bắt đầu", "Ngày kết thúc")
```

**Trong đó**:

* **Mã CK:** Mã chứng khoán cần lấy thông tin hoặc index (VNINDEX, HNXINDEX, UPINDEX, VN30, HNX30,...)&#x20;
* **Ngày bắt đầu**: Ngày bắt đầu lấy dữ liệu, định dạng "dd/MM/yyyy"
* **Ngày kết thúc:** Ngày kết thúc lấy dữ liệu, định dạng "dd/MM/yyyy"

**Giá trị trả về:**

Một chuỗi các giá trị trong đó mỗi phần tử là khối lượng nước ngoài mua ứng với 1 ngày giao dịch trong khoảng thời gian.

## IE.Foreign.SellValue

Lấy giá trị nước ngoài bán của 1 mã hoặc index trong 1 khoảng thời gian

**Cú pháp**

```
=IE.Foreign.SellValue("Mã CK", "Ngày bắt đầu", "Ngày kết thúc")
```

**Trong đó**:

* **Mã CK:** Mã chứng khoán cần lấy thông tin hoặc index (VNINDEX, HNXINDEX, UPINDEX, VN30, HNX30,...)&#x20;
* **Ngày bắt đầu**: Ngày bắt đầu lấy dữ liệu, định dạng "dd/MM/yyyy"
* **Ngày kết thúc:** Ngày kết thúc lấy dữ liệu, định dạng "dd/MM/yyyy"

**Giá trị trả về:**

Một chuỗi các giá trị trong đó mỗi phần tử là giá trị nước ngoài bán ứng với 1 ngày giao dịch trong khoảng thời gian.

## IE.Foreign.SellVolume

Lấy khối lượng nước ngoài bán của 1 mã hoặc index trong 1 khoảng thời gian

**Cú pháp**

```
=IE.Foreign.SellVolume("Mã CK", "Ngày bắt đầu", "Ngày kết thúc")
```

**Trong đó**:

* **Mã CK:** Mã chứng khoán cần lấy thông tin hoặc index (VNINDEX, HNXINDEX, UPINDEX, VN30, HNX30,...)&#x20;
* **Ngày bắt đầu**: Ngày bắt đầu lấy dữ liệu, định dạng "dd/MM/yyyy"
* **Ngày kết thúc:** Ngày kết thúc lấy dữ liệu, định dạng "dd/MM/yyyy"

**Giá trị trả về:**

Một chuỗi các giá trị trong đó mỗi phần tử là khối lượng nước ngoài bán ứng với 1 ngày giao dịch trong khoảng thời gian.

## IE.Foreign.TradingDate

Lấy ngày giao dịch của 1 mã hoặc index trong 1 khoảng thời gian

**Cú pháp**

```
=IE.Foreign.TradingDate("Mã CK", "Ngày bắt đầu", "Ngày kết thúc")
```

**Trong đó**:

* **Mã CK:** Mã chứng khoán cần lấy thông tin hoặc index (VNINDEX, HNXINDEX, UPINDEX, VN30, HNX30,...)&#x20;
* **Ngày bắt đầu**: Ngày bắt đầu lấy dữ liệu, định dạng "dd/MM/yyyy"
* **Ngày kết thúc:** Ngày kết thúc lấy dữ liệu, định dạng "dd/MM/yyyy"

**Giá trị trả về:**

Một chuỗi các giá trị trong đó mỗi phần tử là ứng với 1 ngày giao dịch trong khoảng thời gian.
