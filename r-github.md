R github
================

# R Markdown 安装

- 在RStudio中的console中 安装rmarkdown包

``` r
install.packages("rmarkdown")
```

- 生成PDF需要LaTex或tinytex包

``` r
install.packages('tinytex')  
tinytex::install_tinytex()
```

# R Markdown 流程

1.  安装 rmarkdown
2.  新建Rmarkdown项目
3.  项目的内容
    - 1）YAML：title、author、date、指定output文件类型等
    - 2）TEXT：是rmarkdown里的主要内容
    - 3）Code
      chunks：执行文件内的代码块，Rmd文件中除了R代码段以外，还可以插入Rcpp、Python、Julia、SQL等许多编程语言的代码段
4.  导出

# R Markdown 使用

## 1.YAML

- ymlthis是专门为写R Markdown的YAML header而开发的包
  借助ymlthis的图形化插件可以进行基本的YAML设置

``` r
install.packages('ymlthis')
```

- YAML设置中文支持

``` yaml
header-includes:
  - \usepackage{ctex}
# 或者
documentclass: ctexart
```

## 2.TEXT

- HELP-Markdown Quick Reference 官网<https://rmarkdown.rstudio.com/> R
  Markdown: The Definitive Guide  
  R Markdown Cookbook
- R
  数据分析指南与速查手册<https://www.math.pku.edu.cn/teachers/lidf/docs/Rbook/html/_Rbook/rmarkdown.html>
- R语言教程
  <https://www.math.pku.edu.cn/teachers/lidf/docs/Rbook/html/_Rbook/rmarkdown.html>

## 3.Code Chunks

You can quickly insert chunks like these into your file with

the keyboard shortcut Ctrl + Alt + I (OS X: Cmd + Option + I) the Add
Chunk command in the editor toolbar

``` r
library(reticulate)
print("Hi,python")
import this
```

- 图片

![](r-github_files/figure-gfm/pressure-1.png)<!-- -->

- 表格

``` r
x <- 1:10; y <- x^2; lmr <- lm(y ~ x)
co <- summary(lmr)$coefficients
knitr::kable(co)
```

|             | Estimate | Std. Error |   t value | Pr(\>\|t\|) |
|:------------|---------:|-----------:|----------:|------------:|
| (Intercept) |      -22 |  5.5497748 | -3.964125 |   0.0041530 |
| x           |       11 |  0.8944272 | 12.298374 |   0.0000018 |
