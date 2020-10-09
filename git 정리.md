# Git 

부딪히면서 배운다.



## 간편 안내서

[Roger Dudler, git-guide](https://rogerdudler.github.io/git-guide/index.ko.html)

아주아주 기본이 되는 명령어들을 쉽게 설명해주는 안내서



## Error

##  failed to push some refs to '...'

- 상황 
  - git clone 명령어를 사용해서 github에 repo를 받아왔음 (구성 - readme.md)
  - typora를 사용해서 readme.md 수정
  - `git add .` `git commit -m ""` `git push origin master` 수행 시 오류 발생  



github에 있는 파일과 현재 push 하려는 commit이 일치하지 않아 발생하는 오류라고 한다.

즉, 원격 저장소와 로컬 저장소의 상태가 다르다.

github의 상태 그대로 clone 했고 수정해서 push 하는데, 왜 에러가 발생하는지 모르겠다.



- 해결
  1. `git pull` : github의 최신 상태를 내려받아서 다시 `git push`한다.
  2. `git push -f origin` : 강제로 덮어씌워버린다. (강제라는 말이 보이니 꽤나 위험하다.)





