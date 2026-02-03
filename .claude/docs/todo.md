# TODO List

## Feature: 로그인/회원가입 기능

### DB (Database Layer)
- [ ] User 모델 생성
  - [ ] 필드: id, username, email, hashed_password, created_at, updated_at
  - [ ] 인덱스: username(unique), email(unique)
- [ ] User CRUD 함수 구현
  - [ ] create_user() - 회원가입용
  - [ ] get_user_by_username() - 로그인 인증용
  - [ ] get_user_by_email() - 이메일 조회용
  - [ ] get_user_by_id() - 사용자 정보 조회용

### BE (Backend API Layer)
- [ ] 회원가입 API
  - [ ] POST /api/auth/register
  - [ ] UserCreate 스키마 (username, email, password)
  - [ ] 비밀번호 해싱 (bcrypt)
  - [ ] 중복 체크 (username, email)
- [ ] 로그인 API
  - [ ] POST /api/auth/login
  - [ ] LoginRequest 스키마 (username, password)
  - [ ] 비밀번호 검증
  - [ ] JWT 토큰 발급 또는 세션 생성
- [ ] 사용자 정보 조회 API
  - [ ] GET /api/users/me
  - [ ] 인증 미들웨어/의존성 구현
- [ ] 로그아웃 API (필요시)
  - [ ] POST /api/auth/logout

### FE (Frontend UI Layer)
- [ ] 회원가입 페이지
  - [ ] /app/register/page.tsx 생성
  - [ ] 회원가입 폼 컴포넌트
  - [ ] 입력 검증 (이메일 형식, 비밀번호 강도)
  - [ ] API 연동 (POST /api/auth/register)
  - [ ] 성공/실패 메시지 표시
- [ ] 로그인 페이지
  - [ ] /app/login/page.tsx 생성
  - [ ] 로그인 폼 컴포넌트
  - [ ] API 연동 (POST /api/auth/login)
  - [ ] 토큰 저장 (localStorage 또는 cookie)
  - [ ] 로그인 성공 시 리다이렉트
- [ ] 인증 상태 관리
  - [ ] Context API 또는 상태 관리 라이브러리
  - [ ] 로그인 여부 확인
  - [ ] 보호된 라우트 구현
- [ ] 네비게이션 업데이트
  - [ ] 로그인/회원가입 버튼 (미로그인 시)
  - [ ] 로그아웃 버튼 (로그인 시)
  - [ ] 사용자 정보 표시

---

## 작업 순서 (권장)
1. **DB Layer** (db-agent) → User 모델 및 CRUD 생성
2. **BE Layer** (be-agent) → 회원가입/로그인 API 구현
3. **FE Layer** (fe-agent) → UI 구현 및 API 연동
