# Assignment
아래의 조건을 만족하는 강의 시스템 API를 구현해주세요.

모든 테이블/프로젝트 구조는 본인이 아는 선에서 가장 좋은 형태로 만들어 주세요.

직접 서비스 한다는 생각으로 최대한 협업하기 좋고, 견고하고, 구조화되고, 확장에 열려 있는 구조로 프로젝트를 만들어주세요.

라이브러리 / 프레임워크를 얼마나 잘 사용하는가보다, ES6+ (혹은 TS) / SQL / OOP / FP / 테스트코드 / 도메인 설계 / 프로젝트 구조 설계 등에 대한 이해도가 얼마나 높은지가 중요합니다.

## 요구사항
- api.yaml에 정의되어 있는 API를 구현해 주세요
- 테이블은 필요에 따라서 자유롭게 만들어 주세요
- name field에는 이모지가 포함될 수 있습니다.
# 세부 요구사항
### 리소스 저장
#### File 리소스
  - 패스는 foo/boo/{randomString}.{ext}로 변환해 주세요 
  - size는 랜덤으로 넣어주시면 됩니다.
  - File 형식으로 저장하는 대상은 다음과 같습니다.
    - application/pdf, application/octet-stream
    - image/png등 이미지 파일
    - video/mp4등 비디오 파일
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
  - origin
    - 랜덤 string 값
#### URL 리소스
 - 그밖의 모든 데이터는 URL형식으로 저장하시면 됩니다.
 - 호스트가 Youtube(https://www.youtube.com/watch?v=-{paramId} 는 uri를 https://youtu.be/embed/{paramId} 로 변경해서 저장해 주세요
 - protocol이 없거나 http인 URL은 [https://를](https://를) 붙여서 저장 
 - encodeURI는 decode해서 저장해 주세요.

#### 링크
- 링크는 Document가 아닌 타입에서 Document타입을 대상으로만 가능합니다.

### 기술 스택
- 언어는 무관합니다. 단 javascript, typescript 의 사용을 우대합니다.
- 데이터베이스는 RDB 의 사용으로 제한합니다.
- 테스트 코드를 작성해주세요.
- docker 를 사용하여, 최대한 공유가 용이한 구조로 제작해주세요.
- 프레임워크 및 라이브러리 제한사항
  - 서버 관련 프레임워크
  - orm
  - 테스트 코드 관련 라이브러리
  - date 관련 라이브러리
  - validation 관련 라이브러리
- 위 참고 관련 프레임워크 및 라이브러리를 제외한 다른 프레임워크 및 라이브러리의 사용을 자제해주세요.

## 참고
- API는 https://stoplight.io/studio/ 를 사용해서 보시는게 가장 좋습니다.
- 과제에 대한 구동 방법에 대해서 [README.md](http://README.md) 에 남겨주세요.
- 시간이 조금 더 있었다면 추가하거나 개선할 수 있는 점을 남겨주세요
