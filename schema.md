customers [icon: user, color: green] {
  id serial pk
  username varchar(50) unique not null
  email varchar(50) unique not null
  phone char(20)
  dob date
  password varchar(256)
  bio text
  profile_picture text
  address text
  customer_id fk
}

product [icon: gcp-producer-portal, color: orange]{
  id serial pk
  name string
  description text
  product_type enum [thrifted, handmade]
  price decimal(10, 2)
   category varchar(20)
  size varchar(20)
  weight decimal
  color varchar(20)
}

thrifted_product[color: red] {
  id serial pk
  product_id fk
  condition enum [new, good, fair, poor]
  sourced_from varchar(50)
}

handmade_product[color: grey] {
  id serial pk
  product_id fk
  materials_used text
  restock_possible boolean
}

inventory [icon: gcp-os-inventory-management, color: pink]{
  id serial pk
  product_qty int
  product_id fk
}

order[icon: d365-intelligent-order-management, color: yellow]{
  id serial pk
  customer_id fk
  total_amount decimal
  order_date date
  order_status enum [pending, processing, shipped, cancelled]
}

orderitem[icon: d365-intelligent-order-management,color: brown]{
  id serial pk
  order_id fk
  product_id fk
  quantity int
  unit_price decimal
}

payment [icon: payment, color: purple]{
  id serial pk
  order_id fk
  paid_amount decimal(10,8)
  payment_mode enum [stripe, cod]
  payment_date date
  payment_status enum[pending, paid, failed, refund]
}

shipping [icon: ship,color: orange]{
  id serial pk
  order_id fk
  courier_id fk
  tracking_number varchar(40)
  shipped_date date
  delivery_status enum [not_shipped, shipped, out_for_delivery, delivered, failed_delivery, returned]
}

customers.id - product.product_id
order.id < orderitem.order_id
product.id < orderitem.product_id
product.id - inventory.product_id
product.id - thrifted_product.product_id
product.id - handmade_product.product_id
order.id - payment.order_id
order.id - shipping.order_id

