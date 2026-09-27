Key Learning:

    HTML Form 구조 설계: action, method 속성의 이해와 함께, 데이터를 입력받기 위한 다양한 폼 
    요소(input, select, checkbox, radio)의 활용법을 익혔습니다.

    CSS를 통한 UI/UX 개선: 뼈대만 있는 HTML 요소에 padding, border, box-shadow 등을 
    적용하여 레이아웃을 다듬고, :focus와 :hover 가상 클래스로 사용자 상호작용을 시각화하는 방법을 배웠습니다.

    Validation: HTML 속성(required, minlength)을 이용한 1차 검증과 JavaScript
    (checkValidity(), preventDefault())를 이용한 2차 검증을 결합하여 잘못된 데이터 전송을
     막는 방벙을 배웠습니다.

Form Elements:

    <input type="text">, <input type="email">: 사용자명, 이메일, 주소 등 텍스트 데이터를
     입력받는 데 사용했습니다.

    <input type="radio">: 결제 수단처럼 단일 선택이 필요한 항목에 활용했습니다.

    <input type="checkbox">: 청구지 주소 동일 여부, 정보 저장 동의 등 선택/해제가 가능한 
    옵션에 적용했습니다.

    <select> & <option>: 국가 및 도 선택 시 목록을 제공하여 입력을 선택가능하게 했습니다.


    <button type="submit">: 작성된 폼 데이터를 검증하고 제출하는 이벤트를 발생시키는 용도로 
    사용했습니다.

    <fieldset> & <legend>: 관련된 폼 요소들(청구지 주소, 결제 정보 등)을 그룹화하고 시각적 
    단서를 제공했습니다.

HTML vs CSS: 

    form1.html : 웹페이지의 정보 구조를 잡는 데 집중한 뼈대입니다. 시각적인 정렬이나 여백이 
    없어 요소들이 세로로 딱딱하게 나열되어 있습니다. 전체적으로 브라우저의 
    기본적인 스타일로만 이루어졌습니다.

    form1_css.html : 뼈대 위에 CSS 스타일을 입혀 디자인을 했습니다. Flexbox를 활용하여 중앙
     정렬을 맞추고, border-radius로 모서리를 둥글게 처리했으며, 입력창 클릭 시 초록색 테두리
     (:focus)가 생기게 하거나 버튼에 마우스를 올렸을 때 색상이 변하게(:hover) 하여 시각적으로
    보기 편하게 만들었습니다.

Validation & JS: 

    적용 조건: 필수 입력(required), 이메일 형식 지정(type="email"), 사용자명 최소 6자 이상
    (minlength="6").

    처리 과정:

    1.addEventListener("submit", ...)로 제출 버튼 클릭 이벤트를 감지합니다.

    2.폼이 바로 넘어가는 것을 막기 위해 event.preventDefault()를 호출하여 동작을 차단합니다.

    3.checkValidity() 메서드를 사용해 각 요소가 HTML 조건(빈칸, 이메일 형식, 최소 길이)을 
    만족하는지 검사합니다.

    4.조건에 맞지 않으면 경고 alert() 메세지를 띄우고, focus()를 사용해 오류가 발생한 
    입력창으로 커서를 이동시킨 뒤 return으로 함수를 즉시 종료합니다.

    5.모든 조건을 통과하면 최종적으로 성공 alert() 메시지를 출력합니다.

Problem & Solution: 

    사용자명이 6자 미만일 때 자바스크립트로 띄우려는 알림창 대신 브라우저 자체의 영어 메세지가 
    먼저 등장하여 제가만든 경고 메세지가 나오지않았습니다. <form> 태그 속성에 novalidate를
     추가하여 브라우저의 기본 메세지을 비활성화하고, JavaScript만 작동하도록 하여 해결했습니다.


Reflection: 

    자바스크립트로 모든 조건을 일일이 코딩하지 않아도, HTML 태그의 속성과 자바스크립트의 
    checkValidity() 함수 하나를 연결하면 효율적인 조건검사가 가능하다는 점을 배웠습니다.
