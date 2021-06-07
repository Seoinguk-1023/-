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

   

<h3>서버 구동순서</h3>

1. python -m venv myvnev (가상환경 생성)

2. source myvenv/Scripts/activate(가상환경 실행)

3. pip install django (장고 설치)

4. django-admin startproject 프로젝트이름(프로젝트 생성)

5. cd 프로젝트이름 (프로젝트로 들어가기)

6. python manage.py startapp 앱이름(앱 생성,추가)

7. project setting.py 에 들어가 istalled.apps추가하기

   ```
   ex) 앱이름 asdf일시,
   'asdf.apps.AsdfConfig',
   ```

8. 앱폴더 하위로 template 만들어 html 제작.

9. 웹사이트 구동
   1. app생성
   2. template제작
   3. views제작
   4. views와 url 연결
10. python manage.py runserver(서버구동)

<h4>템플릿 문법</h4>

```{% for ~~ %}
{% for ~~~ in wordDict %}
...
{% endfor %}
```

변수명 사용시 중괄호 2개 : {{변수명}}



<h2>Django와 데이터베이스</h2>



* class = 붕어빵 틀과 비슷함, 내용은 다르지만 데이터를 저장하는 틀을 만들어줌

  

```
makemigrations : 앱 내의 migration 폴더를 만들어서 models.py 의 변경사항을 저장

migrate : migration 폴더를 실행시켜 데이터 베이스에 적용시키는 명령어
```



저장된 migration 한 database는 /admin 을 통해서 들어갈 수 있는데 superuser을 생성 후 admin.py에

```
from .models import Blog
# Register your models here.
admin.site.register(Blog)
모델을 등록해야 사용 가능.
```



<h3>CRUD</h3>

create, read, update, delete

<h4> READ </h4>



<h4> CREATE </h4>

* 함수생성
  1. new : new.html 보여줌
  2. create : 데이터베이스에 저장

* http 요청방식 

  ```
  Get 
  > 데이터를 얻기위한 요청
  > 데이터가 url에 보임
  Post
  > 데이터를 생성하기 위한 요청
  > Csrf 공격 방지
  ```

  