# ruby-on-rails

## index

## links

* doc
    - [http://guides.rubyonrails.org/](http://guides.rubyonrails.org/)
* lecture
    - [http://onoffmix.com/event/82501](http://onoffmix.com/event/82501)
    - [http://onoffmix.com/event/82502](http://onoffmix.com/event/82502)
* repo
    - [https://github.com/cycorld/todo-list](https://github.com/cycorld/todo-list)

---

* 문법이 열려있음
    - 하나코드를 짤대 여러 방식으로 짤 수있음
        + 성향별 선호도 존재
* 일본에서 만들어짐
    - like psesudo
* 대용량 프로젝트는 비추천
    - 2.0 에서 성능 개선
    - 토이 프로젝트
* cloud9
    - [c9.io](c9.io)
    - cloud ide
    - amazon.com
* cmd
    - install bundle
        + gem install rails --no-document
* 철학
    - 컨트롤러 핏
    - 모델 팻
* rails g model Todo item:string complete:boolean
    - db/.../*.rb
        + , null: false
        + , default: false
    - DB에 따라 다르게 설정 할 필요 없음
* cmd
    - rails c(onsole)
* ruby syntax
    - | 생략
    - each do x
    - each_with_index do x, i
    - 쌍따옴표
        + 인터폴레이션 지원
        + 홑따옴표 미지원
* 알아서 생성해주는 코드가 많아서 처음에는 쉽지만 나중에는 공부해야 할 부분이 있음
* ORM
    - active record
    - Todo.create(item: 'fist item', complete: false)
    - Todo.all
    - Todo.find(1)
    - Todo.find_by_*(1)
        + Todo.find_by_*(1)
        + 에러처리 가능
    - Todo.new
        + a = Todo.new
        * a.complete = true
        * 프로퍼티 직접 접근 가능
        * a.save
            - transaction
* 문서
    - [http://guides.rubyonrails.org/](http://guides.rubyonrails.org/)
* ruby lib
    - Gemfile
    - like package.json in node
* libs
    - fingerprint
        + cache
        + css 파일명뒤에 핑거프린트를 붙여서 브라우저에서 새로 다운 받게 만든다
    - async
        + turbolinks
    - API server
        + jbuilder
            * JSON render template
            * 복잡한 구조를 도와줌
    - debug
        + byebug
    - pry
        + [https://github.com/rweng/pry-rails](https://github.com/rweng/pry-rails)
            * gem 'pry-rails', :group => :development
* generator
    - g controller Todos index
* views
    - erb template
        + <%= %>
        + <% %>
* Controller
    - render: json: {...}
* haml
    - [http://haml.info/](http://haml.info/)
    - indent
    - like jade in node
* route
    - rake routes
    - resources :todos, except: [:index]
* Todos 컨트롤러의 index 액션에서 전체 Todo 내용 불러오기
    - 변수명 앞에 @붙이면 뷰에서 사용할 수 있음
* 자료형
    - array
    - hash
        + dictionary python
        + json javascript
        + h = {a:1, b:2}
            * h[:a]
            * symbol
                - h = {:a => 1, :b => 2}
* 질답
    - css chche
        + structure
            * app/asset/
                - pieline
    - rake
        + cmd
        + == make
    - hash string
    - asset precompile
    - web server
        + puma
            * websocket
    - csrf
        + csrf-tocken
        + off
            * ApplicationContoller
                - 상속구조
                - protect_from_forgery
    - db
        + sqlite3
            * /config/database.yml
        + seed.rb
            * initial record
            * ex. import csv script