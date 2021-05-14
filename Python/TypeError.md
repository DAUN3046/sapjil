# 문제발생
TypeError: cannot unpack non-iterable int object
  
# 문제원인
sum1, sum2 = 0

# 문제해결
원래 의도는 sum1, sum2 = 0, 0 이었을텐데 정수를 하나 빼먹은 것이다.
기억안나면

sum1 = 0

sum2 = 0

이렇게 변수를 나눠서 선언하자...
