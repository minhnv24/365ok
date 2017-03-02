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


### 1. Đăng nhập hệ thống (general)
Mô tả: Đăng nhập hệ thống get accesstoken <br/>

* Link: /api/auth/login

* Tham số truyền vào: Post
```php
[
    "username"=>"Tên đăng nhập",
    "password"=>"Mật khẩu"
]
```

* Trả về
```json
{
  "data": {
    "access_token": "Token đăng nhập, sử dụng sau này",
    "user": {
      "id": "6",
      "username": "minh",
      "fullname": "minh",
      "code": null,
      "type": null,
      "avatar": null,
      "wallpaper": null,
      "position_wallpaper": null,
      "dob": "0",
      "email": "minhcntt12@gmail.com",
      "address": null,
      "phone": "01642265105",
      "degree": null,
      "position": null,
      "bank_account": null,
      "gender": "1",
      "activekey": null,
      "fbid": null,
      "fbemail": null,
      "status": "1",
      "active_register": null,
      "link_fb": null,
      "caption": null,
      "fullname_none_utf": null,
      "company_id": "1",
      "last_login": "1488361992",
      "usercreate": null,
      "datecreate": "1484025145",
      "del_flag": "0",
      "lat": null,
      "lng": null,
      "lat_location": null,
      "formatted_address": null,
      "images": {
        "avatar_lg": "Ảnh avatar của user"
      }
    }
  },
  "status": 200,
  "message": "success"
}
```


------------------------


### 2. Đăng ký (general)

* Mô tả: Khách hàng đăng ký để đặt hàng

* Tham số truyền vào: POST

* Link : /api/customer
```php
[
    'email' => 'string',
    'fullname' => 'string',
    'address' => 'string',
    'phone' => 'string',
    'password' => 'string',
    'type' => 'int',
    'username' => 'string',
    'gender' => 'int',
    'dob' => 'int',
    'caption' => 'string',
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


### 2. Đăng nhập (general)

* Mô tả: Khách hàng đăng nhập để đặt hàng

* Tham số truyền vào: POST

* Link : /api/customer/login
```php
[
    'username' => 'string (Số điện thoại - Username - Email)',
    'password' => 'string',
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

### 3. Menu (general)

* Mô tả: Menu Top - SideBar Tin tức

* Tham số truyền vào: GET

* Link : /api/menu-item
```php
[
    'source_id' => 'int',
    'type_menu' => 'int',
]
```

* Trả về: Object Array
```json
{
  "data": {
  },
  "status": 200,
  "message": "success"
}
```
--------------------------------------

### 3. Slider - Banner

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

### 4. News(Tin tức)

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

### 5. Store(Cửa hàng)

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
### 6. Attribute(Thuộc tính)

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
### 7. Brand(Thương hiệu)

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
### 8. Product(Sản phẩm)

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