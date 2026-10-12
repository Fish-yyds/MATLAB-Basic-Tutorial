# MATLAB 基础语法资料

## 1. MATLAB 是什么？

MATLAB（Matrix Laboratory）是一种用于数值计算、算法开发、数据分析和可视化的软件环境。它特别适合：

- 矩阵与线性代数计算
- 数学建模
- 信号与图像处理
- 工程仿真
- 数据分析与算法验证

## 2. MATLAB 运行环境

启动 MATLAB 后，最常使用的区域有：

- Command Window：命令窗口，用于直接执行命令
- Editor：编辑器，用于编写脚本和函数
- Workspace：工作区，查看变量
- Current Folder：当前目录，可切换工作目录

### 常用命令

```matlab
clear;    % 清空变量
clc;      % 清空命令窗口
close all;% 关闭所有图窗
```

## 3. 变量与赋值

MATLAB 中变量不需要声明类型，直接赋值即可：

```matlab
x = 10;
y = 3.14;
z = 'hello';
flag = true;
```

### 变量命名规则

- 区分大小写
- 不能以数字开头
- 不能使用 MATLAB 保留字
- 建议使用有意义的命名方式

```matlab
a = 5;
A = 10;
resultValue = 20;
```

## 4. 基本运算

```matlab
x = 4;
y = 3;

sumValue = x + y;
subValue = x - y;
prodValue = x * y;
divValue = x / y;
powValue = x ^ y;
```

### 常用数学函数

```matlab
sqrt(16)      % 4
abs(-5)       % 5
sin(pi/2)     % 1
cos(pi)       % -1
exp(1)        % e
log(10)       % ln(10)
```

## 5. 向量和矩阵

### 5.1 创建向量

```matlab
v = [1 2 3 4 5];     % 行向量
v_col = [1;2;3;4;5]; % 列向量
```

### 5.2 创建矩阵

```matlab
A = [1 2 3;
     4 5 6;
     7 8 9];
```

### 5.3 生成特殊矩阵

```matlab
zeros(3, 3)    % 3x3 零矩阵
ones(2, 4)     % 2x4 全1矩阵
eye(4)         % 4x4 单位矩阵
rand(3,2)     % 3x2 随机矩阵
linspace(0, 1, 5) % 0到1之间生成5个点
```

### 5.4 索引

```matlab
A = [1 2 3; 4 5 6; 7 8 9];
A(1, 2)    % 第1行第2列
A(:, 1)    % 第1列所有元素
A(2:3, :)  % 第2到3行所有列
```

## 6. 矩阵运算

```matlab
A = [1 2; 3 4];
B = [5 6; 7 8];

A + B
A - B
A * B
A .* B      % 对应元素相乘
A'          % 转置
A.'         % 非共轭转置
```

## 7. 关系运算符

```matlab
x = 5;

x == 5      % 等于
x ~= 3      % 不等于
x > 3       % 大于
x < 10      % 小于
x >= 5      % 大于等于
x <= 7      % 小于等于
```

## 8. 逻辑运算符

```matlab
a = true;
b = false;

a && b      % 逻辑与
a || b      % 逻辑或
~a          % 逻辑非
```

## 9. 控制结构

### 9.1 if 语句

```matlab
x = 10;

if x > 0
    disp('x 是正数');
elseif x == 0
    disp('x 等于 0');
else
    disp('x 是负数');
end
```

### 9.2 for 循环

```matlab
for i = 1:5
    disp(i);
end
```

### 9.3 while 循环

```matlab
n = 1;
while n <= 5
    disp(n);
    n = n + 1;
end
```

### 9.4 switch 语句

```matlab
score = 80;

switch score
    case 90
        disp('优秀');
    case 80
        disp('良好');
    otherwise
        disp('一般');
end
```

## 10. 函数与脚本

### 10.1 脚本

脚本文件以 `.m` 为后缀，直接运行即可：

```matlab
% demo.m
x = 0:0.1:2*pi;
y = sin(x);
plot(x, y);
```

### 10.2 函数

函数文件也用 `.m` 后缀，并以 `function` 开头：

```matlab
function y = addTwo(x)
    y = x + 2;
end
```

调用：

```matlab
result = addTwo(5);
```

## 11. 常用内置函数

```matlab
length([1 2 3 4])    % 4
size(A)              % 返回矩阵大小
sum([1 2 3])         % 6
mean([1 2 3])        % 2
max([1 2 3])         % 3
min([1 2 3])         % 1
```

## 12. 绘图基础

```matlab
x = 0:0.1:2*pi;
y = sin(x);
plot(x, y);
xlabel('x');
ylabel('sin(x)');
title('正弦函数');
grid on;
```

### 多条曲线

```matlab
x = 0:0.1:2*pi;
plot(x, sin(x), 'r');
hold on;
plot(x, cos(x), 'b');
legend('sin(x)', 'cos(x)');
hold off;
```

## 13. 常见注意事项

- MATLAB 中大多数运算默认按矩阵方式计算
- `.*` 是对应元素相乘，不是普通乘法
- `A^2` 是矩阵平方，不是逐元素平方
- `A(1,2)` 用于访问特定元素
- 分号 `;` 会抑制输出

## 14. 小练习

### 练习 1：计算向量和

```matlab
v = [1 2 3 4 5];
result = sum(v);
disp(result);
```

### 练习 2：判断奇偶

```matlab
n = 8;
if mod(n, 2) == 0
    disp('偶数');
else
    disp('奇数');
end
```

### 练习 3：生成正弦波

```matlab
x = 0:0.01:2*pi;
y = sin(x);
plot(x, y);
```

## 15. 学习建议

初学 MATLAB 时建议按下面顺序学习：

1. 变量和赋值
2. 向量与矩阵
3. 基础运算
4. 控制语句
5. 函数与脚本
6. 绘图与数据可视化
7. 工程应用案例

## 16. 总结

MATLAB 的基础语法非常简洁，核心重点包括：

- 变量赋值
- 数组与矩阵
- 运算符
- 控制语句
- 函数/脚本
- 绘图

只要勤加练习，就能快速上手。

