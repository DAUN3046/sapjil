# 문제발생
Error in pie(socialPro2, main = "참여활동 여부") : 
  'x' values must be positive.
  
# 문제원인
표 전체를 쑤셔넣어서 그래프가 안그려진 것이다. 

# 문제해결
pie(socialPro2$Percent, main = "참여활동 여부")
그래프 그릴 열만 정확히 지정해주면 실행 된다. 급하게 생각하지 말자.
