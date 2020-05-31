---
layout: post
title: Terminal 이쁘게 만들기
comments: true
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

   soruce ~/.zshrc 하여 적용하기 s

