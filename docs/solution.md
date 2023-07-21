### Workflow
1. render list product
2. show product detail
3. show cart list when click cart icon
4. add to cart
5. handle Up Or Down Amount product in card
6. remove product in card

---

### Solution

##### 1. render list product:
- prop down


##### 2. show product detail
- Create `Modal` global-component `slot`
- Add comp `detail-product` into `slot` of `Modal`

##### 3. show cart list when click cart icon
- using `Modal` global component
- Add comp `cart-list` into `slot` of `Modal`

##### 4. add to cart

- 1. Tăng `count` `cart` lên
    - Cộng all `amount` của `product` trong `carList` --> `reduce()` --> `computed` để tính


- 2. Thêm product to cart

  - Check product trong cart 
    + Nếu đã có --> tăng `amount` của `product` tại `[index]`  lên 1
    + else chưa có --> `push` vào `cartList`

- 3. Sum price in list Cart
  - Cộng all `price * amount` của `product` trong `carList` --> `reduce()` --> `computed` để tính
  


##### 5. handle Up Or Down Amount product in card
- Đặt 1 `flag` cho 2 nút `up` và `down` để nhận biết
  + Đặt true cho nút `up`


- Khi click `up` check nếu product `đã có` trong `cartList` --> tăng `amount` của `product` tại `[index]`  lên 1

- Check thêm điều kiện trong `listCart` khi `Up`
  + Nếu `product` có `amount` > `quantityInStock` của thì --> ko cho `Up` nữa

- Case nút `Down` ngược lại

##### 6. remove product in card
- Dùng filter loại bỏ product bị remove