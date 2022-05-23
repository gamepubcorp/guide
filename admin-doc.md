{ "title": "관리자 화면 가이드" }

## 관리자 로그인

### 아이디로 로그인

#### 관리자 페이지 접근 후 ID/PW 로그인

```
URL : http://pubsdk.igamepub.co.kr/Main/Login/{Appid}/
```

![](https://github.com/gamepubcorp/guide/blob/main/image-admin/01.png?raw=true)

#### 접근 권한 요청

* 권한 요청
  * 게임명 / ID / 팀명 / 이름 => 시스템팀에 전달 후 권한 할당 요청

![](https://github.com/gamepubcorp/guide/blob/main/image-admin/02.png?raw=true)

#### 비밀번호 변경

* 최초 로그인시 비밀번호 변경 필요
* 우측 상단 메뉴 - [비밀번호 변경] 가능

![](https://github.com/gamepubcorp/guide/blob/main/image-admin/02_pw.png?raw=true)

## 프로젝트

### 프로젝트 목록

* 프로젝트 최초 등록은 시스템 팀에서 등록 후 목록에 노출 됩니다.
* 프로젝트가 보이지 않을 경우에는 시스템팀에 계정별 프로젝트 등록 요청을 해주세요.

![](https://github.com/gamepubcorp/guide/blob/main/image-admin/03.png?raw=true)

## 통계

### 대쉬보드

#### 간략정보

* 매출 - 실시간 조회되며 전체, 당일 매출을 안내 합니다.
* DAU, NRU, MCU - 1시간 단위로 취합하여 일 평균, 당일 현황을 안내 합니다.

![](https://github.com/gamepubcorp/guide/blob/main/image-admin/06.png?raw=true)

#### 기간별 조회

**날짜를 선택하여 항목별 차트 및 데이터 확인이 가능 합니다.**

![](https://github.com/gamepubcorp/guide/blob/main/image-admin/07.png?raw=true)

* DAU : 일자별 접속 계정 수
* NRU : 신규 가입 계정 수
* BU : 결제 계정
* Revenue : 결제 금액
* ARPU : 접속 계정당 구매 평균 금액
* ARPPU : 결 계정당 평균 금액
* MCU : 일자별 최고 동시 접속자 계정 수

### 사용자지표 (DAU, NRU)

**사용자 지표를 마켓별, 지역별로 구분하여 볼 수 있습니다.**

![](https://github.com/gamepubcorp/guide/blob/main/image-admin/08.png?raw=true)

* Store - Google, Apple, OneStore, Galaxy
* Nation - 디바이스 지역

### 매출지표 (Revenue, BU)

**결제 횟수 및 금액 정보를 마켓, 지역, 상품로 구분 하여 볼 수 있습니다.**

![](https://github.com/gamepubcorp/guide/blob/main/image-admin/09.png?raw=true)

* Store - Google, Apple, OneStore, Galaxy
* Nation - 디바이스 지역
* Item - 구매 상품

### 동시접속자 (MCU)

**동시 접속자 추이를 볼 수 있습니다.**
* 1분 단위 접속자 합계를 기준으로 1시간 동안 최대 계정 수

![](https://github.com/gamepubcorp/guide/blob/main/image-admin/10.png?raw=true)

* MCU : 일자별 최고 동시 접속자 계정 수

### 잔존률 (+1 Day Retention)

**NRU 기준 일자별 접속 계정 수를 퍼센트로 볼수 있습니다.**

![](https://github.com/gamepubcorp/guide/blob/main/image-admin/11.png?raw=true)

## 운영

### 회원

#### 회원목록

**계정ID : 가입일자(yymmdd) + 임의문자열(38자리)으로 구성되며 중복 되지 않는 유일한 값으로 구성**

![](https://github.com/gamepubcorp/guide/blob/main/image-admin/12.png?raw=true)

* 내려받기
  * 설정된 검색 정보를 기준으로 회원정보 CSV 다운로드 가능.

#### 회원상세

**회원목록의 '계정ID'를 클릭하면 회원의 상세정보 조회 및 관리가 가능**

![](https://github.com/gamepubcorp/guide/blob/main/image-admin/13.png?raw=true)

* 기본정보
  * 계정상세정보
  * 계정탈퇴, 계정복원 가능
* 로그인연동목록
  * 계정에 연결된 로그인 채널 목록
* 계정제재
  * 계정제재등록, 계정제재해지
* 변경이력
  * 계정의 변경 이력을 안내

### 결제

#### 구매내역

**스토어 구매 내역 조회 화면**

![](https://github.com/gamepubcorp/guide/blob/main/image-admin/16.png?raw=true)

* 결제상태
  * 결제시도 : 가결제 (거래번호 생성)
  * 결제완료 : 영수증 검증이 완료된 상태
  * 아이템지급 : 게임 서버로 아이템 지급 처리 완료
  * 개인환불 : 스토어 사용자환불조회 API를 통하여 환불 처리된 상태
  * 재결제 : 사용자환불 후 사용자 재결제 (아이템은 지급 되지 않음)
    * 게임 서버 URL으로 아이템 지급 호출 없음.
    * 클라이언트게임 일 경우 VoidedTid 항목을 참고 하여 아이템 지급 하지 않도록 처리.
* 상세보기
  * 아이템 지급 요청 결과를 확인 및 재지급 요청 가능
* 내려받기
  * 검색 항목을 통해 결제이력 CSV 다운로드 가능

#### 인앱상품

**스토어에 등록된 상품정보와 1:1 매칭되어야 구매 및 통계 조회가 가능함**

* 매칭되어야 하는 필수 정보 : 스토어, 상품ID
* PubSDK에서 내부적으로 사용되는 부가정보
  * 게임상품ID, 상품명, 설명
  * 가격은 원 단위로 환산하여 등록 필요. 원 단위 가격을 기준으로 매출 계산함.

![](https://github.com/gamepubcorp/guide/blob/main/image-admin/14.png?raw=true)

* 내려받기
  * 등록 항목 CSV 다운로드 가능
* 대량등록
  * [샘플내려받기] CSV 파일 다운로드 후 정보 입력하여 대량 업로드 가능

#### 스토어별 인앱 상품 등록 관리

![](https://github.com/gamepubcorp/guide/blob/main/image-admin/15.png?raw=true)

* 스토어상품ID : 스토어 상품ID와 매칭
* 가격 : 표기 금액을 기준으로 결제 금액 통계에 사용됨


#### 구글개인환불 목록

**구글 개인 환불자 조회 API를 통한 동기화 목록을 볼 수 있습니다.**

![](https://github.com/gamepubcorp/guide/blob/main/image-admin/17.png?raw=true)

{% hint style="info" %}
구글 개인 환불자 조회 API 를 통한 데이터 동기화 (1시간 단위 동기화 진행)
{% endhint %}

#### 구글 개인 환불자 제재 설정

**구글 개인 환불자 API 조회 대상에 대한 계정 블럭 설정**

![](https://github.com/gamepubcorp/guide/blob/main/image-admin/18.png?raw=true)

* 활성화 : 활성화 시 설정한 옵션에 따라 자동으로 결제 취소 악용자들을 이용정지 시킵니다.
* 환불횟수 : 해당 횟수 이상(>=)이면 이용정지 처리 됩니다. (0으로 설정 시 해당 조건은 사용하지 않음.)
* 환불금액(원) : 취소 금액의 합이 설정한 금액 이상(>=)이면 이용정지 처리 됩니다. (0으로 설정 시 해당 조건은 사용하지 않음.)
* 계정블럭일수 : 계정 블럭 처리 일 수 (0으로 설정 시 해당 조건은 사용되지 않습니다.)
* 메시지 : 계정 블럭 처리 진행 후 로그인 시 언어별 메시지 안내

{% hint style="info" %}
PubSDK API - Ping 호출 시 회원 정보 블럭 상태 조회 결과 반환을 통한 인게임 킥처리 연동 가능
{% endhint %}

### 푸쉬

#### 일반관리

##### 목록

**등록된 푸쉬 목록을 조회 하거나 발송 전 등록된 항목 삭제 / 신규 등록**

![](https://github.com/gamepubcorp/guide/blob/main/image-admin/19.png?raw=true)

##### 등록

**언어, 플랫폼, 광고성수신, 야간푸쉬동의, 발송시간에 맞추어 로그인 시 등록된 정보를 대상을 판별하여 발송**

{% hint style="info" %}
마지막 로그인이 2달이 지나면 Push 발송 대상에서 제거되며, 추후 로그인시 발송 대상자에 포함 됩니다.
{% endhint %}

![](https://github.com/gamepubcorp/guide/blob/main/image-admin/20.png?raw=true)

* 푸쉬 발송 기준
  * 미등록 언어 대상자
    * 대표 언어 메시지로 발송
  * 푸쉬동의
    * 푸쉬수신 허용 대상자 발송
  * 광고성수신
    * 광고수신 허용 대상자 발송
  * 야간수신동의 (KST 기준 21시 ~ 08시)
    * 야간수신 허용 대상자 발송

#### 반복관리

##### 목록

**푸쉬를 반복적으로 생성하기 위해 등록된 반복목록 조회**

![](https://github.com/gamepubcorp/guide/blob/main/image-admin/21.png?raw=true)

##### 등록

**반복적인 푸쉬 생성을 위한 등록 화면**

![](https://github.com/gamepubcorp/guide/blob/main/image-admin/22.png?raw=true)

{% hint style="info" %}
매일 저녁 10시에 다음날 발송이 필요한 푸쉬 생성 되며 생성된 항목은 일반관리 목록에서 조회 / 삭제 가능
{% endhint %}

### 공지사항

#### 목록

**노출할 일정 및 스토어를 지정하면 해당 조건에 맞춰 공지사항이 노출되고 일정 종료 후에는 노출되지 않습니다.**

![](https://github.com/gamepubcorp/guide/blob/main/image-admin/23.png?raw=true)

* 목록을 드래그하여 게시물의 노출 순서를 바꿀 수 있습니다.  게임 공지사항의 순서에도 반영 됩니다.

#### 등록

**Notice, Update 카테고리 구분이 가능 하며 스토어, 노출시간, 언어에 맞추어 설정이 가능 합니다.**

![](https://github.com/gamepubcorp/guide/blob/main/image-admin/24.png?raw=true)

* 메시지 : 내용에 있는 문자열을 그대로 SDK 클라이언트에 전송합니다.

### 이미지배너

#### 목록

![](https://github.com/gamepubcorp/guide/blob/main/image-admin/25.png?raw=true)

* 드래그 앤 드롭 방식으로 정렬 순서를 변경 할 수 있습니다.

#### 등록

![](https://github.com/gamepubcorp/guide/blob/main/image-admin/26.png?raw=true)

* 이미지 4MB  미만의 파일만 업로드 가능합니다.

### 점검

#### 목록

**인게임의 점검 설정된 목록 입니다.**

![](https://github.com/gamepubcorp/guide/blob/main/image-admin/27.png?raw=true)

* 비고 : 점검일시, 사용여부로 간략히 안내 합니다.

#### 등록

**점검이 설정된 시간에 유저 접속을 차단 합니다.**

![](https://github.com/gamepubcorp/guide/blob/main/image-admin/28.png?raw=true)

{% hint style="info" %}
IP관리 메뉴에 클라이언트 IP가 허용IP로 등록이 되어 있을 경우 로그인(접속)을 허용 합니다.
{% endhint %}

### 고객센터

#### 고객센터 URL 등록 관리

**고객센터 URL 언어별 등록 관리**

![](https://github.com/gamepubcorp/guide/blob/main/image-admin/31.png?raw=true)

### 약관

#### 약관 URL

| 구분 | 내용 |
| ------ | ------ |
| 이용약관         | 한글 - https://pubsdk-cdn.gamepub.co.kr/corp/policy/service/service.html <br> 영문 - https://pubsdk-cdn.gamepub.co.kr/corp/policy/service/service_en.html <br> 일어 - https://pubsdk-cdn.gamepub.co.kr/corp/policy/service/service_jp.html |
| 개인정보처리방침 | 한글 - https://pubsdk-cdn.gamepub.co.kr/corp/policy/privacy/privacy.html <br> 영문 - https://pubsdk-cdn.gamepub.co.kr/corp/policy/privacy/privacy_en.html <br> 일어 - https://pubsdk-cdn.gamepub.co.kr/corp/policy/privacy/privacy_jp.html |
| 환불정책         | - |​

##### 이용약관

![](https://github.com/gamepubcorp/guide/blob/main/image-admin/32.png?raw=true)

##### 개인정보처리방침

![](https://github.com/gamepubcorp/guide/blob/main/image-admin/33.png?raw=true)

##### 환불정책

![](https://github.com/gamepubcorp/guide/blob/main/image-admin/34.png?raw=true)


## 설정

### App설정

#### App 기초 정보 설정 및 연동 정보 관리

![](https://github.com/gamepubcorp/guide/blob/main/image-admin/04.png?raw=true)

* 기본정보
  * AppName : 게임명
  * 스토어 : 출시 스토어 선택
  * 사용언어 : 게임에서 지원 하고자 하는 언어를 선택 합니다.
  * 대표언어 : 사용언어 중 기본이 되는 언어를 선택 합니다.
    * 예시 > 푸쉬 발송 시 사용자의 언어와 사용언어가 불일치 할 경우 대표 언어로 메시지 전달
* 게임서버 - 허용IP 설정을 통해 Test <-> Real URL으로 호출 가능
  * 결제보상URL : 결제 검증 후 아이템 지급 호출 URL
  * 쿠폰보상URL : 회원이 쿠폰 사용 후 아이템 지급 호출 URL
* Firebase
  * 서비스계정 : 푸쉬 메시지 발송을 위한 Firebase 정보 업로드
* PackageName : 스토어 패키지명
* 기타설정
  * 계정탈퇴 철회 가능일 일반 / 게스트 : 회원이 계정탈퇴 요청 후 철회 가능한 유효일자

### 버전관리

**앱의 버전이 등록된 버전코드 보다 낮은 경우 스토어의 업데이트 화면으로 유도합니다.**

![](https://github.com/gamepubcorp/guide/blob/main/image-admin/05.png?raw=true)

* 기본정보
  * 사용여부 : 일시적 중지 / 활성화
  * 강제/권고 : 강제시 게임 접속을 불가 하며, 링크경로로 유도 합니다.
  * 버전명, 버전코드 : 버전의 정보를 입력 합니다.
  * 링크경로 : 인게임에서 버튼 클릭시 이동하는 경로를 입력 합니다.
* 업데이트 내역 : 변경된 이력을 안내 합니다.

### 접속IP관리

#### 허용IP

**특정 IP에 대해 허용 하는 목록을 보여 줍니다.**

![](https://github.com/gamepubcorp/guide/blob/main/image-admin/29.png?raw=true)

* 타입
  * 로그인 : 설정된 IP로 접속 시 [로그인차단, 점검]을 무시합니다.
  * 점검 : 설정된 IP로 접속 시 [점검]을 무시합니다.
  * App버전 : 설정된 IP로 접속 시 [App버전]을 무시합니다.
  * 아이템URL : 설정된 IP로 접속 후 [결제]/[쿠폰] 아이템 지급 요청시 [App설정]에 입력된 Test URL 주소로 호출 됩니다.
* 사용안함 설정으로 일시적 사용 해지 가능

#### 차단IP

**특정 IP에 대해 차단 하는 목록을 보여 줍니다.**

![](https://github.com/gamepubcorp/guide/blob/main/image-admin/30.png?raw=true)

* 타입
  * 로그인 : 설정된 IP로 접속 시 [로그인]을 차단 합니다.
* 사용안함 설정으로 일시적 사용 해지 가능

{% hint style="info" %}
[허용IP - 로그인]으로 설정된 IP는 [차단IP] 처리가 진행되지 않습니다.
{% endhint %}


## 게임

### 쿠폰

#### 목록

**등록된 쿠폰 목록을 확인 하거나 예약, 생성, 사용된 수량을 확인**

![](https://github.com/gamepubcorp/guide/blob/main/image-admin/35.png?raw=true)

* 진행중인 항목은 쿠폰 CSV 다운로드 가능

#### 등록

**쿠폰 등록, 추가 발급 관리**

![](https://github.com/gamepubcorp/guide/blob/main/image-admin/36.png?raw=true)

* 기본정보
  * 제목 : 쿠폰명
  * 삭제여부 : 일시적 사용 불가 처리
  * 사용기간 : 쿠폰 사용 유효기간
* 사용제한 : 쿠폰 사용 횟수 제한
  * 계정, 일자, 서버, 캐릭터 단위로 구분
  * 쿠폰 사용 API 호출 시 서버, 캐릭터 단위로 제한 할 경우 서버, 캐릭터 고유값 필수 입력
* 구성
  * Word (원코드 쿠폰) : 단어 형식으로 등록된 단어를 사용자가 입력 시 보상 수령 가능 
  * Key (난수) : 미리 생성된 Key (16자리)와 일치된 값을 사용자가 입력 시 보상 수령 가능
    * 생성된  Key는 목록에서 CSV 형식으로 다운로드 가능
    * 신규, 추가 발급 시 예약 (예약수량 증가)되며 1시간 단위로 예약 순서에 맞추어 생성
* 지급보상
  * Json 형식으로 항목이 추가 되도록 구성 되어, 쿠폰 사용시 설정된 쿠폰보상URL 으로 전달
  * 지원되지 않는 항목은 [추가] 하여 텍스트 수정 후 [저장]

### 로그인검증실패로그

#### 목록

**Server To Server API 로그인 검증 실패 시 로그 기록 및 조회**

![](https://github.com/gamepubcorp/guide/blob/main/image-admin/37.png?raw=true)

* 상세보기 기능으로 로그인 검증 데이터 상세 조회
* 조회 데이터를 기준으로 DB 회원 정보와 매칭 하여 이상 유무 체크 가능

### 원격구성

#### 목록

**Game Client에서 사용되는 Key/Value 형식의 문자열을 등록/관리**

![](https://github.com/gamepubcorp/guide/blob/main/image-admin/38.png?raw=true)