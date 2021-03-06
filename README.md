# sudoku_v1.0

# 简介
  这是一个数独谜题的小程序。基于python语言在jupyter上开发。
  引了Numpy、Pandas库。
  
# 思路
## 数独表示
  将数独问题转化 9*9*9 的矩阵，依次代表 1～9 数字可能性/行/列
  0/1/10 分别代表该位置 不存在可能/存在可能/确定 是该数字
  > 例如 矩阵[0,2,3] 位置为0,意思就是 数独第3行、第4列，为1可能性0 ；
  > 矩阵[2,4,3] 位置为10,意思就是 数独第5行、第4列，确定为3  ；
## 数独解题思路
  - 根据数独规则，如果一个格子确定为某数，那么1～9其他数字可能性为0，同行、同列、同group 为某数的可能性为0；
  - 双子星规律，如果同行两个格子都只有 1和4 的可能性，那么同行的其他格子 1和4的可能性 为0 （同列、同group同样符合此规律）；
  运用以上两条规则就可以循环更新矩阵就可解出数独。
  
  
# 使用方法

- 使用 9*9 的嵌套列表存储 数独难题（后期计划加入自动识别API接口）；
- 使用 find_the_answer()求解
- 用 show_table() 展示pandas dataframe 格式求解答案（过程答案也可以展示）
