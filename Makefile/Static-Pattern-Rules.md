Makefile Static Pattern Rules
-----------------------------

https://www.gnu.org/software/make/manual/html_node/Static-Usage.html#Static-Usage

Makefile 에서 다중 Target 에 대해 Pattern 처리가 필요할 때 사용함

```
targets …: target-pattern: prereq-patterns …
        recipe
        …
```

예를 들어,

`j/a.json`, `j/b.json`, `j/c.json` 파일을 '../o' 라는 디렉토리로 복사하는 Rule 이 필요하다면,

```
SOURCES=j/a.json j/b.json j/c.json
TARGET_DIR=../o
TARGETS=$(addprefix $(TARGET_DIR)/,SOURCES)
# 위의 경우에 TARGETS 는 ../o/j/a.json 등이 된다.

all: $(TARGETS)

# 다중 타겟에 대해서, 타겟의 패턴을 지정하고, 각 타겟의 소스를 지정한다.
$(TARGETS): $(TARGET_DIR)/%: %
  mkdir -p `dirname $@`
  cp $< $@
```

위의 코드를 통해서 해결
