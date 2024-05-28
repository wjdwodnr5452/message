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


# 웹 애플리케이션에 메시지 적용하기

#### 타임리프 메시지 적용
- 타임리프의 메시지 표현식 #{...} 를 사용하면 스프링의 메시지를 편리하게 조회할 수 있음
- 예시) #{label.item}

#### 적용법
```
<div th:text="#{label.item}"></h2>
```

# 웹 애플리케이션에 국제화 적용 하기

##### 웹으로 확인하기
- 크롬 브라우저 -> 설정 -> 언어를 검색하고, 우선 순위를 변경
- 웹 브라우저의 언어 설정 값을 변경하면 요청시 ```Accept-Language``` 의 값이 변경 된다.

```Accept-Language``` 는 클라이언트가 서버에 기대하는 언어 정보를 담아서 요청하는 HTTP 요청 헤더이다.

#### 스프링의 국제화 메시지 선택
- 스프링도 Locale 정보를 알아야 언어를 선택할 수 있음 스프링은 언어 선택시 기본으로 Accept-Language 헤더의 값을 사용 한다.

##### LocaleResolver
- 스프링은 Locale 선택 방식을 변경할 수 있도록 LocaleResolver 라는 인터페이스를 제공 하는데 스프링 부트는 기본으로 Accept-Languge를 활용하는 AcceptHeadrLocaleResolver를 사용한다.

```
public interface LocaleResolver {
Locale resolveLocale(HttpServletRequest request);
void setLocale(HttpServletRequest request, @Nullable HttpServletResponse
response, @Nullable Locale locale);
}
```


