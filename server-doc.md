{ "title": "Server API" }
{ "description": "PubSDK Server & Game Server - Server Side HTTP Request" }

## PubSDK 서버 > 게임 서버 호출

### 결제 - 아이템 지급 호출

**결제 완료 및 영수증 검증 후  PubSDK 서버에서 게임 서버로 아이템 지급을 위해 HTTP 요청을 합니다.**

![Purchase Flow](https://github.com/gamepubcorp/guide/blob/main/image-server/01_purchase_flow.png?raw=true)

**Request**

```
Method : POST
URL : {URL}
Header : "content-type: application/json; charset=UTF-8"
Body : 
{
   accountid
   tid
   orderid
   purchasetoken
   store
   productid
   serverid
   playerid
   etc
}
```

{% hint style="info" %}
{URL} 항목은 PubSDK 관리자 - 설정 - App설정 - 게임서버 - 결제보상URL 항목에 입력 되어야 합니다.
{% endhint %}

| Attribute     | Type   | Length | Description               |
| ------------- | :----: | -----: | ------------------------- |
| accountid     | string | 50     | 계정ID                    |
| tid           | string | 20     | 결제번호                  |
| order         | string | 100    | 주문번호(GPA-xxx-xxx-xxx) |
| purchasetoken | string | 1000   | 결제 토큰                 |
| store         | string | 10     | 스토어                    |
| productid     | string | 50     | 결제 상품ID               |
| serverid      | string | 10     | 결제 호출시 입력값 전달   |
| playerid      | string | 50     | 결제 호출시 입력값 전달   |
| etc           | string | 500    | 결제 호출시 입력값 전달   |

**Response**
```
예시 - 대소문자 주의
{
    "code": 1,
    "message" : "Success",
    "reward" : "item:1,cnt:10"
}
```

| Attribute | Type   | Length | Description       |
| --------- | :----: | -----: | ----------------- |
| code      | int    | 1      | 0:실패, 1:성공    |
| message   | string | 100    | 오류 발생 시 내용 |
| reward    | string | 1000   | 아이템 지급 목록 (Game Client Result Data)  |

### 쿠폰 - 아이템 지급 호출

**쿠폰 사용 후에 PubSDK 서버에서 게임 서버로 아이템 지급을 위해 HTTP 요청을 합니다.**

**Request**

```
Method : POST
URL : {URL}
Header : "content-type: application/json; charset=UTF-8"
Body : 
{
   accountid
   serverid
   playerid
   item
}
```

{% hint style="info" %}
{URL} 항목은 PubSDK 관리자 - 설정 - App설정 - 게임서버 - 쿠폰보상URL 항목에 입력 되어야 합니다.
{% endhint %}

| Attribute | Type   | Length | Description             |
| --------- | :----: | -----: | ----------------------- |
| accountid | string | 50     | 계정ID                  |
| serverid  | string | 10     | 쿠폰 호출시 입력값 전달 |
| playerid  | string | 100    | 쿠폰 호출시 입력값 전달 |
| etc       | string | 500    | 쿠폰 호출시 입력값 전달 |
| item      | string | 500    | 지급 아이템 (JSON) - 예시 > <br> [{"type":"EXP","code":"0","count":100}, <br> {"type":"GOLD","code":"0","count":200}] |

**Response**
```
예시 - 대소문자 주의
{
    "code": 1,
    "message" : "Success"
}
```

| Attribute | Type   | Length | Description       |
| --------- | :----: | -----: | ----------------- |
| code      | int    | 1      | 0:실패, 1:성공    |
| message   | string | 100    | 오류 발생 시 내용 |

## 게임 서버 > PubSDK 서버 호출

### 로그인 토큰 검증 - (Optional)

**게임에서 로그인 완료 후 얻은 정보로 PubSDK 서버에 로그인 검증이 가능 합니다.**

* 검증 - PubSDK AuthToken 검증 절차
  * AuthToken
    * 호출 시 Param 불일치 검증
    * Sign 검증 (변조 검증)
    * 생성 -> 검증 호출 시간 10분 제한
    * 회원정보 불일치 검증 (예시> Login DeviceID <-> Token DeviceID)      

![Login Flow](https://github.com/gamepubcorp/guide/blob/main/image-server/03_login_flow.png?raw=true)
        
**Request**
```
Method : POST
URL : https://pubsdkapi.igamepub.co.kr/api/game/loginauth
Header : "content-type: application/json"
Body : 
{
    accountid
    channel
    channelid
    authtoken
}
```

| Attribute  | Type   | Length | Description      |
| ---------- | :----: | -----: | ---------------- |
| accountid  | string | 50     | 계정ID           |
| channel    | string | 50     | 로그인 구분      |
| channelid  | string | 50     | 로그인ID         |
| authtoken  | string | 2000   | PubSDK 인증 토큰 |

**Response**

```
예시 - 대소문자 주의

성공 : 
{ code = 1, message = "OK" }

실패 :  
{ code = -1, message = "Request Data Check" }
{ code = -2, message = "AuthToken Data Error" }
{ code = -3, message = "AuthToken Expired" }
{ code = -4, message = "Request Data Error" }
{ code = -5, message = "User Not found" }
```

| Attribute | Type   | Length | Description       |
| --------- | :----: | -----: | ----------------- |
| code      | int    | 1      | 1:성공            |
| message   | string | 100    | 오류 발생 시 내용 |

​