# Git 

부딪히면서 배운다.



## 간편 안내서

[Roger Dudler, git-guide](https://rogerdudler.github.io/git-guide/index.ko.html)

아주아주 기본이 되는 명령어들을 쉽게 설명해주는 안내서



## Error

### failed to push some refs to '...'

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



---

###  ! [rejected]        master -> master (fetch first)
error: failed to push some refs to 'https://github.com/rxjw95/Knowledge.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.



- 상황
  - git error 해결법 작성 후 knowledge repo push 수행 시 오류 발생



일단 회사 노트북에서도 github을 관리하고 내 개인 노트북에서도 github을 관리하기 때문에 상태가 달라서 생긴 문제다.

그래서 `git pull`을 먹이니 화면이 변경되면서 merge 하는 이유를 작성하라는데, 타이핑이 하나도 안먹혀서 왜 이러나 싶었다. (처음 있는 일이라서 ㅎㅎ)



- 해결

  1. Press “i” on your keyboard.

  2. Write your merge message

  3. Press “esc” button

  4. Type “:wq”
  5. Press Enter
  6. Finally, Push Changes “git push”



참고 : https://mrvirk.com/enter-a-commit-message-to-explain-why-this-merge-is-necessary.html

---

