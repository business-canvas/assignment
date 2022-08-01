# Assignment

아래 사항들을 만족하는 리소스 관리 시스템 API를 구현해주세요.

## User Story

사용자는 리소스 관리 시스템을 통해 여러가지 리소스를 저장하고 연결해서 관리하고자 합니다.

- 리소스 저장
  - Document 리소스
    - Google Workspace 에서 제공하는 Document, Presentation, Spreadsheet 를 저장합니다.
  - URL 리소스
    - Youtube, 블로그 등 Document 를 제외한 어떤 URL 이든 저장합니다.
- 리소스 링크
  - URL 리소스(from)를 Document 리소스(to)로 연결할 수 있습니다.
- 리소스 불러오기
  - 리소스 리스트를 불러올 수 있습니다.
  - 특정 타입(Document or URL) 의 리소스 리스트를 불러올 수 있습니다.
  - 개별 리소스를 불러올 수 있습니다.
  - 각 리소스는 자신과 연결된 리소스 정보를 포함합니다.

## 판단 기준

- 기본기: 라이브러리 / 프레임워크를 얼마나 잘 사용하는가보다, ES6+ (혹은 TS) / SQL / OOP / FP / 테스트코드 / 도메인 설계 / 프로젝트 구조 설계 등에 대한 이해도가 얼마나 높은지가 중요합니다.

- 지속적으로 확장 가능한 구조: 단순히 작동하는 코드가 아니라 3년 정도 프로젝트를 진행해가면서 지속적으로 확장 가능한 구조인지가 중요합니다.

- 협업: 혼자 개발하기 쉬운 코드 보다 다른 사람들과 협업하기 좋은 코드인지가 중요합니다.

## 요구사항

- api.yaml에 정의되어 있는 API를 구현해 주세요
- 테이블은 필요에 따라서 자유롭게 만들어 주세요
- name field에는 이모지가 포함될 수 있습니다.

### 리소스 저장

#### Document 리소스

- Document 형식으로 저장하는 대상은 다음과 같습니다.
  - application/vnd.google-apps.document
  - application/vnd.google-apps.presentation
  - application/vnd.google-apps.spreadsheet
- docType은 다음과 같이 변환 해 주세요
  - document ⇒ doc
  - presentation ⇒ presentation
  - spreadsheet ⇒ sheet
- creator
  - 랜덤 string 값

#### URL 리소스

- 그밖의 모든 데이터는 URL형식으로 저장하시면 됩니다.
- 호스트가 Youtube(https://www.youtube.com/watch?v=-{paramId} 는 uri를 https://youtu.be/embed/{paramId} 로 변경해서 저장해 주세요
- protocol이 없거나 http인 URL은 [https://를](https://를) 붙여서 저장
- encodeURI는 decode해서 저장해 주세요.

#### 링크

- 링크는 Document가 아닌 타입에서 Document타입을 대상으로만 가능합니다.

### 기술 스택

- 언어는 무관합니다.
- 데이터베이스는 Relational Database 를 사용해주세요.
- 테스트 코드를 작성해주세요.
- 결과물은 docker 를 사용하여, 최대한 공유가 용이한 구조로 제작해주세요.
- 프레임워크 및 라이브러리는 아래 용도를 제외하고는 사용을 자제해주세요.
  - 서버 관련 프레임워크
  - ORM or Database 관련 라이브러리
  - 테스트 코드 관련 라이브러리
  - Date 관련 라이브러리
  - Validation 관련 라이브러리

## 참고

- [Open API spec](./api.yaml) 은 https://editor.swagger.io/ 혹은 https://stoplight.io/studio/ 를 사용해 보실 수 있습니다.
- 과제 결과물 구동 방법을 프로젝트의 [README.md](http://README.md) 에 남겨주세요.
- 시간이 조금 더 있었다면 추가하거나 개선할 수 있는 점을 남겨주세요.
