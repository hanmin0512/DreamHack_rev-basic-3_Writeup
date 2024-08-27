# DreamHack rev-basic-3 Writeup
워게임 주소: https://dreamhack.io/wargame/challenges/17/

## 정적 분석

### main 함수 분석

rev-basic-0,1,2 와 크게 다를게 없는 것을 알 수 있다.
sub_140001000함수를 분석해 보도록 하겠다.

<img width="516" alt="스크린샷 2024-08-27 오후 8 48 57" src="https://github.com/user-attachments/assets/52a9b0c7-48fa-48cd-ac64-07eb57989658">

### sub_140001000 함수 분석

아래 그림과 같이 입력 값을 배열로 한글자씩 가져와 1 x 16 + 8 = 24, 24글자를 비교한다.
비교 할 때 사용자 입력값을 순서 대로 가져와 비교한다.

비교 식:  [0 ~ 24] xor (배열[0 ~ 24] + 2 * [0 ~ 24])

<img width="553" alt="스크린샷 2024-08-27 오후 8 49 47" src="https://github.com/user-attachments/assets/48505370-b743-494b-adbf-2d671bc1f8e1">

byte_140003000 더블 클릭하여 확인.

<img width="814" alt="스크린샷 2024-08-27 오후 8 52 33" src="https://github.com/user-attachments/assets/2dc0d0a8-9113-4f27-8cda-dbf03a7c3648">

Hex_view를 통해 값 확인

<img width="682" alt="스크린샷 2024-08-27 오후 8 55 03" src="https://github.com/user-attachments/assets/70c642a0-24e8-4ed5-8168-cc59599eb057">

Shift + E를 눌러 값 확인
비교 식이 적용되어 나온 값이기 때문에 비교식을 역으로 해주기 위해 -2 * (0~24)를 한 후, xor 연산까지 해준다.

<img width="509" alt="스크린샷 2024-08-27 오후 8 56 13" src="https://github.com/user-attachments/assets/1b8300d6-8ea5-4775-818b-b35538d531c3">

bytes 값을 python을 활용해 비교식을 역으로 진행하여 결과 값을 확인 한다.

## 결론

<img width="566" alt="스크린샷 2024-08-27 오후 9 13 36" src="https://github.com/user-attachments/assets/0140da1c-3f4d-43d1-b343-e2bc3bc1bae6">

<img width="807" alt="스크린샷 2024-08-27 오후 9 23 09" src="https://github.com/user-attachments/assets/401684d6-adc7-4dfc-919e-19a71edc3dff">

