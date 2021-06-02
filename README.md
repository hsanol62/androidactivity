# androidactivity

# 기능
로그인 (로그인 여부)
회원가입(아이디 중복 체크, 빈칸 거부)

# 설명
Bitnami WAMP 설치 [Apache(웹서버), MySQL(데이터), PHP]
phpmyadmin 접속해 데이터 베이스 생성
php로 데이터와 안드로이드 스튜디오 앱부분 연결

# 코드
### Android Studio
<java>
- LoginActivity
- LoginRequest
- MainActivity
- RegisterActivity
- RegisterRequest

<latout>
activity_login.xml
activity_main.xml
activity_register.xml


- lOGINACTIVITY
  ```
   // 회원가입 버튼을 클릭 시 (수행 로그인화면에서 회원가입 화면으로 이동)
        btn_register.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                Intent intent = new Intent(LoginActivity.this, RegisterActivity.class);
                startActivity(intent);
            }
        });
 
  
  // EditText에 현재 입력되어있는 값을 get(가져온다)해온다.
                String userID = et_id.getText().toString();
                String userPass = et_pass.getText().toString();```

```//성공할 경우
  boolean success = jsonObject.getBoolean("success");
  String userID = jsonObject.getString("userID");
                                String userPass = jsonObject.getString("userPassword");
                                
     //로그인 성공 알림창                           
     Toast.makeText(getApplicationContext(),"로그인에 성공하였습니다.",Toast.LENGTH_SHORT).show();
                         
                         //로그인 창에서 메인창으로 이동
                                Intent intent = new Intent(LoginActivity.this, MainActivity.class);
                                // 메인창에 로그인창에 썼던 아이디 비번을 가져온다.
                                intent.putExtra("userID", userID);
                                intent.putExtra("userPass", userPass);
                                //실행
                                startActivity(intent);
```

 -REGISTERREQUEST
  ```// URL에 전송 ( PHP 파일 연동 )
    final static private String URL = "http://hsanol62.dothome.co.kr/Register.php";
    
    //포스트 방식으로 RESTER.PHP 파일에 해당 정보를 보내고 결과값을 가져온다.
    public RegisterRequest(String userID, String userPassword, String userName, int userAge, Response.Listener<String> listener) {
        super(Method.POST, URL, listener, null);
        
    //유저 정보 저장
     map = new HashMap<>();
        map.put("userID",userID);
        map.put("userPassword", userPassword);
        map.put("userName", userName);
        map.put("userAge", userAge + "");
   ```
    
  ### php
  ![image](https://user-images.githubusercontent.com/71969709/120552871-c0fac180-c432-11eb-9821-e3494bc77a7f.png)

  
  ### data - mysql
  register
  ![image](https://user-images.githubusercontent.com/71969709/120550885-606a8500-c430-11eb-839f-dd250f1cd9cb.png)

  login
  ![image](https://user-images.githubusercontent.com/71969709/120552942-d8d24580-c432-11eb-80b6-b7a9743977d6.png)

    
 # 구현
<img src="https://user-images.githubusercontent.com/71969709/120554705-06b88980-c435-11eb-9cbe-f9eaad0eb729.png" width="30%">
<!--    -->
<img src="https://user-images.githubusercontent.com/71969709/120554766-1d5ee080-c435-11eb-927c-cab41a7e1bca.png" width="30%">


<img src="https://user-images.githubusercontent.com/71969709/120219440-366d6300-c276-11eb-836d-9d6357d7d2db.png" width="30%">
<img src="https://user-images.githubusercontent.com/71969709/120219456-3bcaad80-c276-11eb-998f-dd5c4e962632.png" width="30%">
<!-- 회원가입   -->
  <img src="https://user-images.githubusercontent.com/71969709/120554863-3e273600-c435-11eb-9f94-d7857caf1995.png" width="30%">
<img src="https://user-images.githubusercontent.com/71969709/120219470-41c08e80-c276-11eb-839f-23420eabdf1a.png" width="30%">
<img src="https://user-images.githubusercontent.com/71969709/120219482-45ecac00-c276-11eb-8672-58f053d9bf81.png" width="30%">
<img src="https://user-images.githubusercontent.com/71969709/120219499-4a18c980-c276-11eb-88fb-9460b4cbca17.png" width="30%">
<img src="https://user-images.githubusercontent.com/71969709/120220478-bba54780-c277-11eb-83dd-80a4c19c94b0.png" width="30%">
