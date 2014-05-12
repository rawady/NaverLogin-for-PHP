NLPL  - v0.03
=====================


**네이버 아이디로 로그인 PHP**.
----------


Update History
---------
> **0.03 변경사항**
> 
> getConnectState() 반환값이 true / false 로 변경됨.
> - (string) connected -> (bool) true
> - (string) empty -> (bool) false


Documents
---------

**NAVER LOGIN PHP LIBRARY** 는 NAVER 공식 라이브러리가 아닙니다.

> **NOTE:**
> 
> - 네이버 공식 라이브러리가 아닙니다.
> - PHP로 **네이버 아이디로 로그인** 을 연동하기 쉽도록 제공합니다.
> - 네이버 공식 API 연동 명세는  **네이버 아이디로 로그인** 을 참고하세요.
> - <i class="icon-share"></i> http://developer.naver.com/wiki/pages/NaverLogin.






> **Spec (0.03 버전):**
> 
> - PHP 5 이상의 버전이 필요합니다.
> - curl 활성화 필요.


> **지원 기능 (0.03 버전):**
> 
> - 네이버 인증 요청 및 엑세스 토큰 취득.
> - 네이버 아이디로 로그인 버튼 생성.
> - 사용자 프로필 취득 ( JSON ).
> - 로그아웃



#### <i class="icon-file"></i> 시작하기

네이버에서 발급된 CLIENT_ID, CLIENT_SECRET 이 필요합니다. http://developer.naver.com/openapi/register.nhn 를 방문하여 키를 발급받고, 등록 과정을 완료한 이후 사용이 가능합니다.

> **주의:** 로그인 사용자 연결 유지를 위해, 세션을 사용합니다. 서버의 세션이 작동 가능하도록 해주세요.


----------


How to use
---------------

### Class 초기화


```
$naver = new Naver(array(
		"CLIENT_ID" => "USER_CLIENT_ID",
		"CLIENT_SECRET" => "USER_CLIENT_SECRET",
		"RETURN_URL" => "USER_RETURN_URL")
	);
```


### 로그인 버튼 생성

로그인 버튼은 네이버 공식 이미지로 저희 서버에서 재전송됩니다. 로그인 상태에서는 로그아웃 버튼이 표시됩니다.
```
// $naver->login();

<div class="login_box">
 <?=$naver->login()?>
</div>
```

```
// 로그인 버튼 크기변경시 

$naver->login(array(
	"width"=>"200"
));

```


### 사용자 정보 취득

사용자 정보는 로그인 및 인증 완료상태에서만, 작동합니다.
네이버에서 제공되는 XML 을  **JSON** 으로 인코딩하여 반환합니다.

```
(string JSON) $naver->getUserProfile();
```




### 로그인 상태 확인

현재 사용자의 로그인/인증 상태를 확인 할 수 있습니다.

```
(boolean) $naver->getConnectState();
```

> **리턴값:**
> 
> - <i>(boolean)</i>**true** 로그인 및 인증 완료
> - <i>(boolean)</i>**false** 연결안됨




### Access Token 확인

현재 사용자에게 발급된 엑세스토큰을 반환합니다.

```
(string) $naver->getAccess_token();
```




**곧 업데이트 됩니다...** 
