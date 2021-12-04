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

## 1. 5f0f5fbe280fbf000c233304
<img src="https://user-images.githubusercontent.com/77472995/144710985-f91925da-87f0-4bf0-b976-b78ca78f1fdf.png" width=350px height=350px> 
$ vimgolf put 5f0f5fbe280fbf000c233304

### solution (my score:9 / best score:8)
<img src="https://user-images.githubusercontent.com/77472995/144716494-3a74f62a-3f7d-4853-ad5c-22ca848989a6.gif" width=850px height=500px>

`GWi"\<End\>"\<Esc\>ZZ`
+ G : 맨 마지막 행으로 이동
+ W : 단어 단위 이동 (현재 커서는 {)
+ i : 입력모드 전환(현재 커서의 앞에서 입력)
+ ZZ : 저장하고 종료

## 2. 603ba26a01b4d00009c10a49 (simple replacements)
<img src="https://user-images.githubusercontent.com/77472995/144711580-009fa354-e18c-424e-a423-44aba902c35a.png" width=350px height=350px>
$ vimgolf put 603ba26a01b4d00009c10a49

### solution (my score:25 / best score:19)
<img src="https://user-images.githubusercontent.com/77472995/144716648-2808c5d9-fee7-428e-b686-7cd759d43ed1.gif" width=850px height=500px>

`wcwvim\<Esc\>:%s/emacs/vim/g\<CR\>ZZ`
+ w : 단어단위 이동 (현재 커서는 sublime의 s에 위치)
+ cw : 단어대체(sublime이라는 단어가 삭제되면서 입력모드로 변환)
+ vim입력
+ :%s/emacs/vim/g : emacs라는 단어를 vim으로 치환
+ ZZ : 저장하고 종료

## 3. 5f1063aa8361810006e73210 (Satisfy the go linter)
<img src="https://user-images.githubusercontent.com/77472995/144712342-4a1701c7-67b2-4e04-94b0-cc60efa6826f.png" width=350px height=350px>
$ vimgolf put 5f1063aa8361810006e73210

### solution (my score:33 / best score:20)
<img src="https://user-images.githubusercontent.com/77472995/144716664-886ddb19-df2b-4d84-8954-c5bad3176cfc.gif" width=850px height=500px>

`4GO// Version TODO\<Esc\>Y\<Down\>pwcwDebug\<Esc\>ZZ`
+ 4G : 4번째 행으로 이동
+ O : 현재 커서위치의 행을 한칸 내리고 삽입모드 (// Version TODO 입력)
+ Y : 현재 행을 복사
+ p : 현재 커서 아래 행에 붙여넣기
+ w : 단어단위 이동(현재 커서는 Version의 V)
+ cw : 단어대체(Version이라는 단어가 사라지고 입력모드로 변경 Version을 Debug로 변경)
+ ZZ : 저장하고 종료

## 4. 9v0060da5177000000000209 (Plotting some variables in python)
<img src="https://user-images.githubusercontent.com/77472995/144716004-3d4595f3-5089-49d9-b8f9-811d1988fa6e.png" width=450px height=350px>
$ vimgolf put 9v0060da5177000000000209

### solution (my score:68 / best score:34)
<img src="https://user-images.githubusercontent.com/77472995/144716768-d4ca53d1-cd3a-492a-9dc4-66f19f1ecee3.gif" width=850px height=500px>

`3Gf1r2f1r2fkrbf1r2<Down>r3FkrrF1r3F1r3<Down>r4f1r4fkrgf1r4qqFyiabs(<Right><Right>)<Esc><Up>q3@qZZ`
+ 3G : 3행으로 이동
+ f1 : 1을 찾는다.
+ r2 : 찾은 1을 2로 변경한다.
+ ...
+ fk : 'k'를 찾는다.
+ rb : 찾은 'k'를 'b'로 변경한다.
+ Fk : 뒤쪽으로 'k'를 찾는다.
+ rr : 찾은 'k'를 'r'로 변경한다.
+ ...
+ qq : 매크로 시작(매크로를 끝낼 때까지 타이핑하는 키를 모두 녹화한다.)
+ Fy : 'y'를 뒤로 찾는다.
+ i : 입력모드로 변경 (abs(~)를 입력한다)
+ q : 매크로 녹화 중지
+ 3@q : 매크로를 3번 실행한다.
+ ZZ : 저장하고 종료

## 5. 6013804df3308e0009368f1c (Python dataclasses)
<img src="https://user-images.githubusercontent.com/77472995/144716279-3c488fcd-cf1d-431a-9384-09ce5c6f6093.png" width=450px height=350px>
$ vimgolf put 6013804df3308e0009368f1c

### solution (my score:28 / best score:19)
<img src="https://user-images.githubusercontent.com/77472995/144716727-0072fa48-eded-41af-8a44-8ce2bb057d70.gif" width=850px height=500px>

`5Gyw5<Down>f"pa,name,age,score<Esc>ZZ`
+ 5G : 5행으로 이동
+ yw : 커서 위치에서 오른쪽 한 단어 복사(student_id)
+ 5↓ : 5칸 아래로 이동(10행으로)
+ f" : "를 찾아서 이동
+ p : 복사한 단어(student_id) 붙여넣기
+ a : 입력모드로 변경(커서 오른쪽으로 입력된다.)
+ ,name,age,score 입력
+ ZZ : 저장하고 종료
