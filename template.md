---
marp: true
paginate: true
theme: uncover
footer: kembo

style: |
    section.title {
        justify-content: center;
        text-align: center;
    }
    section {
        justify-content: start;
        text-align: left;
    }
    section ul {
        margin: 15px 0 30px;
    }

    section.split {
        overflow: visible;
        display: grid;
    }
    section.split.col2 {
        grid-template-columns: 570px 570px;
        grid-template-rows: 120px 100px auto 100px auto;
    }
    section.split.col3 {
        grid-template-columns: 380px 380px 380px;
        grid-template-rows: 120px 100px auto;
    }

    section.split h2,
    section.split h3 {
        grid-row: 1 / 2;
    }
    section.split.col2 h2,
    section.split.col2 h3 {
        grid-column: 1 / 3;
    }
    section.split.col3 h2,
    section.split.col3 h3 {
        grid-column: 1 / 4;
    }

    section.split.col2 h4:nth-of-type(n+1):nth-of-type(-n+2),
    section.split.col3 h4:nth-of-type(n+1):nth-of-type(-n+3) {
        grid-row: 2 / 3;
    }
    section.split.col2 h4:nth-of-type(n+3):nth-of-type(-n+4) {
        grid-row: 4 / 5;
    }

    section.split h4:nth-of-type(1) + :not(h4) {
        grid-column: 1 / 2;
        grid-row: 3 / 4;
    }
    section.split h4:nth-of-type(2) + :not(h4) {
        grid-column: 2 / 3;
        grid-row: 3 / 4;
    }
    section.split.col3 h4:nth-of-type(3) + :not(h4) {
        grid-column: 3 / 4;
        grid-row: 3 / 4;
    }
    section.split.col2 h4:nth-of-type(3) + :not(h4) {
        grid-column: 1 / 2;
        grid-row: 5 / 6;
    }
    section.split.col2 h4:nth-of-type(4) + :not(h4) {
        grid-column: 2 / 3;
        grid-row: 5 / 6;
    }
---
<!-- _class: title -->

# タイトル

---

<!-- _class: split col2 -->

## スライド1

#### One

内容

#### Two

内容内容

#### Three

内容内容内容

#### Four

内容内容内容内容

---

<!-- _class: split col3 -->

## スライド2

#### One

本文

#### Two

#### Three

本本本文文文
文文文本本本
本本本文文文
