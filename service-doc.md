{ "title": "서비스 기초 설정 가이드" }

## 1. 프로젝트 명칭 정의

### 프로젝트 정보

| 구분 | 내용 | 설명(예시) |
| ---- | ---- | ---- |
|게임명	| |테스트 게임|
|Firebase 프로젝트 명칭	||TestGame|
|스토어	||Google / IOS / One / Galaxy|
|지원 언어	||한국어 / 영어 / 일본어 / 중국어(간체) / 중국어(번체) / 태국어 / 베트남어 ….|
|대표 언어	||지원 언어 중 1가지 선택|
|AppPackageName - Google||com.gamepub.pubsdktest|
|AppPackageName - IOS||com.gamepub.pubsdktest|
|AppPackageName - One||com.gamepub.pubsdktest|
|AppPackageName - Galaxy||com.gamepub.pubsdktest|
|게임서버 - 결제 보상 URL(Real)|허용IP 설정에 따른 분기|https://domain?userId=id…|
|게임서버 - 결제 보상 URL(Test)|허용IP 설정에 따른 분기|https://domain?userId=id…|
|게임서버 - 쿠폰 보상 URL(Real)|허용IP 설정에 따른 분기|https://domain?userId=id…|
|게임서버 - 쿠폰 보상 URL(Test)|허용IP 설정에 따른 분기|https://domain?userId=id…|

--------------------

## 2. 구글 OAuth 계정

### 2-1. 구글 결제 영수증 검증 OAuth 계정 정보

| 구분 | 내용 | 예시 |
| ---- | ---- | ---- |
|ClientID||64889....hvju.apps.googleusercontent.com|
|ClientSecrelt||FohwFk....sk_sNA|
|RefreshToken||1//04-E....UZPIFy8|

### 2-2. 구글 OAuth 계정 생성 방법

#### 2-2-1. Google Play Console - OAuth 계정 확인 - https://play.google.com/console

##### 2-2-1-1. Google Play Console -> 설정 - 개발자계정 - API액세스

![](https://github.com/gamepubcorp/guide/blob/main/image-service/02_01_01.GooglePlayConsole.png?raw=true)

#### 2-2-2. Google Cloud Platform - 사용자 인증 정보 - https://console.cloud.google.com/apis/

##### 2-2-2-1. 사용자 인증정보 OAuth ClientID 생성

![](https://github.com/gamepubcorp/guide/blob/main/image-service/02_03_%EC%82%AC%EC%9A%A9%EC%9E%90%EC%9D%B8%EC%A6%9D%EC%A0%95%EB%B3%B4.png?raw=true)

##### 2-2-2-2. OAuth 2.0 ClientID 생성

![](https://github.com/gamepubcorp/guide/blob/main/image-service/02_04_%EC%8B%A0%EA%B7%9C%EC%83%9D%EC%84%B1.png?raw=true)

##### 2-2-2-3. OAuth 2.0 ClientID 생성 완료

![](https://github.com/gamepubcorp/guide/blob/main/image-service/02_05_%EA%B3%84%EC%A0%95%EC%83%9D%EC%84%B1%EB%90%A8.png?raw=true)

##### 2-2-2-4. OAuth 2.0 ClientID - 상세보기

![](https://github.com/gamepubcorp/guide/blob/main/image-service/02_06_%EA%B3%84%EC%A0%95%EC%A0%95%EB%B3%B4_ID_SecretKey.png?raw=true)

#### 2-2-3. Google Developers - OAuth 2.0 Playground - https://developers.google.com/oauthplayground/

##### 2-2-3-1. OAuth Play Ground - ClientID 설정

![](https://github.com/gamepubcorp/guide/blob/main/image-service/02_07_Step1.png?raw=true)

##### 2-2-3-2. OAuth 계정 선택 / 권한 부여

![](https://github.com/gamepubcorp/guide/blob/main/image-service/02_08_%ED%97%88%EC%9A%A9%EA%B3%84%EC%A0%95%EC%84%A0%ED%83%9D.png?raw=true)

##### 2-2-3-3. Authorization RefreshToken 발급

![](https://github.com/gamepubcorp/guide/blob/main/image-service/02_09_RefreshToken.png?raw=true)

##### 2-2-3-4. OAuth API 호출 테스트

![](https://github.com/gamepubcorp/guide/blob/main/image-service/02_10_API%ED%98%B8%EC%B6%9C%ED%85%8C%EC%8A%A4%ED%8A%B8.png?raw=true)

------------------------------

## 3. Firebase Push Message 설정

#### 3-1. Firebase 프로젝트 설정 - https://console.firebase.google.com/

![](https://github.com/gamepubcorp/guide/blob/main/image-service/03_00_%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8%EC%84%A4%EC%A0%95.png?raw=true)

#### 3-2. Google Cloud Platform 서비스 계정 설정

![](https://github.com/gamepubcorp/guide/blob/main/image-service/03_01_%EC%84%9C%EB%B9%84%EC%8A%A4%EA%B3%84%EC%A0%95.png?raw=true)

#### 3-3. 비공개 키 생성 - [복구 불가 주의]

![](https://github.com/gamepubcorp/guide/blob/main/image-service/03_02_%EB%B9%84%EA%B3%B5%EA%B0%9C%ED%82%A4%EB%A7%8C%EB%93%A4%EA%B8%B0.png?raw=true)

#### 3-4. 비공개 키 저장

![](https://github.com/gamepubcorp/guide/blob/main/image-service/03_03_%EB%B9%84%EA%B3%B5%EA%B0%9C%ED%82%A4%EC%A0%80%EC%9E%A5.png?raw=true)

#### 3-5. PubSDK Admin - App 설정 - 비공개 키 등록

![](https://github.com/gamepubcorp/guide/blob/main/image-service/03_04_%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8%EC%84%A4%EC%A0%95_%EB%B9%84%EA%B3%B5%EA%B0%9C%ED%82%A4%EB%93%B1%EB%A1%9D.png?raw=true)

## 4. Apple Push Notification service (APNs) 설정

#### 4-1. P8 인증서 / KeyID 전달 - https://developer.apple.com/account/resources/authkeys/list

![](https://github.com/gamepubcorp/guide/blob/main/image-service/04_01_p8%ED%8C%8C%EC%9D%BC%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C.png?raw=true)

#### 4-2 TeamID - https://developer.apple.com/account/#/membership/

![](https://github.com/gamepubcorp/guide/blob/main/image-service/04_02_TeamID%EC%A1%B0%ED%9A%8C.png?raw=true)

## 5. Apple Store Server Notification 설정

#### 5-1. 서버 응답 URL 입력 - https://appstoreconnect.apple.com/apps/{id}/appstore/info

https://developer.apple.com/documentation/appstoreservernotifications

![](https://github.com/gamepubcorp/guide/blob/main/image-service/05_01_Apple_Server_Notification_URL.png?raw=true)
