
[bookshop_schema.json]
```
{
  "metadata": {
    "schema_name": "bookshop",
    "schema_format": "JSON",
    "description": "This database is a relational database (RDB) for an online BookShop, consisting of tables related to customers, orders, products, and shipping.",
    "include_sample_data": true
  },
  "tables": [
    {
      "name": "Customer",
      "table_type": "Master",
      "description": "顧客マスタ。会員情報を格納する。",
      "columns": [
        {
          "name": "customerId",
          "type": "INT",
          "primary_key": true,
          "not_null": true,
          "auto_increment": true,
          "description": "顧客ID"
        },
        {
          "name": "name",
          "type": "VARCHAR(255)",
          "not_null": true,
          "description": "顧客名"
        },
        {
          "name": "emailAddress",
          "type": "VARCHAR(255)",
          "not_null": true,
          "description": "メールアドレス"
        },
        {
          "name": "phoneNumber",
          "type": "VARCHAR(20)",
          "not_null": false,
          "description": "電話番号"
        },
        {
          "name": "gender",
          "type": "ENUM",
          "not_null": true,
          "description": "性別",
          "enum_values": [
            {
              "value": "Male",
              "description": "男性"
            },
            {
              "value": "Female",
              "description": "女性"
            },
            {
              "value": "Other",
              "description": "その他"
            }
          ]
        },
        {
          "name": "birthYear",
          "type": "YEAR",
          "not_null": false,
          "description": "出生年度"
        },
        {
          "name": "billingStreet",
          "type": "VARCHAR(255)",
          "not_null": false,
          "description": "請求先住所の通り"
        },
        {
          "name": "billingCity",
          "type": "VARCHAR(100)",
          "not_null": false,
          "description": "請求先住所の市"
        },
        {
          "name": "billingState",
          "type": "VARCHAR(100)",
          "not_null": false,
          "description": "請求先住所の都道府県"
        },
        {
          "name": "billingPostalCode",
          "type": "VARCHAR(20)",
          "not_null": false,
          "description": "請求先郵便番号"
        },
        {
          "name": "billingCountry",
          "type": "VARCHAR(100)",
          "not_null": false,
          "description": "請求先住所の国"
        },
        {
          "name": "shippingStreet",
          "type": "VARCHAR(255)",
          "not_null": false,
          "description": "配送先住所の通り"
        },
        {
          "name": "shippingCity",
          "type": "VARCHAR(100)",
          "not_null": false,
          "description": "配送先住所の市"
        },
        {
          "name": "shippingState",
          "type": "VARCHAR(100)",
          "not_null": false,
          "description": "配送先住所の都道府県"
        },
        {
          "name": "shippingPostalCode",
          "type": "VARCHAR(20)",
          "not_null": false,
          "description": "配送先郵便番号"
        },
        {
          "name": "shippingCountry",
          "type": "VARCHAR(100)",
          "not_null": false,
          "description": "配送先住所の国"
        },
        {
          "name": "createdAt",
          "type": "DATETIME",
          "not_null": false,
          "default": "CURRENT_TIMESTAMP",
          "description": "データ登録日"
        },
        {
          "name": "updatedAt",
          "type": "DATETIME",
          "not_null": false,
          "default": "CURRENT_TIMESTAMP",
          "description": "データ更新日"
        }
      ],
      "sample_data": [
        {
          "customerId": 1,
          "name": "佐藤 浩",
          "emailAddress": "chiyo43@example.com",
          "phoneNumber": "07-3889-7253",
          "gender": "Other",
          "birthYear": 1948,
          "billingStreet": "027 阿部 Street",
          "billingCity": "目黒区",
          "billingState": "愛知県",
          "billingPostalCode": "123-4567",
          "billingCountry": "Japan",
          "shippingStreet": "512 小川 Street",
          "shippingCity": "長生郡長生村",
          "shippingState": "山形県",
          "shippingPostalCode": "678-9016",
          "shippingCountry": "Japan",
          "createdAt": "",
          "updatedAt": ""
        },
        {
          "customerId": 2,
          "name": "渡辺 淳",
          "emailAddress": "asuka13@example.com",
          "phoneNumber": "080-5639-8150",
          "gender": "Other",
          "birthYear": 2004,
          "billingStreet": "662 石川 Street",
          "billingCity": "葛飾区",
          "billingState": "大阪府",
          "billingPostalCode": "234-5678",
          "billingCountry": "Japan",
          "shippingStreet": "983 吉田 Street",
          "shippingCity": "横浜市金沢区",
          "shippingState": "秋田県",
          "shippingPostalCode": "123-4569",
          "shippingCountry": "Japan",
          "createdAt": "",
          "updatedAt": ""
        }
      ]
    },
    {
      "name": "Product",
      "table_type": "Master",
      "description": "製品（書籍）マスタ。書籍情報を格納する。",
      "columns": [
        {
          "name": "bookId",
          "type": "INT",
          "primary_key": true,
          "auto_increment": true,
          "not_null": true,
          "description": "書籍ID"
        },
        {
          "name": "bookTitle",
          "type": "VARCHAR(255)",
          "not_null": true,
          "description": "書籍タイトル"
        },
        {
          "name": "author",
          "type": "VARCHAR(255)",
          "not_null": true,
          "description": "著者"
        },
        {
          "name": "price",
          "type": "DECIMAL(10,2)",
          "not_null": true,
          "description": "価格"
        },
        {
          "name": "publisher",
          "type": "VARCHAR(255)",
          "not_null": true,
          "description": "出版社"
        },
        {
          "name": "createdAt",
          "type": "DATETIME",
          "not_null": false,
          "default": "CURRENT_TIMESTAMP",
          "description": "データ登録日"
        },
        {
          "name": "updatedAt",
          "type": "DATETIME",
          "not_null": false,
          "default": "CURRENT_TIMESTAMP",
          "description": "データ更新日"
        }
      ],
      "sample_data": [
        {
          "bookId": 1,
          "bookTitle": "Rubyケ奇跡ス",
          "author": "鈴木 真綾",
          "price": 792.93,
          "publisher": "学研プラス",
          "createdAt": "",
          "updatedAt": ""
        },
        {
          "bookId": 2,
          "bookTitle": "未来スプログラミングサ",
          "author": "中村 美加子",
          "price": 505.67,
          "publisher": "角川書店",
          "createdAt": "",
          "updatedAt": ""
        }
      ]
    },
    {
      "name": "Orders",
      "table_type": "Transaction",
      "description": "注文データ。顧客による注文を管理する。",
      "columns": [
        {
          "name": "orderId",
          "type": "CHAR(36)",
          "primary_key": true,
          "not_null": true,
          "description": "注文ID (UUID)"
        },
        {
          "name": "customerId",
          "type": "INT",
          "not_null": false,
          "description": "顧客ID"
        },
        {
          "name": "orderDate",
          "type": "TIMESTAMP",
          "not_null": false,
          "description": "注文日"
        },
        {
          "name": "totalAmount",
          "type": "DECIMAL(10,2)",
          "not_null": false,
          "description": "総額"
        },
        {
          "name": "paymentMethodType",
          "type": "VARCHAR(50)",
          "not_null": false,
          "description": "支払い方法のタイプ"
        },
        {
          "name": "paymentProvider",
          "type": "VARCHAR(50)",
          "not_null": false,
          "description": "支払いプロバイダー"
        },
        {
          "name": "notes",
          "type": "TEXT",
          "not_null": false,
          "description": "配送に関するメモ"
        },
        {
          "name": "createdAt",
          "type": "DATETIME",
          "not_null": false,
          "default": "CURRENT_TIMESTAMP",
          "description": "データ登録日"
        },
        {
          "name": "updatedAt",
          "type": "DATETIME",
          "not_null": false,
          "default": "CURRENT_TIMESTAMP",
          "description": "データ更新日"
        }
      ],
      "sample_data": [
        {
          "orderId": "00001b84-dcf9-4f11-93f1-4c4c077ced3e",
          "customerId": 14191,
          "orderDate": "",
          "totalAmount": 14057.1,
          "paymentMethodType": "クレジットカード",
          "paymentProvider": "Visa",
          "notes": "バナー符号サンプル陶器差別する普通のじぶんの。",
          "createdAt": "",
          "updatedAt": ""
        },
        {
          "orderId": "00002476-b1dd-41c9-8cb4-a4ecd174a977",
          "customerId": 23538,
          "orderDate": "",
          "totalAmount": 14193.86,
          "paymentMethodType": "銀行振込",
          "paymentProvider": "三菱UFJ銀行",
          "notes": "ダニ日曜日通行料金目的ささやきバケツ転倒。",
          "createdAt": "",
          "updatedAt": ""
        }
      ]
    },
    {
      "name": "OrderItems",
      "table_type": "Detail",
      "description": "注文明細データ。注文ごとの商品情報を格納する。",
      "columns": [
        {
          "name": "orderId",
          "type": "CHAR(36)",
          "primary_key": true,
          "not_null": true,
          "description": "注文ID (Orders参照)"
        },
        {
          "name": "bookId",
          "type": "INT",
          "primary_key": true,
          "not_null": true,
          "description": "書籍ID (Product参照)"
        },
        {
          "name": "quantity",
          "type": "INT",
          "not_null": false,
          "description": "数量"
        },
        {
          "name": "price",
          "type": "DECIMAL(10,2)",
          "not_null": false,
          "description": "単価"
        },
        {
          "name": "totalPrice",
          "type": "DECIMAL(10,2)",
          "not_null": false,
          "description": "合計価格"
        }
      ],
      "sample_data": [
        {
          "orderId": "00001b84-dcf9-4f11-93f1-4c4c077ced3e",
          "bookId": 63155,
          "quantity": 1,
          "price": 2573.36,
          "totalPrice": 2573.36
        },
        {
          "orderId": "00001b84-dcf9-4f11-93f1-4c4c077ced3e",
          "bookId": 100391,
          "quantity": 1,
          "price": 3413.24,
          "totalPrice": 3413.24
        }
      ]
    },
    {
      "name": "Shipping",
      "table_type": "Transaction",
      "description": "配送データ。配送先情報を管理する。",
      "columns": [
        {
          "name": "shippingId",
          "type": "CHAR(36)",
          "primary_key": true,
          "not_null": true,
          "description": "配送ID (UUID)"
        },
        {
          "name": "customerId",
          "type": "VARCHAR(10)",
          "not_null": false,
          "description": "顧客ID"
        },
        {
          "name": "orderId",
          "type": "CHAR(36)",
          "not_null": false,
          "description": "注文ID"
        },
        {
          "name": "orderDate",
          "type": "TIMESTAMP",
          "not_null": false,
          "description": "注文日"
        },
        {
          "name": "shippingDate",
          "type": "TIMESTAMP",
          "not_null": false,
          "description": "配送日"
        },
        {
          "name": "shippingStreet",
          "type": "VARCHAR(255)",
          "not_null": false,
          "description": "配送先住所の通り"
        },
        {
          "name": "shippingCity",
          "type": "VARCHAR(100)",
          "not_null": false,
          "description": "配送先住所の市"
        },
        {
          "name": "shippingState",
          "type": "VARCHAR(100)",
          "not_null": false,
          "description": "配送先住所の都道府県"
        },
        {
          "name": "shippingPostalCode",
          "type": "VARCHAR(20)",
          "not_null": false,
          "description": "配送先郵便番号"
        },
        {
          "name": "shippingCountry",
          "type": "VARCHAR(100)",
          "not_null": false,
          "description": "配送先住所の国"
        },
        {
          "name": "shippingStatus",
          "type": "ENUM",
          "description": "出荷状況",
          "enum_values": [
            {
              "value": "Pending",
              "description": "出荷処理待ち"
            },
            {
              "value": "Shipped",
              "description": "出荷済み"
            },
            {
              "value": "In Transit",
              "description": "配送中"
            },
            {
              "value": "Delivered",
              "description": "配達完了"
            },
            {
              "value": "Cancelled",
              "description": "キャンセル済み"
            }
          ],
          "default": "Pending"
        },
        {
          "name": "notes",
          "type": "TEXT",
          "not_null": false,
          "description": "配送メモ"
        },
        {
          "name": "createdAt",
          "type": "DATETIME",
          "not_null": false,
          "default": "CURRENT_TIMESTAMP",
          "description": "データ登録日"
        },
        {
          "name": "updatedAt",
          "type": "DATETIME",
          "not_null": false,
          "default": "CURRENT_TIMESTAMP",
          "description": "データ更新日"
        }
      ],
      "sample_data": [
        {
          "shippingId": "000005de-4525-4377-99da-ae4c8e4d4b09",
          "customerId": 30916,
          "orderId": "5a79e3d5-9f60-48ed-a020-02b1fe8bb9a8",
          "orderDate": "",
          "shippingDate": "",
          "shippingStreet": "989 加藤 Street",
          "shippingCity": "長生郡一宮町",
          "shippingState": "長野県",
          "shippingPostalCode": "234-5671",
          "shippingCountry": "Japan",
          "shippingStatus": "Delivered",
          "notes": "",
          "createdAt": "",
          "updatedAt": ""
        },
        {
          "shippingId": "000011d5-8b0a-4961-92b3-da3d143a8d37",
          "customerId": 43556,
          "orderId": "cffc24c4-5bb2-4d57-81eb-951b640193b1",
          "orderDate": "",
          "shippingDate": "",
          "shippingStreet": "224 遠藤 Street",
          "shippingCity": "浦安市",
          "shippingState": "石川県",
          "shippingPostalCode": "456-7890",
          "shippingCountry": "Japan",
          "shippingStatus": "Delivered",
          "notes": "",
          "createdAt": "",
          "updatedAt": ""
        }
      ]
    },
    {
      "name": "ShippingItems",
      "table_type": "Detail",
      "description": "配送明細データ。配送ごとの商品情報を格納する。",
      "columns": [
        {
          "name": "shippingId",
          "type": "CHAR(36)",
          "primary_key": true,
          "not_null": true,
          "description": "配送ID"
        },
        {
          "name": "bookId",
          "type": "INT",
          "primary_key": true,
          "not_null": true,
          "description": "書籍ID"
        },
        {
          "name": "title",
          "type": "VARCHAR(255)",
          "not_null": false,
          "description": "書籍タイトル"
        },
        {
          "name": "quantity",
          "type": "INT",
          "not_null": false,
          "description": "数量"
        }
      ],
      "sample_data": [
        {
          "shippingId": "000005de-4525-4377-99da-ae4c8e4d4b09",
          "bookId": 40472,
          "title": "未来サセキュリティウ",
          "quantity": 1
        },
        {
          "shippingId": "000005de-4525-4377-99da-ae4c8e4d4b09",
          "bookId": 50646,
          "title": "デジタルソ世界エ",
          "quantity": 2
        }
      ]
    }
  ],
  "relationships": [
    {
      "from_table": "Orders",
      "from_column": "customerId",
      "to_table": "Customer",
      "to_column": "customerId"
    },
    {
      "from_table": "OrderItems",
      "from_column": "orderId",
      "to_table": "Orders",
      "to_column": "orderId"
    },
    {
      "from_table": "OrderItems",
      "from_column": "bookId",
      "to_table": "Product",
      "to_column": "bookId"
    },
    {
      "from_table": "Shipping",
      "from_column": "customerId",
      "to_table": "Customer",
      "to_column": "customerId"
    },
    {
      "from_table": "Shipping",
      "from_column": "orderId",
      "to_table": "Orders",
      "to_column": "orderId"
    },
    {
      "from_table": "ShippingItems",
      "from_column": "shippingId",
      "to_table": "Shipping",
      "to_column": "shippingId"
    },
    {
      "from_table": "ShippingItems",
      "from_column": "bookId",
      "to_table": "Product",
      "to_column": "bookId"
    }
  ],
  "table_categories": {
    "master_tables": [
      "Customer",
      "Product",
      "Category"
    ],
    "transaction_tables": [
      "Orders",
      "Payments"
    ],
    "detail_tables": [
      "OrderItems",
      "ShippingItems"
    ]
  },
  "disambiguation_rules": {
    "customerId": {
      "preferred_column": "Customer.customerId",
      "reason": "Master table and the origin of all related foreign keys"
    },
    "shippingStreet": {
      "preferred_column": "Customer.shippingStreet",
      "reason": "Master table preferred, and origin in Customer → Shipping relationship"
    },
    "shippingCity": {
      "preferred_column": "Customer.shippingCity",
      "reason": "Master table preferred, and origin in Customer → Shipping relationship"
    },
    "shippingState": {
      "preferred_column": "Customer.shippingState",
      "reason": "Master table preferred, and origin in Customer → Shipping relationship"
    },
    "shippingPostalCode": {
      "preferred_column": "Customer.shippingPostalCode",
      "reason": "Master table preferred, and origin in Customer → Shipping relationship"
    },
    "shippingCountry": {
      "preferred_column": "Customer.shippingCountry",
      "reason": "Master table preferred, and origin in Customer → Shipping relationship"
    },
    "bookId": {
      "preferred_column": "Product.bookId",
      "reason": "Master table and common source for both OrderItems and ShippingItems"
    },
    "price": {
      "preferred_column": "Product.price",
      "reason": "Original data is defined in the Product (book master) table"
    },
    "orderId": {
      "preferred_column": "Orders.orderId",
      "reason": "Central Transaction table and source for OrderItems and Shipping"
    },
    "orderDate": {
      "preferred_column": "Orders.orderDate",
      "reason": "Original data for Shipping orderDate comes from Orders"
    },
    "notes": {
      "preferred_column": "Orders.notes",
      "reason": "Shipping notes are derived from order-level notes"
    },
    "quantity": {
      "preferred_column": "OrderItems.quantity",
      "reason": "Shipping quantities are based on ordered quantities"
    },
    "shippingId": {
      "preferred_column": "Shipping.shippingId",
      "reason": "Origin key in Shipping → ShippingItems relationship"
    }
  }
}
```