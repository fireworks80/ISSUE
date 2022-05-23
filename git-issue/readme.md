# git issue

`non-fast-forward` issue

![non fast forward img](/git-issue/img/non-fast-forward.png)

일 경우

## 원인

.gitignore 또는 readme.md 때문에 생긴다고 한다.

## 해결법

```
git push origin +main
```

푸시하려고 하는 브랜치 앞에 `+`를 붙여주면 된다.
