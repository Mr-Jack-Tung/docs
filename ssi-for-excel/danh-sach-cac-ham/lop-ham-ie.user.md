---
description: >-
  Các hàm lấy thông tin tiểu khoản, danh mục chứng khoán, watchlist của tài
  khoản
---

# Lớp hàm IE.User

## IE.User.Accounts

Lấy danh sách tài khoản

**Cú pháp**

```
=IE.User.Accounts()
```

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> danh sách các tiểu khoản của tài khoản mà bạn đang đăng nhập iExcel

## IE.User.Portfolios

Lấy danh mục chứng khoán đang nắm giữ

**Cú pháp**

```
=IE.User.Portfolios("Tài khoản")
```

**Trong đó:**

* **Tài khoản:** Tiểu khoản của tài khoản đang đăng nhập iExcel cần lấy thông tin

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> thông tin danh mục chứng khoán đang nắm giữ của tiểu khoản

## IE.User.WatchList

Lấy danh sách watchlist

**Cú pháp**

```
=IE.User.WatchList()
```

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> danh sách WatchList của tài khoản đang đăng nhập iExcel

## IE.User.WatchListDetail

Lấy danh sách mã chứng khoán của watchlist

**Cú pháp**

```
=IE.User.WatchListDetail("Tên danh mục")
```

**Trong đó:**

* **Tên danh mục:** Tên danh mục của tài khoản đang đăng nhập iExcel, được lấy ra thông tin từ hàm IE.User.WatchList

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> thông tin danh mục chứng khoán trong danh mục
