## Tổng quan
Domain API: https://admin.365ok.vn <br/>
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


-----------------------
### 1. Detail_Product(Chi tiết sản phẩm)

*Mô tả: Lấy ra chi tiết sản phẩm( Combo và quà tặng nếu có, sản phẩm liên quan )

* Tham số truyền vào: GET

* Link : /api/product/{id:[0-9]+}
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
--------------------------------------

### 2. Slider - Banner

* Tham số truyền vào: GET

* Link : /api/website-slideshow
```php
[
    'name' => 'string',
    'q' => 'string',
    'page' => 'int',
    'limit' => 'int',
    'type' => 'int'
]
```

* Trả về: Object Json ()
```json
{
  "data": {
  },
  "status": 200,
  "message": "success"
}
```
--------------------------------------

### 3. News(Tin tức)

*Mô tả: Lấy ra danh sách tin tức -

* Tham số truyền vào: GET

* Link : /api/news
```php
[
    'category_id' => 'string',
    'name' => 'string',
    'status' => 'int',
    'idnot' => 'int',
    'q' => 'string',
    'page' => 'int,1',
    'limit' => 'int,20',
]
```

* Trả về: Object Json (danh sách tin tức hoặc danh sách tin tức liên quan)
```json
{
  "data": {
  },
  "status": 200,
  "message": "success"
}
```

--------------------------------------

### 4. Store(Cửa hàng)

*Mô tả: Lấy ra danh sách cửa hàng

* Tham số truyền vào: GET

* Link : /api/store
```php
[
    'email' => 'string',
    'phone' => 'string',
    'code' => 'string',
    'status' => 'int',
    'q' => 'string',
    'page' => 'int,1',
    'limit' => 'int,20',
]
```

* Trả về: Object Json (danh sách cửa hàng)
```json
{
  "data": {
  },
  "status": 200,
  "message": "success"
}
```
-----------------------
### 5. Attribute(Thuộc tính)

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
### 6. Brand(Thương hiệu)

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
### 7. Product(Sản phẩm)

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

-----------------------
### 8. Combo(Combo Sản phẩm)

*Mô tả: Lấy ra danh sách combo sản phẩm

* Tham số truyền vào: GET

* Link : /api/product-product-combo-detail 

```php
[
    'product_id' => $product_id,
    'type' => 2 ,
    'options' => 1
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