# 마크다운 문법

## Heading 사용법

- 문제의 제목이나 소제목으로 사용한다.
- #의 개수에 따라 대응되는 수준이 있으며, h1 ~ h6까지 표현 가능
- 만약, 사용자가 h5 level의 제목을 생성한다면, 아래와 같이 사용할 수 있다.

아래와 같이 '#'을 5개 이용해서, level 5의 제목을 생성할 수 있다.

##### Heading level 5



## List 사용법

- 순서가 있는 리스트와 순서가 없는 리스트로 구성
- Typora Tip) Tab와 Shift+tab으로 하위 목록을 자유롭게 생성 가능

순서가 있는 리스트의 경우,  아래와 같이 순번을 매겨서 사용

1. First item
2. Second item
3. Third item

순서가 없는 리스트의 경우, 아래와 같이 순번없이 사용

- First item
- Second item
- Third item



## Fenced Code Block 사용법

- 코드 블록은 backtick 기호 3개를 활용하여 작성(\`\`\` \`\`\`)
- 코드 블록에 특정 언어를 명시하면 Syntax Highlighting  적용 가능
  - 일부 환경에서는 적용이 되지 않을 수 있음

```Json
// JSON Example
{
    "firstName": "John",
    "lastName": "Smith",
    "age": 25
}
```

```java
// Java Example
public class Car {
    String company;
    String model;
    
    String getCompany() {
        return company;
    }
    
    String getModel() {
        return model;
    }
}
```



## Inline Code Block 사용법

- 코드 블록은 backtick 기호 1개를 인라인에 활용하여 작성(``)

아래와 같이, 특정 부분('nano')를 inline code block로 만들 수 있다.

At the command prompt, type `nano`



## Link 사용법

- \[문자열\](url)을 통해 링크를 작성 가능
  - 특정 파일들 포함하여 연결 시킬 수도 있음

아래와 같이, 작성해서 사용하면, 

```html
My GitHub Page is [KyuSahm's GitHub](https://github.com/KyuSahm)
```

다음과 같이 화면에 나타난다.

My GitHub Page is [KyuSahm's GitHub](https://github.com/KyuSahm)



## 이미지 사용법

- \!\[문자열](url)을 통해 이미지를 사용 가능
  - 특정 파일들 포함하여 연결 시킬 수도 있음
- Typora Tip) 드래그앤드랍으로 활용 가능
  - 활용시 상대 경로 설정을 반드시 할 것!

아래와 같이 작성하면,

```Html
![My beautiful picture is this](./images/sample.jpg)
```

다음과 같이 화면에 나타난다.

![My beautiful picture is this](./images/sample.jpg)



## Blockquotes(인용문) 사용법

- > \>를 통해 인용문을 작성

아래와 같이 작성하면,

```Htm
> No pain, No Gain 
```

다음과 같이 화면에 나타난다.

> No pain, No Gain



# Table 사용법

- 표는 아래의 문법을 참고
  - 일부 지원 안되는 환경도 있음
- Typora Tip) 본문 > 표 > 표 삽입으로 편하게 관리

아래와 같이 작성하면, 

```Html
| Syntax    | Description |
| --------- | ----------- |
| Header    | Title       |
| Paragraph | Text        |
```

다음과 같이 표시된다.

| Syntax    | Description |
| --------- | ----------- |
| Header    | Title       |
| Paragraph | Text        |



## Text 강조 사용법

- 굵게(bold), 기울임(Italic)을 통해 특정 글자들을 강조
- 텍스트 굵게 만드려면,  "**"로 감싸거나, "__" 로 감싸면 됨

아래와 같이 작성하면, 

```Html
I just love **bold text**
```

다음과 같이 표시된다.

I just love **bold text**



## 수평선 사용법

- 3개 이상의 asterisks(***), dashes(---), or underscores(___)를 사용

아래와 같이 작성하면, 

```Html
***
---
________________________
```

다음과 같이 표시된다.

***

---

___________________________________



## 마크다운 관련 자료

- GitHub Flavored Markdown (https://github.github.com/gfm/)
- Mastering Markdown (https://guides.github.com/features/mastering-markdown/)
- Markdown Guide (https://www.markdownguide.org/)









