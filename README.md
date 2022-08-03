## 현재 아키텍처 구조 (08.02)

```
- src 
	- controller
		- excontroller // 운동기능 추가 컨트롤러 CRUD
			-create.js ..
		- routinecontroller // 루틴 추가 컨트롤러 CRUD
			- create.js ..
		- sharecontroller // 공유 컨트롤러 
			- share.js
		- signcontroller // 유저(회원가입, 로그인 등..) 컨트롤러
			- accessToken.js
			- index.js  // 회원가입, 탈퇴, 로그인,로그아웃
			- oauth.js  // 소셜 로그인 (네이버, 구글)
			- refreshToken.js
		- testcontroller // 테스트 컨트롤러 (테스트 케이스 아님..)
			- index.js
	- orm
		- sequelize
			- config
			- migrations
			- models
				-index.js
				-user.js
				-routinepart.js
				-routine.js
				-exercise.js
			- seeders
	- public
		- image		
	app.js 
- tests
	- test.js // jest test 
```

## 실행 방법

1. `npm i` // 인스톨

2. `npm start` // app.js 실행됨. 

   ![스크린샷, 2022-07-28 20-31-12](https://user-images.githubusercontent.com/71261997/181495125-b0b7b3e8-ab0f-4a95-bdc4-65e3eed35916.png)

## 데이터베이스 마이그레이션

1. `npx sequelize db:migrate`

2. `npx sequelize-cli db:seed:all`

3. `npm start`

   

## 리팩토링 방향

1. 에러와 버그 상황에 잘 대처가 가능하도록 SRP 원칙에 충실히 할것
	- 의존방향이 꼬이지않게 해야함.
	- 명확한 네이밍.
	- 추가 확장 및 수정사항에 용이한 구조를 가질것
2. 커밋 메세지에 신경쓸것 (이슈와 연동)
3. 객체 지향적으로 리팩토링하기

