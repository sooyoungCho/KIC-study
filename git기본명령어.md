# git 설정

git config --global user.name "사용자 이름"<br>
git config --global user.email "이메일" <br>

## 저장소 생성
```
pwd
cd ..
mkdir "생성할 폴더명"
cd "들어갈 폴더명"
git init
```

## 커밋
```
git status
git commit -a
git commit -m "커밋메시지"
```

## 원격 저장소 > 로컬 저장소
```
git clone "깃허브 주소"
```

## 로컬저장소와 원격 저장소의 연결
```
git remote add origin "깃허브 주소"
git remote -v
```

## 로컬 작업내역 원격 저장소에 올리기
```
git push origin --all
```

## 브랜치 생성과 이동
```
git branch
git branch "생성시킬 브랜치 이름"
git checkout "이동할 브랜치명"
```