# 🧩 Real Estate Auction Platform (Frontend & Backend)

본 프로젝트는 **블록체인 기반 부동산 경매 시스템**의 프론트엔드 및 백엔드 구현 코드입니다.  
Django 기반의 백엔드와 템플릿 기반의 프론트엔드로 구성되어 있으며,  
Solidity 스마트컨트랙트와의 연동을 고려해 설계되었습니다.

⚠️ 현재 일부 기능은 미완성 상태이며, 온체인 연동은 부분적으로만 구현되었습니다.


## 📌 프로젝트 개요

- **목표**: 부동산 경매 절차의 투명성과 자동화 향상을 위한 웹 기반 경매 시스템 구현
- **기획**: 블록체인 위에서 입찰 데이터를 관리하고 낙찰 및 미납자 처리를 자동화하는 구조
- **역할**: 입찰 로직 설계, 스마트컨트랙트 구현 및 테스트, web3.py 기반 백엔드 연동 기능 개발

## 역할

| 이름 | 역할 |
| :--- | :--- |
| **최윤기** | 블록체인 스마트컨트랙트 개발, 구조 설계 |
| 김성준 | DB |
| 민수빈 | 프론트엔드 개발 |
| 이민지 | 백엔드 개발 |

## 🧱 기술 스택

- 프론트엔드 : HTML, CSS, JavaScript, Django Template 
- 백엔드 : Python, Django  
- 블록체인 연동 : web3.py (서버에서 스마트컨트랙트 함수 호출)    
- 테스트 도구 : Hardhat (Solidity 컨트랙트 테스트)   
- 인덱싱/질의 : The Graph (GraphQL 기반 블록체인 서브그래프 구축 및 질의)  
- 데이터베이스 : SQLite (개발용)   

## 📊 설계

<details>
<summary>structure</summary>
<br>
<img width="643" height="351" alt="image" src="https://github.com/user-attachments/assets/d85472bb-4d57-4cb4-8ae1-90967fe606ad" />
<br>
<img width="310" height="78" alt="image" src="https://github.com/user-attachments/assets/1180e6dc-482c-4c27-be22-c173b665f3a4" />
<img width="315" height="85" alt="image" src="https://github.com/user-attachments/assets/140cd032-543c-417d-845b-8b9f11511129" />


</details>

<details>
<summary>스마트 컨트랙트 구조</summary>
<br>
<img width="580" height="236" alt="image" src="https://github.com/user-attachments/assets/fb0c8ef1-6bf7-4a48-b8d8-e782ade540da" />
<img width="608" height="280" alt="image" src="https://github.com/user-attachments/assets/8f516417-ba3f-40c5-90b3-4b6e72a0fa8d" />



</details>



## ⚙️ 주요 기능

### ✅ 프론트엔드
- 입찰서 작성 및 제출 페이지
- 낙찰 여부 및 입찰 내역 조회
- 입찰자 주소와 로그인 유저 비교 후 `(나)` 표시 등 시각화 처리

### ✅ 백엔드
- Django 기반 API 서버 구성
- web3.py를 이용한 스마트컨트랙트 호출 기능 구현
- 입찰 처리, 낙찰자 확인 로직 설계
- 오프체인 및 온체인 로직 분리 설계


## 🧩 스마트컨트랙트 연동

- Ethereum 네트워크의 레이어 2 솔루션인 Arbitrum 네트워크 활용
- 컨트랙트는 **입찰 등록**, **예치금 관리**, **낙찰 확정 및 미납자 처리** 등의 기능을 수행
- Solidity 기반으로 직접 개발 및 Hardhat으로 테스트 완료
- Chainlink Keeper와의 연동을 고려한 자동화 구조 포함

🔗 스마트컨트랙트 코드: (https://sepolia.arbiscan.io/address/0xa83a9bbd6ff325827074a54ea6fb86fb40ceb536#code))

## 화면

<details>
<summary>메인 화면</summary>
<br><img width="1058" height="672" alt="image" src="https://github.com/user-attachments/assets/fe80e2dd-e116-4849-9738-46dab47ef293" />

</details>

<details>
<summary>검색 기능</summary>
<br><img width="870" height="604" alt="image" src="https://github.com/user-attachments/assets/4c9fe65c-51d8-42d0-8000-6185d81b5af0" />

</details>

<details>
  <summary>입찰표 작성</summary>
<br>
<img width="858" height="726" alt="image" src="https://github.com/user-attachments/assets/a4d57f48-9ad4-4560-a406-0ed8588027fc" />
<img width="914" height="726" alt="image" src="https://github.com/user-attachments/assets/fc4f0a43-0b57-47ce-9de9-b678cdc9e9cd" />


</details>

<details>
<summary>블록체인 지갑 연동 확인</summary>
<br>
<img width="642" height="782" alt="image" src="https://github.com/user-attachments/assets/ddb15b40-3884-47d4-975d-919054b02c4a" />

</details>

<details>
<summary>관심 목록</summary>
<br>
  <img width="1130" height="776" alt="image" src="https://github.com/user-attachments/assets/22083d09-d047-4dc4-9605-09ef02efa160" />


</details>

<details>
<summary>내역 조회</summary>
<br>
<img width="1238" height="362" alt="image" src="https://github.com/user-attachments/assets/3a7ec060-20e5-44e3-8033-bc59045925cd" />
<img width="1106" height="490" alt="image" src="https://github.com/user-attachments/assets/209be161-75be-435b-a4c3-ccd5a79351c6" />


</details>

<details>
<summary>ai 챗봇 상담원</summary></summary>
<br>
<img width="1124" height="772" alt="image" src="https://github.com/user-attachments/assets/63f3f4fb-6451-48db-bb6a-5b02ca42a94c" />


</details>
