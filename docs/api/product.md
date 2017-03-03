## Tổng quan
Domain API: https://admin.365ok.vn/ <br/>
Giao thức: HTTP POST (Form-Data), HTTP GET <br/>
Kết quả trả về: 
+ Status:200 => Thành công <br/>
+ Status: != 200 => Thông báo lỗi qua field message. <br/>

* Mô tả chung:<br/>
```
'page' => Kiểu int là số trang 
'limit' => Số bản ghi hiển thị trên mỗi trang<br/>
'q' => Chuỗi tìm kiếm theo tên ...<br/>
'status' => Trạng thái ...<br/>
```

**Tất cả các API khi gọi lên đều kèm theo tham số**
```
app_token = 36501|da3c4c5f57018e3c0cf004efb26ffc87,
website_id = 'int'
```

-----------------------
### 1. Attribute(Thuộc tính)

*Mô tả: Lấy ra danh sách thuộc tính của sản phẩm

* Tham số truyền vào: GET

* Link : /api/attribute
```php
[           
    'type' => 'int',
    'name' => 'string',
    'code' => 'string',
    'status' => 'int',
    'q' => 'string',
    'page' => 'int',
    'limit' => 'int',
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
### 2. Brand(Thương hiệu)

*Mô tả: Lấy ra danh sách thương hiệu

* Tham số truyền vào: GET

* Link : /api/brand
```php
[          
    'name' => 'string',
    'code' => 'string',
    'status' => 'int',
    'q' => 'string',
    'page' => 'int,1',
    'limit' => 'int,20',
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
### 3. Product(Sản phẩm)

*Mô tả: Lấy ra danh sách sản phẩm

* Tham số truyền vào: GET

* Link : /api/product
```php
[
    'brand_id' => 'int',
    'category_id' => 'string',
    'code' => 'string',
    'status' => 'int,1',
    'q' => 'string',
    'page' => 'int,1',
    'limit' => 'int,10',
    'attribute_id' => 'string',
    'product_type_id' => 'int'
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
