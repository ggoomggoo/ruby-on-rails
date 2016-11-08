# ruby-on-rails

## index

## links

* doc
    - rails
        + [http://guides.rubyonrails.org/](http://guides.rubyonrails.org/)
        + [http://guides.rubyonrails.org/getting_started.html](http://guides.rubyonrails.org/getting_started.html)
        + [http://installrails.com/](http://installrails.com/)
    - ruby
        + kor
            * [http://ruby-korea.github.io/rubygems-guides/rubygems-basics/](http://ruby-korea.github.io/rubygems-guides/rubygems-basics/)
* lecture
    - 최용철 님; 멋쟁이사자처럼(LikeLion) 창립자
        + 패스트캠퍼스, 멋쟁이사자처럼, 플러닝
    - onoffmix
        + [http://onoffmix.com/event/82501](http://onoffmix.com/event/82501)
        + [http://onoffmix.com/event/82502](http://onoffmix.com/event/82502)
    - repo
        + [https://github.com/cycorld/todo-list](https://github.com/cycorld/todo-list)

---

* 문법이 열려있음
    - 하나코드를 짤대 여러 방식으로 짤 수있음
        + 성향별 선호도 존재
* 일본에서 만들어짐
    - like psesudo
* 대용량 프로젝트는 비추천
    - 2.0 에서 성능 개선
    - 토이 프로젝트
* 환경
    - windows
        + 어려움
    - cloud ide
        + cloud9
            * [c9.io](c9.io)
            * amazon.com
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
        + get, post, update, delete 등.. 을 기본 포맷으로 자동 생성
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

---

* helper
    - underscore(a_a)
* form_tag
* todo_path
    - rake routes
        + 주소 규칙
* data-method
    - jquery_ujs
* crud
    - create
    - delete
    - destory
    - edit
        + views
            * edit_*.html.erb
    - update
        + redirect root
            * not back
* views
    - layouts
        + application.html.erb
* toggle
    - /config/route.rb
        + member do get 'toggle'
        + do ~ end ?
        + [http://guides.rubyonrails.org/routing.html](http://guides.rubyonrails.org/routing.html)

---

* 생산성
    - Rails 규칙을 따르는 선에서는 generate 활용하면 생산선이 높음
    - 커스터마이징을 하면 이해와 수고가 필요함
* GEM
    - package?
    - devise
        + [https://github.com/plataformatec/devise](https://github.com/plataformatec/devise)
        + 기본 기능은 이미 구현. 필요한 부분은 주석 제거.
        + cmd
            * $ rails g devise:views
            * $ rails generate devise User
                - Admin
        + helpers
            * user_signed_in
            * current_user
        + 필터
            * Controller
            * before_action
                - 로그인 체크
                - 권한 체크
            * after_action
            * @변수를 사용해서 다른 전처리에서 사용한 변수 전달
* 모델링
    - relation
        + 테이블
            * 자식에게 부모를 명시
            * 레퍼런스를 명시해주면 인덱스를 자동으로 추가
        + 모델
            * has_many :todos
            * belongs_to :user
                - set, get 이 생성되어 릴레이션 관계가 생성
        + 문법이 너그러움
            * create 파라미터
                - user_id: current_user.id
                - user: current_user
* ajax
    - /javascripts/*.coffee
        + .coffee -> .js 가능
        + 주의할점
            * turbolinks
                - $(document).on('turbolinks:load', function() {/**/})
                - // $(this).attr('contentEditable', true)
                - 걷어내도 된다
                    + del gem, html

* 질답
    - convention
        + !
            * bang
        + ?
            * true/false
    - unless
    - flash
        + like java spring
    - scaffold
        + CRUD genertator
        + cmd
            * rails g scaffold Post user:references content:text 
        + API
            * .json
        + jbuilder
            * json template
    - pagination
        + Todo.order('column ASC').last(10);
        + gem
            * [https://github.com/amatsuda/kaminari](https://github.com/amatsuda/kaminari)
            * [https://github.com/mislav/will_paginate](https://github.com/mislav/will_paginate)
    - 루비 온 레일즈
        + 덴마크
        + 외국
        + k사 신규 페이지
        + 일부 스타트업
        + python, node 다수
        + 익숙해지면 생산성 좋다