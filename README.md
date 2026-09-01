# 화상 채팅 만들기 (Zoom 클론)

**Node.js에서 실시간 통신을 익히려고 만든 화상·채팅 서버 연습입니다.**

WebSocket(`ws`)으로 먼저 만들어보고, 같은 기능을 Socket.IO로 다시 구현하며 둘의 차이를 확인했습니다.

## 구성

```
src/
├── server.js          # Express + http 서버 위에 Socket.IO 얹기
├── views/home.pug     # 화면 템플릿
└── public/js/app.js   # 브라우저 쪽 소켓 클라이언트
```

## 노트

`WebSocket으로 개발한 코드/` 폴더에 Socket.IO로 넘어가기 **전** 단계의 코드를 남겨뒀습니다.

- [`serverJs.md`](./WebSocket으로%20개발한%20코드/serverJs.md) — 순수 `ws` 서버
- [`appJS.md`](./WebSocket으로%20개발한%20코드/appJS.md) — 브라우저 클라이언트
- [`homePug.md`](./WebSocket으로%20개발한%20코드/homePug.md) — 템플릿

**`ws`는 메시지가 그냥 문자열입니다.** 누구에게 보낼지, 무슨 종류의 메시지인지를 전부 직접 정해야 해서 JSON에 타입을 넣어 구분하게 됩니다. Socket.IO는 이벤트 이름과 방(room) 개념을 이미 갖고 있어서 그 부분이 사라집니다. 대신 Socket.IO는 순수 WebSocket이 아니라서 클라이언트도 같은 라이브러리를 써야 합니다.

## 실행

```bash
npm install
npm run dev        # http://localhost:3000
```

---

> 학습용 저장소입니다.
