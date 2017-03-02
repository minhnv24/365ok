## Tổng quan
Domain API: https://admin.365ok.vn <br/>
Giao thức: HTTP POST (Form-Data), HTTP GET <br/>
Kết quả trả về: 
+ Status: **200** => Thành công <br/>
+ Status: **!= 200** => Thông báo lỗi qua field message. <br/>
* Mô tả chung:<br/>
```
"page" => "Kiểu int là số trang"
"limit" => "Số bản ghi hiển thị trên mỗi trang",
"q" => "Chuỗi tìm kiếm theo tên ...",
"status" => "Trạng thái ...",
```

----------


### 1. Đặt hàng

*Mô tả: Đặt hàng sản phẩm

* Tham số truyền vào: POST

* Link : /api/order
```php
"cart"=>
 [
    "product"=>
    [
      ["0f8cbd7f682c18a01cc60429ae93bda3 - (Key tự sinh)"]=>
          [
            'product_id'=> 'int - (ID sản phẩm)',
            'channel_product_id' => 'int (ID channel sản phẩm)',
            'price_sell' => 'int (Giá bán sản phẩm)',
            'quantity' => 'int (Số lượng sản phẩm)',
            'product_combo_id' => 'int (Nếu type là product thì NULL)',
            'key_combo' => 'int (Nếu type là product thì NULL)',
            'type' => 'product (Kiểu product)'
          ]
      ],
    ],    
    [2]=> //(2 - Key combo) 
    [
        [
             'product_id'=> 'int (ID sản phẩm)',
             'channel_product_id' => 'int (ID channel sản phẩm)',
             'price_sell' => 'int (Giá bán sản phẩm)',
             'quantity' => 'int (Số lượng sản phẩm)',
             'product_combo_id' => 'int (Nếu type là product thì NULL)',
             'key_combo' => 'int (Nếu type là product thì NULL)',
             'type' => 'combo (Kiểu product)'
        ],  
        [
             'product_id'=> 'int (ID sản phẩm)',
             'channel_product_id' => 'int (ID channel sản phẩm)',
             'price_sell' => 'int (Giá bán sản phẩm)',
             'quantity' => 'int (Số lượng sản phẩm)',
             'product_combo_id' => 'int',
             'key_combo' => 'int',
             'type' => 'combo (Kiểu combo)'
         ],
    ],    
    [3]=> //( 3 - Key combo) 
    [
        [
             'product_id'=> 'int (ID sản phẩm)',
             'channel_product_id' => 'int (ID channel sản phẩm)',
             'price_sell' => 'int (Giá bán sản phẩm)',
             'quantity' => 'int (Số lượng sản phẩm)',
             'product_combo_id' => 'int (Nếu là product thì NULL)',
             'key_combo' => 'int (Nếu là product thì NULL)',
             'type' => 'combo (Kiểu product)'
        ],  
        [
             'product_id'=> 'int (ID sản phẩm)',
             'channel_product_id' => 'int (ID channel sản phẩm)',
             'price_sell' => 'int (Giá bán sản phẩm)',
             'quantity' => 'int (Số lượng sản phẩm)',
             'product_combo_id' => 'int',
             'key_combo' => 'int',
             'type' => 'combo (Kiểu combo)'
         ],
    ]
],
"order" =>
[
    'source_id'=> 'int (Nguồn đơn hàng)',
    'type' => 'int (Loại đơn online)',
    'address' => 'string (Địa chỉ đặt hàng)',
    'payment_method' => 'int (Phương thức thanh toán)',
    'payment_status' => 'int (Trạng thái thanh toán)',
    'total' => 'float (Tổng tiền thanh toán sau khi đã sale)',
    'total_origin' => 'float (Tổng tiền thanh toán chưa trừ chiết khấu)',
    'transporter_form_id' => 'int (Phương thức vận chuyển)',
    'source_id' => 'int (Nguồn đơn hàng đổ từ web site nào)',
    'customer_caption' => 'string (Ghi chú khách hàng)',
    'caption' => 'string (Mô tả đơn hàng)',
]
'customer' => 
[
     'phone' => 'int (Số điện thoại khách hàng)',
     'fullname' => 'sting (Tên khách hàng)',
     'email' => 'string (Email)',
     'address' => 'string',
     'caption' => 'string',
     'social_type' => 'string (Kiểu dịch vụ)',
     'social' => 'string (ID dịch vụ)',
];
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

