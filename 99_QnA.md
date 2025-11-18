# ✅ 99.정답 

## Q. Hello World 파일 만들기

## A.

```
cd /root/workspace

echo "Hello World" > hello.txt

cat hello.txt
```

## 

* * *

## Q. log 폴더를 만들고 all.txt 파일에서 error로 시작하는 줄만 모아 log/error\_summary.txt 파일로 저장하세요.

## A.

```
# 1. log 폴더 생성
mkdir log

# 2. error로 시작하는 줄만 모아 저장
grep "^ERROR" all.txt > log/error_summary.txt

# 3. 결과 확인
cat log/error_summary.txt
```

* * *

## Q. a.txt 는 hello 문장을, b.txt 는 world 문장을 가진 파일을 만들고 병합해보세요. 

## A.

```
echo "hello" > a.txt
echo "world" > b.txt
# 병합
cat a.txt b.txt > all.txt
```

* * *

## Q. sleep 100 을 & 로 실행하고, ps -ef | grep 으로 PID를 찾아 kill 해보세요.  

## A.

```
sleep 100 &
ps -ef | grep sleep
kill <PID>
```

* * *

## Q. log\_writer.sh를 nohup 으로 실행해보고, 터미널을 종료/재접속한 뒤에도 살아있는지 확인해보세요.  

## A.

```
nohup ./log_writer.sh &
exit    # 세션 종료
# 재접속 후
ps -ef | grep log_writer
tail -f nohup.out
```

<br>

* * *

## Q. 같은 작업을 screen 세션 안에서 실행한 뒤, detach/reattach 를 반복해보세요.

## A.

```
screen -S logsession
./log_writer.sh
# Ctrl + A, D
screen -ls
screen -r logsession
ps -ef | grep log_writer
kill <PID>
```

* * *

## Q.`du` + `df`를 이용해 현재 디스크 상태를 점검해보고, 용량이 가장 큰 디렉토리 3개를 찾아보세요.

## A.

```
df -h
du -sh * | sort -h | tail -3
```

* * *

## Q. `myapp` 폴더를 tar.gz와 zip 두 가지 포맷으로 압축하고, 다시 풀어보세요.

## A.

```
tar -czvf myapp.tar.gz myapp/
tar -xzvf myapp.tar.gz
zip -r myapp.zip myapp/
unzip myapp.zip
```

* * *

## Q. `users.csv`에서 `cut`과 `awk`를 이용해 `(이름, 나이)` 목록만 뽑아보세요.

## A. 

```
cut -d',' -f2,3 users.csv
awk -F',' 'NR>1 {print $2, $3}' users.csv
```

* * *

## Q. `logs2` 디렉토리에서 `grep -rn -i "error"` 로 에러 로그 위치를 찾아보세요.

## A.

```
grep -rni "error" logs2
```

* * *

## Q. `view`를 사용해서 users.csv를 읽기 전용으로 열고, `less`로 big.log를 살펴본 뒤, `uptime`으로 서버 상태를 확인해보세요.

## A.

```
view users.csv
less big.log
uptime
```

<br>

<br>