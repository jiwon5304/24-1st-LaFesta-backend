# 🐊라코스테 모티브의 의류상품 판매 플랫폼 프로젝트

### 유럽 프리미엄 브랜드, 라코스테 홈페이지를 모티브로 한 의류상품 판매 플랫폼 구현

## 프로젝트 소개
'라코스테' 홈페이지를 벤치마킹하여 의류 상품 판매 플랫폼 서비스를 구축했습니다. <br>
애자일 방법론을 채택하여 총 2주 간 스프린트 방식으로 프로젝트를 진행했습니다.<br>
사용자에게 편리한 서비스를 제공할 수 있는 방법을 고민하고 실행에 옮기는 것을 기초 목적으로 삼았습니다.<br><br>
효율적인 아키텍처 구축, 사용자 중심의 다양한 서비스를 제공하기 위해 효율적인 데이터 모델링 방안을 고민했습니다.<br>
최적화된 데이터베이스 사용을 목적으로 장고 ORM을 사용하였습니다.<br>

## BACKEND 개발팀
|이름   |담당 기능|
|-----|------------------------------|
|박지원 |DB 모델링, 회원가입 & 로그인 API, 데코레이터 함수, 검색 기능|
|주종민 |DB 모델링, 제품리스트 페이지 API, db_uploader|
|하예준 |DB 모델링, 제품 상세 페이지, 장바구니 API|


## 개발기간
- 2021/08/30 ~ 2021/09/10

## 시연 영상

<div id=header align="center">
  <a href="https://www.youtube.com/watch?v=epKkvWK1XUU">👉🏻 시연 영상 보러가기</a>
</div>

## 사용 기술 및 tools
### Backend
- Python
- Django
- Mysql

### ETC
- Git
- Github
- POSTMAN

## 모델링
<p align="center"><img src="https://user-images.githubusercontent.com/80395324/144576664-57cad092-fafc-462a-b454-4b9bdf86d410.png" width="1000" height="700"/></p>


## 구현기능
### 회원가입 API
- 이름, 성별, 이메일, 핸드폰번호, 비밀번호, 생년월일을 입력 받아 회원가입을 진행합니다.
- 입력받은 이메일과 비밀번호는 유효성 검사를 실시한 뒤 적합하지 않으면 에러를 반환합니다.
- 비밀번호는 bcrypt로 암호화를 진행해서 DB에 저장합니다.
- 이미 존재하는 이메일로 회원가입을 시도하는 경우 에러를 반환합니다.

### 로그인 API
- 이메일과 비밀번호로 로그인을 합니다.
- 로그인이 성공한 경우에는 JWT토큰을 발행합니다. 추후 인증된 유저만 접근이 가능한 페이지(장바구니)에 데코레이터 함수를 적용시키기 위함입니다.
- 토큰 발행 시 유저의 이름도 함께 반환하도록 구현하였습니다.

### 데코레이터 함수
- 토큰 값이 존재하지 않는 경우 에러를 반환하도록 기능을 구현하였습니다.
- decode한 토큰값이 유효하지 않는 경우 에러를 반환하도록 기능을 구현하였습니다.

### 검색 기능
- Q객체를 사용하여 대소문자를 구분하지 않고 검색 하도록 구현하였습니다.


## 폴더 구조
```bash
├── README.md
├── branch.csv
├── config
│   ├── __init__.py
│   ├── asgi.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── core
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── migrations
│   │   └── __init__.py
│   ├── models.py
│   ├── tests.py
│   ├── utils.py
│   └── views.py
├── db_uploader.py
├── image.csv
├── manage.py
├── my_settings.py
├── orders
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── migrations
│   │   ├── 0001_initial.py
│   │   ├── 0002_alter_orderitemstatus_status.py
│   │   ├── 0003_auto_20210903_2114.py
│   │   ├── 0004_auto_20210906_2002.py
│   │   └── __init__.py
│   ├── models.py
│   ├── tests.py
│   ├── urls.py
│   └── views.py
├── product.csv
├── products
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── migrations
│   │   ├── 0001_initial.py
│   │   └── __init__.py
│   ├── models.py
│   ├── tests.py
│   ├── urls.py
│   └── views.py
├── products_colors.csv
├── products_sizes.csv
├── pull_request_template.md
├── requirements.txt
├── second.csv
└── users
    ├── __init__.py
    ├── admin.py
    ├── apps.py
    ├── migrations
    │   ├── 0001_initial.py
    │   └── __init__.py
    ├── models.py
    ├── tests.py
    ├── urls.py
    └── views.py
```

## TIL정리 (Blog)
- 회고록 :  
- 관련기술 : 

## ❗️ Reference
이 프로젝트는 라코스테 홈페이지를 참조하여 학습목적으로 만들었습니다.<br>
실무수준의 프로젝트이지만 학습용으로 만들었기 때문에 이 코드를 활용하여 이득을 취하거나 무단 배포할 경우 법적으로 문제될 수 있습니다.<br>
이 프로젝트에서 사용하고 있는 사진 대부분은 위코드에서 구매한 것이므로 해당 프로젝트 외부인이 사용할 수 없습니다.
