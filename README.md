# 두번째 과제 - VimGolf
## vimgolf란?
golf는 볼을 채로 쳐서 정해진 구멍에 넣는 게임. 공을 가장 적게 쳐서 구멍에 넣는 쪽이 이기는 게임
vimgolf도 마찬가지이다. start file로 시작하여 end file을 완성하는 게임이지만 타이핑을 가장 적게 치는 쪽이 이기는 게임이다.

## vimgolf 설치 방법
+ apt update (or apt-get update)
+ apt install python (or apt-get install python)
+ apt install python3-pip (or apt-get install python3-pip)
+ pip install vimgolf


## 아래 5개의 VimGolf 문제에 대하여 솔루션을 제시할 것.
* 5f0f5fbe280fbf000c233304
* 603ba26a01b4d00009c10a49
* 5f1063aa8361810006e73210
* 9v0060da5177000000000209
* 6013804df3308e0009368f1c

## 5f0f5fbe280fbf000c233304
<img src="https://user-images.githubusercontent.com/77472995/144710985-f91925da-87f0-4bf0-b976-b78ca78f1fdf.png" width=350px height=350px> 
$ vimgolf put 5f0f5fbe280fbf000c233304

### solution (my score:9 / best score:8)
**GWi"\<End\>"\<Esc\>ZZ**\
+ G : 맨 마지막 행으로 이동
+ W : 단어 단위 이동 (현재 커서는 {)
+ i : 입력모드 전환(현재 커서의 앞에서 입력)
+ ZZ : 저장하고 종료

## 603ba26a01b4d00009c10a49 (simple replacements)
<img src="https://user-images.githubusercontent.com/77472995/144711580-009fa354-e18c-424e-a423-44aba902c35a.png" width=350px height=350px>
$ vimgolf put 603ba26a01b4d00009c10a49

### solution (my score:25 / best score:19)
**wcwvim\<Esc\>:%s/emacs/vim/g\<CR\>ZZ**
+ w : 단어단위 이동 (현재 커서는 sublime의 s에 위치)
+ cw : 단어대체(sublime이라는 단어가 삭제되면서 입력모드로 변환)
+ vim입력
+ :%s/emacs/vim/g : emacs라는 단어를 vim으로 치환
+ ZZ : 저장하고 종료


