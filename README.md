# HTML4_20201124_coding
coding,문법, 입력양식태그


#### **에러 쉽게 찾는 방법 1)**

[1] 이렇게 여러 실행구문이 있을 경우

    function xxx() {

        실행구문1;
        실행구문2;
        실행구문3;
        실행구문4;
        실행구문5;
        실행구문6;

    }

[2] 실행 구문의 주석을 하나씩 풀면서 컴파일하여 검사한다.

    function xxx() {

        실행구문1;
        /*
        실행구문2;
        실행구문3;
        실행구문4;
        실행구문5;
        실행구문6;
        */

    }

#### **에러 쉽게 찾는 방법 2)**

**(alert 방법으로 에러 찾기)**

    function xxx() {

    alert(1);

        실행구문1;

    alert(2);

        실행구문2;

    alert(3);

        실행구문3;

    alert(4);

        실행구문4;

    alert(5);

        실행구문5;

    alert(6);
    
        실행구문6;

    }



#### // \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*  
**// 0. 회원가입 script 태그**  
// \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*

```
<script>
    function checkMemForm(){
```

// \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*  
//**  1.  아이디 유효성 체크하기**  
// \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*

```
var userId = document.memRegForm.userId.value;

var regExp = new RegExp(/^[a-z][a-z0-9_]{4,9}$/);

if(regExp.test(userId)==false){
    alert("올바른 아이디가 아닙니다.")
    // *****************************************
    // 1-1. 사용자가 입력값을 잘못 입력했을 때 기존문자열 삭제하기 
    // *****************************************
    document.memRegForm.userId.value = "";

    return;
}
```

// \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*  
**//  2.  암호 유효성 체크하기**  
// \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*

```
    var pwd = document.memRegForm.pwd.value;

    var regExp = new RegExp(/^[a-z0-9]{8,14}$/);

    if(regExp.test(pwd)==false){

        alert("올바른 비밀번호가 아닙니다.")
        // *****************************************
        // 2-1. 사용자가 입력값을 잘못 입력했을 때 기존문자열 삭제하기 
        // *****************************************
        document.memRegForm.pwd.value = "";

        return;
    }
```

// \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*  
//  **3\.  전화번호 유효성 체크하기**  
// \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*

```
    var phone = document.memRegForm.phone.value;

    var regExp = new RegExp(/^010-[0-9]{4}-[0-9]{4}$/);

    if (regExp.test(phone)==false){

        alert("올바른 전화번호가 아닙니다.");
        // *****************************************
        // 1-1. 사용자가 입력값을 잘못 입력했을 때 기존문자열 삭제하기 
        // *****************************************
        document.memRegForm.phone.value = "";

        return;
    }
```

// \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*  
//  **4.  스킬 유효성 체크하기**  
// \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*  
// 스킬은 1개 이상 체크해야 한다.

```
    var cnt = 0;

    for(var i=0; i<document.memRegForm.skill.length;i++){

        if (document.memRegForm.skill[i].checked==true){

            cnt++;

        }
    }
    if(cnt==0){
        alert("스킬은 1개 이상 체크해야 합니다.")
        return;
    }
```

**// \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\***  
**// 5. 학력 유효성 체크하기**  
**// \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\***  
// 1개는 무조건 선텍해야한다

```
    var cnt = 0;

    for(var i=0; i<document.memRegForm.school.length;i++){

        if (document.memRegForm.school[i].checked==true){

            cnt++;
            break;
        }

    }
    if (cnt==0) {
        alert("학력을 선택하지 않았습니다.")
        return
    }
```

**// \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\***  
**// 6. 종교 유효성 체크하기**  
**// \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\***  
// 여러개중 하나 선택.

```
    var religion = document.memRegForm.religion.value;

    if(religion==""){

        alert("종교를 선택하지 않았습니다.")
        return;
    }
```

**// \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\***  
**//  7.  사진 유효성 체크하기 ( 사진입력은 필수가 아닌경우가 있다)**  
**// \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\***

```
    var pic = document.memRegForm.pic.value;

    if(pic==""){
        alert("사진은 필수 선택입니다.")
        return;
    }
```

**// \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\***  
**//   8.   자기소개 유효성 체크하기\*\*\*\*\*\*(\*\*공백제거 중요\*\*)**  
**// \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\***

```
    var introduce = document.memRegForm.introduce.value;

    while(introduce.indexOf(" ")>=0||introduce.indexOf("\n")>=0){

        introduce = introduce.replace(" ","");
        introduce = introduce.replace("\n","");

    }
    if(introduce==""){
        alert("자기소개를 작성해주세요.")
        return;
    }
```

**// \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\***  
**//  9.  사용자가 입력값을 잘못 입력했을 때 기존문자열 삭제하기**  
**// \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\***

```
    // document.memRegForm.userId.value = "";
    // document.memRegForm.pwd.value = "";
    // document.memRegForm.phone.value = "";
```

**// \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\***  
**//  10.  저장버튼 눌렀을 때 다시한번 확인하는 창 띄우기**  
**// \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\***

```
    if (confirm("정말 전송할까요?")==false){

        return;
    }
```

**// \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\***  
**//  11.  저장 버튼 눌렀을 때 서버로 데이터 보내고 URL 주소로 가기**  
**// \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\***

```
    document.memRegForm.submit();
```

```
}
</script>
```
