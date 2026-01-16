## 암호화(Encryption)
- 데이터를 키(key) 를 사용해 알아볼 수 없게 변환하고,같은 키 또는 대응되는 키로 다시 복원(복호화) 할 수 있는 기술
- 대표 알고리즘으로 대칭키에는 AES,DES공개키에는 RSA, ECC 등이 있다.
## 대칭키 vs. 공개키 
> 대칭키 (Symmetric Key algorithm)
<img width="1309" height="631" alt="image" src="https://github.com/user-attachments/assets/1ec3310a-a2ea-4657-bfc5-7a8af4eb47df" />

- 지금껏 널리 사용되어옴
- 중간에 누가 훔쳐보더라도 알아볼수 없음
- 그러나 어떻게 이 동일한키를 애초에 양쪽에 공유하느냐????
- 결국 한번은 한쪽에서 다른 한쪽으로 이 키를 전송해야함... << 누군가 훔쳐본다면???

> 공개키;비대칭키 (public-key cryptography)
<img width="1282" height="626" alt="image" src="https://github.com/user-attachments/assets/a27af65d-2b4d-4cbb-9d60-410f9abc0816" />

- 서로 다른 두 개의 키가 사용됨(비대칭키)
- 예를들어, A키로 암호화하면 B키로만 복호화 가능
- 네이버 서버는 이 두 키중 하나는 비밀로 보관하고(개인키), 다른하나를 대중들에게 공개함(공개키)
- 사용자는 공개키로 비밀번호를 암호화해서 네이버에 보냄
- 누가 가로채면?? 같은 공개키로는 암호문을 풀어낼수 없음
- 볼수있는건?? 개인키를 가진 네이버만.

## 해시(Hash) 
- 임의 길이의 데이터를 고정 길이의 값(해시값) 으로 변환하는 함수
- 복호화 불가능
- 같은 입력 → 항상 같은 해시값
- 입력이 조금만 바뀌어도 해시값은 완전히 달라짐
- 종류로는 SHA-1, SHA-256, MD5, CRC, Argon2, Bcrypt 등이 있다.

## 보안과 해시
- 원본 데이터와 다른 입력값이 (예컨대 복사본이나 키보드 입력으로 입력 받은 비밀번호가) 같은지 확인하는 작업을 둘의 해시값을 대신 비교하는 것으로 갈음할 수 있다.
- 비밀번호, 전자서명, 전자투표, 전자상거래와 같은 민감한 입력의 무결성을 검증할 때 사용됨
<br /><br />
<img width="476" height="527" alt="image" src="https://github.com/user-attachments/assets/e3d06e33-7ce1-4fa7-a787-d398a1e6f2cd" /> <br /><br />
<img width="486" height="588" alt="image" src="https://github.com/user-attachments/assets/26fb7fe1-1a79-4276-9482-457d93befe5f" /> <br /><br />
- 따라서 서버에서는 비밀번호 원본이 아닌 해시값을 저장해야 한다. 



## 눈사태 효과(Avalanche Effect)
- 원문(Plaintext)의 한 비트의 변화가 최종 암호문(Ciphertext)에 큰 변화를 주는 효과
<img width="732" height="194" alt="image" src="https://github.com/user-attachments/assets/9ee8cf67-c9f0-438f-bed3-e0acd55a9254" />


## salt

## 레인보우 테이블(Rainbow Table)

## 브루트 포스(Brute Force)


## bcrypt

## passlib
