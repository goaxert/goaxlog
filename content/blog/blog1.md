---
title: Hugo & Dimension
---

## Hugo
Tistory나 Naver 블로그 방식보다 Markdown 형식으로 블로그를 작성하고 싶었습니다. Gatsby, Hugo가 최종 후보혔지만 Go에 이끌려 Hugo를 선택하였습니다.

Hugo에도 테마는 많이 있지만 마음에 드는 테마는 찾기 어려웠습니다.
2년동안 업데이트가 없지만 깔끔한 Dimension으로 시작해보겠습니다.

## Install

Hugo를 설치하기 위해서는 go가 필요합니다.

먼저 gvm을 설치합니다.

```bash
$ bash < <(curl -s -S -L https://raw.githubusercontent.com/moovweb/gvm/master/binscripts/gvm-installer)

$ source ~/.gvm/scripts/gvm
```

go를 설치합니다.

```bash
$ gvm install go1.14.3 -B
$ gvm use go1.14.3 --default
```

Hugo를 설치합니다.

```bash
$ mkdir $HOME/src
$ cd $HOME/src
$ git clone https://github.com/gohugoio/hugo.git
$ cd hugo
$ go install
```

## using hugo & dimension

Hugo를 이용하여 New Site를 생성합니다.

```bash
$ hugo new site my-blog
```

Dimension Theme를 적용합니다.
```bash
cd my-blog
git init
git submodule add https://gitlab.com/dspechnikov/dimension-hugo themes/dimension
```

config.toml파일을 수정합니다.

```toml
baseurl = "/"
languageCode = "en-us"
theme = "dimension"
```

themes/dimension/exampleSite에 content 예제가 있습니다. 해당 디렉토리를 /로 복사합니다.

hugo를 실행하여 블로그의 작동을 확인합니다.

```bash
$ hugo serve -D
```