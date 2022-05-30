---
crossref: 
  fig-prefix: 图   # 设置引用格式
  tbl-prefix: 表
  eq-prefix: ""
format: 
  pdf:
    template: _cumcm.tex
    highlight-style: github
#--队伍信息及摘要页--#
NO: 一 # 第几次论文
group: 1707 # 小组编号
school: stulink大学 # 学校名称
name1: 蛋卷 # 学生1姓名
class1: 成都1店 # 学生1班级
number1: 1000000000 # 学生1学号
name2: 烤肉 # 学生2姓名
class2: 成都2店 # ···
number2: 1000000001
name3: 麻辣拌
class3: 成都3店
number3: 1000000002
time: 2022年3月 # 课程论文布置时间
preface: yes  # 是否显示组队信息，参加比赛改为no即可
title: "暴雨将至"
abstract: |-
  摘要第一段

  每段前都要空两个字符，且段间需空一行
keyword: 别问 \ 问就是一只猪
---

# Demo

## 基础

### 数学公式

#### 带编号公式

$$
E = mc^2
$$ {#eq-质能方程}


#### 无编号公式

$$
\text{s.t.} = 
\begin{cases}
x + y\\
x - y
\end{cases}
$$

### 表格及图片

#### 符号说明

| 符号  | 说明        | 单位 |
|-------|-------------|------|
| $x_i$ | 第$i$次相遇 | 毫厘 |
| $y_j$ | 第$j$次错过 | 千里 |

: 符号说明 {#tbl-符号说明}

#### MIT LOGO

![麻省理工学院](mit.png){#fig-mit width="50%" height="17.5%"}

## 引用

引用质能方程([-@eq-质能方程])、符号说明 @tbl-符号说明 、MIT LOGO @fig-mit 。
