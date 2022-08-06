# Headings  

---
제목(Header)을 만들려면 단어나 구절(phrase) 앞에 기호(#)를 추가하면 됩니다.
사용하는 숫자 기호의 수는 제목 수준(level)과 일치해야 합니다.  
<br>
예를 들어, 제목 수준 3(h3)을 만들려면 세 개의 기호(###)을 사용합니다.

| Markdown               | Redndered Output           |
|------------------------|----------------------------|
| # Heading levvel 1     | <h1> Heading level 1 </h1> |
| ## Heading level 2     | <h2> Heading level 2 </h2> |
| ### Heading level 3    | <h3> Heading level 3 </h3> |
| #### Heading level 4   | <h4> Heading level 4 </h4> |
| ##### Heading level 5  | <h5> Heading level 5 </h5> |
| ###### Heading level 6 | <h6> Heading level 6 </h6> |

# Alternate Syntax

---
제목(Header)를 '#'기호 이외에 대체하는 방법입니다.  
아래 줄에 제목 수준(level) 1의 경우 '==' 문자를 추가하고,
제목 수준 2의 경우 '--' 문자를 추가합니다.  

| Markdown                                | Rendered Output            |
|-----------------------------------------|----------------------------|  
| Heading level 1<br/>============        | <h1> Heading level 1 </h1> |
| Heading level 2<br/>--------------------- | <h2> Heading level 2 </h2> |


# Notice

---
마크다운은 기호(#)와 제목 사이의 공백을 처리하는 방법에 동의하지 않습니다. 
호환성을 위해 항상 숫자 기호와 제목 이름 사이에 공백을 넣으십시오.    
또한 호환성을 위해 제목 앞뒤에 빈 줄을 넣어야 합니다.

| Do this                                                                                | Don't do this                                                                    |
|----------------------------------------------------------------------------------------|----------------------------------------------------------------------------------|
| # Here's a Heading                                                                     | #Here's a Heading                                                                |
| Try to put a blank line before...<br/><br/># Heading<br/><br/>... and after a heading. | Without blank lines, this might not look right.<br/># Heading<br/>Don't do this! |


### Ref.

---
- Markdown Guid - Basic Syntax (https://www.markdownguide.org/basic-syntax/#headings)



