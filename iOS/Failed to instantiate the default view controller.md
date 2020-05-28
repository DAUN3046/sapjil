# 문제발생
[WindowScene] Failed to instantiate the default view controller for UIMainStoryboardFile 'Main' - perhaps the designated entry point is not set?

# 발생원인
기본 뷰 컨트롤러를 사용하지 않고 다른 뷰 컨트롤러를 초기 뷰 컨트롤러로 설정하려 했으나, 이를 인스펙터에서 지시해주지 않았을 경우에 생기는 오류이다. 

# 문제해결
기본 뷰 컨트롤러로 만들고 싶은 뷰 컨트롤러의 Attributes inspector에서 is initial View Controller로 지정해주어야 된다.
