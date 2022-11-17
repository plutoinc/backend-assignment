# Short URL Generator

- 길고 못생긴 `destination URL` 대신 귀엽고 깜찍한 `short URL`을 만들 수 있는 서비스를 구현합니다.
- https://bitly.com/ 와 같은 URL shortening 서비스를 참고합니다.

## Requirements

- 아래 `Page Requirements` 에 명시된 요구사항을 만족하는 웹 서비스를 구현합니다.
- 유저가 생성한 `short URL` 정보와 `access log`는 웹 서버의 상태와 상관없이 보존되어야 합니다.

## Non-goal

- web framework, library, DB 선택에는 제한이 없습니다.
- 페이지 디자인은 평가 대상이 아닙니다. `index.html`, `detail.html`, `error.html`을 참고해 구현해주세요.
- 서비스를 웹에 배포하는 것은 필수는 아니지만, 보너스 점수를 받을 수 있습니다.

## Page Requirements

### Home Page

- Page URL: `/`
- `destination URL`에 대한 `short URL`을 생성할 수 있습니다.
- 동일한 `destination URL`을 입력하면 매번 다른 `short URL`을 생성합니다.
- `short URL`이 생성되면 해당 `short URL`의 detail 페이지로 이동합니다.
- `index.html` 파일을 참고해 화면을 노출합니다.

### Short URL

- Page URL: `/{short URL}`
- URL 접근시 `short URL`에 매핑된 `destination URL`로 redirect 시킵니다.
- URL 접근시 클라이언트 `access log`를 남깁니다.

### Short URL Detail Page

- Page URL: `/{short url}/detail`
- 생성된 `short URL`의 상세 정보를 확인할 수 있습니다.
- 생성된 `short URL`로의 `access log`를 확인할 수 있습니다.
- `detail.html` 파일을 참고해 화면을 노출합니다.

#### URL Details

| Name            | Description       |
|-----------------|-------------------|
| Destination URL | 원본 url link       |
| Short URL       | short url link    | 
| Created At      | short url이 생성된 시간 |
| Total Clicks    | short url 클릭 횟수   | 
| Last Clicked At | 마지막 클릭 시간         |

#### Access Log

| Name       | Description      |
|------------|------------------|
| IP         | 클라이언트 IP         |
| User Agent | 클라이언트 user agent |
| Referrer   | 이전 페이지 referrer  |
| Clicked At | 클릭한 시간           |

### Error Page

- 유효하지 않는 `short url`로 접근한 경우 `error.html` 파일을 참고해 화면를 노출합니다.

## Bonus

- 인증 기능을 구현하는 경우 보너스 점수를 받을 수 있습니다.
    - `short URL` 생성시 비밀번호를 입력받고, 상세 페이지를 조회시 인증받은 세션에서만 페이지를 조회할 수 있습니다.
- 서비스를 웹에 배포하는 경우, 보너스 점수를 받을 수 있습니다. 
