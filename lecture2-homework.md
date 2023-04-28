# 第2课 课后作业

## 第1题 转换为bit位 Num2Bits
* 参数：nBits
* 输入信号：in
* 输出信号：b[nBits]
* 输出信号应该是长度为nBits的位数组，相当于in的二进制表示。 b[0] 是最低有效位。

  [解决方案](https://github.com/iden3/circomlib/blob/master/circuits/bitify.circom#L25)

* 代码在此：[Num2Bits](https://github.com/0xKKv7/zkshanghai-workshop/blob/main/lecture2/Num2Bits)

## 第2题 判零 IsZero
* 参数：无
* 输入信号：in
* 输出信号：out
* 要求：如果in为零，out应为1。 如果in不为零，out应为0。 这个有点棘手！

  [解决方案](https://github.com/iden3/circomlib/blob/master/circuits/comparators.circom#L24)

* 代码在此：[IsZeros](https://github.com/0xKKv7/zkshanghai-workshop/blob/main/lecture2/IsZero)

## 第3题 相等 IsEqual
* 参数：无
* 输入信号：in[2]
* 输出信号：out
* 要求：如果 in[0] 等于 in[1]，则 out 应为 1。 否则，out 应该是 0

  [解决方案](https://github.com/iden3/circomlib/blob/master/circuits/comparators.circom#L37)
  
* 代码在此：[IsEqual](https://github.com/0xKKv7/zkshanghai-workshop/blob/main/lecture2/IsZero)

## 第4题 选择器 Selector
* 参数：nChoices
* 输入信号：in[nChoices], index
* 输出：out
* 要求：输出out应该等于in[index]；如果 index 越界（不在 [0, nChoices) 中），out 应该是 0

  [解决方案](https://github.com/iden3/circomlib/blob/master/circuits/comparators.circom#L37)
  
* 代码在此：[Selector](https://github.com/0xKKv7/zkshanghai-workshop/blob/main/lecture2/Selector)

## 第5题 判负 IsNegative
* 注意：信号是模 p（Babyjubjub 素数）的残基，并且没有负数模 p 的自然概念。 <br />但是，很明显，当我们将p-1视为-1时，模运算类似于整数运算。<br />所以我们定义一个约定：取负 按照惯例认为是 (p/2, p-1] 中的余数，非负是 [0, p/2) 中的任意数
* 参数：无
* 输入信号：in
* 输出信号：out
* 要求：如果根据我们的约定，in 为负数，则 out 应为 1。 否则，out 应该是 0。 <br />您可以自由使用CompConstant circuit，它有一个常量参数ct，如果in（二进制数组）在解释为整数时严格大于 ct 则输出 1 ，否则为 0。

  [解决方案](https://github.com/darkforest-eth/circuits/blob/master/perlin/QuinSelector.circom)
  
* 代码在此：[IsNegative](https://github.com/0xKKv7/zkshanghai-workshop/blob/main/lecture2/IsNegative)

## 第6题 少于 LessThan
* 参数：无
* 输入信号：in[2]。 假设提前知道这些最多 
* 输出信号：out
* 要求：如果 in[0] 严格小于 in[1]，则 out 应为 1。 否则，out 应该是 0
* 代码在此：[LessThan](https://github.com/0xKKv7/zkshanghai-workshop/blob/main/lecture2/IsNegative)

## 第7题 整数除法 IntegerDivide
* 参数：nbits。 使用 assert 断言这最多为 126！
* 输入信号：dividend, divisor （被除数，除数）
* 输出信号：remainder, quotient （余数，商）
* 要求：首先，检查dividend和divisor是否最多为nbits位长。 接下来，计算并约束余数和商
* 代码在此：[IntegerDivide](https://github.com/0xKKv7/zkshanghai-workshop/blob/main/lecture2/IntegerDivide)


