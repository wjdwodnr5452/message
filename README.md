# 메시지, 국제화

##### 메시지
- html에 사용하는 메시지를 한 곳에서 관리 하도록 하는 기능을 메시지 기능 이다.

###### 예시) messages.properties 

```
item=상품
item.id=상품 ID
item.itemName=상품명
item.price=가격
item.quantity=수량
```


###### 국제화
- 메시지에서 설명한 메시지 파일을 각 나라별로 별도로 관리하면 서비스를 국제화 할 수 있다.
- 한국에서 접근한 것인지 영어에서 접근 한것인지는 인식하는 방법은 HTTP accecpt-language 해더 값을 사용하거나 사용자가 직접 언어를 선택하도록 하고, 쿠키 등을 사용해서 처리 하면 된다.

##### messages_en.properties
```
item=Item
item.id=Item ID
item.itemName=Item Name
item.price=price
item.quantity=quantity
```
##### messages_ko.properties
```
item=상품
item.id=상품 ID
item.itemName=상품명
item.price=가격
item.quantity=수량
```
