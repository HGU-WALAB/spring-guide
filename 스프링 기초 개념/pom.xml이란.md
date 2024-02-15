# pom.xml이란

## 스프링 프로젝트를 시작하고 Maven을 빌드 툴로 선택해야겠다! 하고 선택하면 프로젝트 내 pom.xml이라는 파일이 자동으로 생성된다. 이 파일은 뭘까?

pom.xml은 Maven의 정보를 담고있는 파일이다. 여기서 POM은 Project Object Model을 뜻하며 프로젝트 내 빌드 옵션을 설정하는 부분이다.

- pom.xml tag
  ```
  <project> : Maven의 XML 네임스페이스를 지정
  <modelVersion> : Maven의 model Version
  <groupId> : 그룹 ID태그
  <artifactId> : 아티팩트ID 태그
  <version> : 버전명 태그
  <packaging> 패키징 형식을 지정하는 태그
  <name> : 프로젝트의 이름
  <url> : Maven의 url
  <properties> : 프로젝트 관련 속성
  <parent> : pom.xml의 상속에 관련된 태그
  <dependencies> : 프로젝트가 의존하는 라이브러리들의 정보
  ```
