## Tổng quan
Domain API: https://admin.365ok.vn/ <br/>
Giao thức: HTTP POST (Form-Data), HTTP GET <br/>
Kết quả trả về: 
+ Status:200 => Thành công <br/>
+ Status: != 200 => Thông báo lỗi qua field message. <br/>

* Mô tả chung:<br/>
```
'page' => Kiểu int là số trang 
'limit' => Số bản ghi hiển thị trên mỗi trang
'q' => Chuỗi tìm kiếm theo tên ...
'status' => Trạng thái ...
```
**Tất cả các API khi gọi lên đều kèm theo tham số**
```
app_token = 36501|da3c4c5f57018e3c0cf004efb26ffc87,
website_id = 'int'
```

-----------------------
### 1. Customer(Chi tiết khách hàng)

*Mô tả: Lấy ra thông tin chi tiết của khách hàng

* Tham số truyền vào: GET

* Link : /api/customer/{id:[0-9]+}
```php
[
    "id"=>"int"
]
```

* Trả về: Object Json
```json
{
  "data": {
  },
  "status": 200,
  "message": "success"
}
```
-----------------------
### 2. Order(Danh sách đơn hàng)

*Mô tả: Lấy ra danh sách đơn hàng của khách hàng đó

* Tham số truyền vào: GET

* Link : /api/order
```php
[     
    'customer_id' => 'int' (ID khách hàng)
]
```

* Trả về: Object Json
```json
{
  "data": {
  },
  "status": 200,
  "message": "success"
}
```
