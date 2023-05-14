# 第2课 课后作业

## 转换为bit位 Num2Bits
参数：nBits</br>
输入信号：in</br>
输出信号：b[nBits]</br>
输出信号应该是长度为nBits的位数组，相当于in的二进制表示。 b[0] 是最低有效位。

解决方案

## 判零 IsZero
参数：无</br>
输入信号：in</br>
输出信号：out</br>
要求：如果in为零，out应为1。 如果in不为零，out应为0。 这个有点棘手！

解决方案

## 相等 IsEqual
参数：无</br>
输入信号：in[2]</br>
输出信号：out</br>
要求：如果 in[0] 等于 in[1]，则 out 应为 1。 否则，out 应该是 0。

解决方案

## 选择器 Selector
参数：nChoices</br>
输入信号：in[nChoices], index</br>
输出：out</br>
要求：输出out应该等于in[index]。 如果 index 越界（不在 [0, nChoices) 中），out 应该是 0。

解决方案

## 判负 IsNegative
注意：信号是模 p（Babyjubjub 素数）的残基，并且没有负数模 p 的自然概念。 但是，很明显，当我们将p-1视为-1时，模运算类似于整数运算。 所以我们定义一个约定：取负 按照惯例认为是 (p/2, p-1] 中的余数，非负是 [0, p/2) 中的任意数

参数：无</br>
输入信号：in</br>
输出信号：out</br>
要求：如果根据我们的约定，in 为负数，则 out 应为 1。 否则，out 应该是 0。 您可以自由使用CompConstant circuit，它有一个常量参数ct，如果in（二进制数组）在解释为整数时严格大于 ct 则输出 1 ，否则为 0。

解决方案

## 理解检查：为什么我们不能只使用 LessThan 或上一个练习中的比较器电路之一？
少于 LessThan</br>
参数：无</br>
输入信号：in[2]。 假设提前知道这些最多。</br>
输出信号：out</br>
要求：如果 in[0] 严格小于 in[1]，则 out 应为 1。 否则，out 应该是 0。

扩展 1：如果您知道输入信号最多为 ，您如何减少该电路所需的约束总数？ 编写一个在k中参数化的电路版本。</br>
扩展 2：编写 LessEqThan（测试 in[0] 是否 ≤ in[1]）、GreaterThan 和 GreaterEqThan</br>
解决方案（扩展1）

## 整数除法 IntegerDivide
注意：这个电路非常难！</br>

参数：nbits。 使用 assert 断言这最多为 126！</br>
输入信号：dividend, divisor （被除数，除数）</br>
输出信号：remainder, quotient （余数，商）</br>
要求：首先，检查dividend和divisor是否最多为nbits位长。 接下来，计算并约束余数和商。

扩展：您将如何修改电路以处理负的被除数？</br>
解决方案（忽略第二个参数SQRT_P，这是无关紧要的）

## 排序 Sort 【可选】
参数：N</br>
输入信号：in[N]</br>
输出信号：out[N]</br>
要求：将输入in[N]的N个数字按照从小到大进行排列，并输出到out[N]信号中。
