---
layout: post
title: Terminal 이쁘게 만들기
comments: true
tag: [Terminal, iterm2]
---



## Mac에서 Terminal 이쁘게 만들기



### iterm2 + oh-my-zsh  이용하기



1. iterm2 설치하기 

   https://www.iterm2.com/ 에서 iterms2 설치하기 

   https://github.com/mbadolato/iTerm2-Color-Schemes 에서 테마 설치하기

   profile - colors 탭에서 테마를 import 하기

   

2. oh-my-zsh 설치하기

   brew 설치 안 되었으면 brew부터 설치 . .(설치 방법은 알아서)

   zsh 설치 (shell의 확장 버전)

   ```shell
   brew install zsh
   ```

   oh-my-zsh 설치 (zsh의 확장 버전)

   ~~~shell
   sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
   ~~~

3. git 상태를 알 수 있는 agnoster 테마를 적용하기

   vi ~/.zshrc 하여

   ZSH_THEME=”robyrussell”  ----> ZSH_THEME=”agnoster” 로 바꾸기

   soruce ~/.zshrc 하여 적용하기 

4. agnoster 테마를 적용하면 폰트가 깨져서 폰트를 바꿔야함

   https://github.com/naver/d2codingfont에 들어가 폰트를 다운받아서 적용해야함 

   Profile - text에서 change font를 선택하면 된다고 하지만 내 iterms2에는 없었음. 그래서 다운 받은 폰트를 응용프로그램 - 서체관리자에 업로드시켜서 폰트를 바꿔줬음 

5. @MacBook-pro 없애기

   ~~~shell
   prompt_context() {
     if [[ "$USER" != "$DEFAULT_USER" || -n "$SSH_CLIENT" ]]; then
       prompt_segment black default "%(!.%{%F{yellow}%}.)$USER"
     fi
   }
   ~~~

   ~/.zshrc에서 위의 코드를 맨 마지막에 넣으면 사용자 이름만 나오게 할 수 있음. 

6. NewLine 적용

   ~~~shell
   vi ~/.oh-my-zsh/themes/agnoster.zsh-theme
   ~~~

   에서 

   ~~~shell
   build_prompt() {
     RETVAL=$?
     prompt_status
     prompt_virtualenv
     prompt_context
     prompt_dir
     prompt_git
     prompt_bzr
     prompt_hg
     prompt_newline 
     prompt_end
   }
   ~~~

   build_prompt에서 prompt_newline을 prompt_end 위에 적용시킨다. 꼭 위에 적어야 한다고 한다. 

   ~~~shell
   prompt_newline() {
     if [[ -n $CURRENT_BG ]]; then
       echo -n "%{%k%F{$CURRENT_BG}%}$SEGMENT_SEPARATOR
   %{%k%F{blue}%}$SEGMENT_SEPARATOR"
     else
       echo -n "%{%k%}"
     fi
   
     echo -n "%{%f%}"
     CURRENT_BG=''
   }
   ~~~

   위의 코드를 아래에 추가해준다. 

7. Syntax-Hightlight 적용하기 

   사용할 수 있는 명령어라면 초록색으로 하이라이팅 된다. 

   ~~~shell
   //설치 
   brew install zsh-syntax-highlighting
   
   //플러그인 적용
   echo "source /usr/local/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh" >> ${ZDOTDIR:-$HOME}/.zshrc
   ~~~



### 완성작

---

![terminal](/Users/jh/Github/hease02.github.io/assets/img/terminal.png)

