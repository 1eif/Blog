# 修改IDEA运行SpringBoot项目时控制台输出高亮日志

### 路径：

Run——Edit Configurations——Environment——VM options：

### 填入代码：

```
-Dspring.output.ansi.enabled=ALWAYS
```

![code](https://qncdn.laufan.cn/img/20210607202951.png?imageView2/0/q/75%7Cimageslim)

### 效果

![效果](https://qncdn.laufan.cn/img/20210607203619.png?imageView2/0/q/75%7Cimageslim)