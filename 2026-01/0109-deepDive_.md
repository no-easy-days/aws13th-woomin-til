## 유효성검사 (Validation)
- 잘못된 데이터 입력을 방지하기 위한 기능 <br/><br/>
> 엑셀 예시
<img width="1231" height="466" alt="스크린샷 2026-01-09 142612" src="https://github.com/user-attachments/assets/2317dc63-0623-4138-ab9b-2eff86529a27" />
<br/><br/><br/>

## 직렬화 (Serialization)
- 객체를 저장 가능하거나 전송 가능한 형태로 (연속된)문자열 또는 바이트로 전환하는 과정 
> 왜?
- 객체 : 메모리에 존재하고 추상적 / String,bytes : 드라이브에 저장 또는 통신선을 통해 전송 <br/><br/>

> 1번 컴퓨터의 객체를 2번 컴퓨터로 전송
<img width="1203" height="620" alt="스크린샷 2026-01-09 150450" src="https://github.com/user-attachments/assets/7058e1ae-30b0-4070-9f9d-43116846d12c" />
<br/><br/>

> 객체에서 JSON파일로 직렬화 해서 전송
<img width="1254" height="630" alt="스크린샷 2026-01-09 150138" src="https://github.com/user-attachments/assets/bea2d0c2-42cf-4994-bdbb-595d133e3c97" />
<br/><br/>

## 데이터 무결성 (Data Integrity)
- 데이터의 정확성과 일관성이 보장된 상태를 위하여 비인가자로부터 데이터를 보호하는 성질
<br/><br/>

## 스키마(Schema)
- (철학)체계적으로 완성하다.
- 데이터베이스의 구조(개체,속성,관계)에 대한 정의
<br/><br/>

## JSON(JavaScript Object Notation)
<img width="849" height="552" alt="스크린샷 2026-01-09 153444" src="https://github.com/user-attachments/assets/f410a962-de0a-4c37-932b-77e3fa9e956a" />
<br/><br/>

## API(Application Programming Interface)
- 앱이 프로그래밍 언어로 상호작용 할때의 규칙(경계면) <br/><br/>
> 카카오책 검색 API 가이드 예
<img width="1260" height="756" alt="스크린샷 2026-01-09 153717" src="https://github.com/user-attachments/assets/59e84192-897f-4f9a-bc53-54eb5f65e560" />
<br/><br/>

## Fast API
- Python 3.7+ 버전의 표준 타입 힌트(Type Hints)를 기반으로 API를 구축하기 위한 현대적이고 빠른(고성능) 웹 프레임워크
- 데이터 유효성 검사, 직렬화 및 자동 문서 생성을 위해 Pydantic 라이브러리를 핵심적으로 활용
<br/><br/>

## Type Hint
- 이 변수·함수에는 이런 타입이 들어올 거다”라고 미리 적어 두는 표기법
<img width="870" height="713" alt="image" src="https://github.com/user-attachments/assets/d6cd7578-54e0-490d-aced-b4a72ea90ae1" />


## Pydantic
- 타입 힌트를 이용해 데이터 검증과 setting 관리를 해주는 라이브러리
> 데이터 파싱(Parsing): 단순히 "틀렸다"고 말하는 게 아니라, 데이터를 적절한 타입으로 변환하려고 시도 (ex. 문자열 "123"을 정수 123으로 자동 변환)
<img width="1281" height="618" alt="image" src="https://github.com/user-attachments/assets/0d32420f-31ff-4092-99b9-fc1b2f66dbf5" />

<img width="1280" height="630" alt="image" src="https://github.com/user-attachments/assets/4ffd9974-46aa-4683-9bac-f6664adf9ba3" />


<br/><br/>

## 회원가입 폼에서 이메일 주소 칸에 '안녕하세요'라고 적으면??
- 서버 입구에서 유효성 검사에 걸려 요청이 거부됨
<img width="442" height="374" alt="스크린샷 2026-01-09 160020" src="https://github.com/user-attachments/assets/fea1d0a9-d714-4868-a4e4-a0ab4ac62b69" />
<br/><br/>

## 데이터가 서버 로직(함수) 안으로 들어오기 전에 문지기가 막아주는 것과, 들어와서 에러가 나는 것의 차이는?
- 데이터를 서버 로직에 전달하기 전에 유효성 검사로 차단하면
잘못된 입력이 내부로 침투하지 않아 서버 안정성과 책임 분리가 명확해지지만,
로직 내부에서 에러가 발생하면 서버 오류로 처리되어 신뢰성과 유지보수성이 떨어진다.
<br/><br/>

## FastAPI의 단짝 친구인 Pydantic은 어떻게 파이썬의 타입 힌트(age: int)만 보고 검사 코드를 자동으로 만들어주는가?
- Pydantic이 타입 힌트를 해석해서 자동 검증 로직 생성
<br/><br/>

## 과거에는 개발자가 if type(age) != int: 같은 코드를 수십 줄씩 짰다고한다. Pydantic을 사용한다면 어떻게 코드가 바뀌게 되는지?
- 수십 줄의 if 검사 코드가 “선언 한 줄”로 바뀐다. <br/><br/>
> 과거
<img width="807" height="780" alt="image" src="https://github.com/user-attachments/assets/b0e45d69-c80c-446b-9260-d2aba77331f1" />
<br/><br/>
> Pydantic을 사용
<img width="654" height="486" alt="image" src="https://github.com/user-attachments/assets/9465b8ac-ecf3-4547-884c-3b555b3388d8" />

