<h2>Django</h2>



<h3>MTV 패턴</h3>

* T (template) :사용자가 보이는 영역, html, css

* M(model) : Database, 데이터가 저장되는 곳
* V(view) : 데이터를 처리하는 곳, MTV중 핵심



- App : django를 이루는 작은 프로젝트 단위

  앱을 추가할때 앱을 인식시키는법

  project > settings.py >INSTALLED_APPS

  ```
  등록 규칙
  'project.apps.ProjectConfig',
  '이름.apps.이름(첫글자대문자)+Config',(콤마 추가)
  ```



<h5>웹사이트 구동순서</h5>

1. 사용자가 서버에 요청
2. 서버의 view는 model에게 요청에 필요한 데이터를 받음
3. view는 받은 데이터를 적절하게 처리해서 template으로 넘김
4. template은 받은 정보를 사용자에게 보여줌



웹사이트 구동작업

1. app생성
2. template제작
3. views제작
4. views와 url 연결