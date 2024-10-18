# java-calculator-precourse

# **문자열 덧셈 계산기**
## **기능 요구 사항**

입력한 문자열에서 숫자를 추출하여 더하는 계산기를 구현한다.

- 쉼표(,) 또는 콜론(:)을 구분자로 가지는 문자열을 전달하는 경우 구분자를 기준으로 분리한 각 숫자의 합을 반환한다.
    - 예: "" => 0, "1,2" => 3, "1,2,3" => 6, "1,2:3" => 6
- 앞의 기본 구분자(쉼표, 콜론) 외에 커스텀 구분자를 지정할 수 있다. 커스텀 구분자는 문자열 앞부분의 "//"와 "\n" 사이에 위치하는 문자를 커스텀 구분자로 사용한다.
    - 예를 들어 "//;\n1;2;3"과 같이 값을 입력할 경우 커스텀 구분자는 세미콜론(;)이며, 결과 값은 6이 반환되어야 한다.
- 사용자가 잘못된 값을 입력할 경우 `IllegalArgumentException`을 발생시킨 후 애플리케이션은 종료되어야 한다.

## 구현 기능 목록

### 빈 문자열의 처리

- [ ]  입력이 “” 일때, 0으로 인식하도록 구현하기

### 쉼표(,)와 콜론(:)을 구분자로 사용하는 기본 덧셈

- [ ]  쉼표(,) 또는 콜론(:)을 구분자로 사용하는 기본적인 덧셈 기능을 구현하기
    - 예: `"1,2" => 3`, `"1,2:3" => 6`

### 커스텀 구분자의 처리

- [ ]  문자열 앞부분의 "//"와 "\n" 사이에 커스텀 구분자로 사용커스텀 구분자가 포함된 경우 이를 처리하는 기능을 추가하기
    - 예: `"//;\n1;2;3" => 6`

### 숫자 추출 및 실제 덧셈 로직

- [ ]  구분자를 기준으로 숫자를 추출하고, 해당 숫자들을 더하는 기능을 구현하기

### 예외 처리

- [ ]  ‘잘못된’ 입력이 들어온 경우, `IllegalArgumentException`을 발생시키는 예외 처리 로직을 구현하기
    - [ ]  **음수가 입력된 경우**: 입력 조건은 **구분자와 양수로 구성된 문자열**이므로 **음수**가 들어왔을 때 예외를 발생시킨다
    - [ ]  **숫자가 아닌 입력의 경우:** 숫자와 구분자 외에 다른 문자가 입력된 경우 예외를 발생시킨다
        - 예: `"1,a,3"` 또는 `"1,2:b"` → `IllegalArgumentException` 발생
    - [ ]  **구분자가 연속으로 나타난 경우:** 기본 구분자(쉼표, 콜론) 또는 커스텀 구분자가 연속으로 나타난 경우 예외를 발생시킨다
        - 예: `"1,,2"` 또는 `"1::2"` → `IllegalArgumentException` 발생
    - [ ]  **입력 문자열이 구분자로 시작하거나 끝나는 경우**: 입력 문자열의 시작 또는 끝이 구분자인 경우 예외를 발생시킨다
        - 예: `“,1,2”`, `"1,2,"` → `IllegalArgumentException` 발생
    - [ ]  공백이 포함된 경우: 입력 문자열에 불필요한 공백이 포함된 경우 예외를 발생시킨다
        - 예: `"1, 2"` 또는 `"1 ,2:3 "` → `IllegalArgumentException` 발생

### 최종 계산값 출력

- [ ]  덧셈 결과를 출력하는 기능을 구현하기