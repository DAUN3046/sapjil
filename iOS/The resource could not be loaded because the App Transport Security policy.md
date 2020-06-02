# 문제발생

The resource could not be loaded because the App Transport Security policy requires the use of a secure connection.

# 발생원인

App Transport Security가 활성화되어 http를 통해 URLSession 사용이 안되기 때문에 info.plist 수정이 필요하다. 

# 문제해결

Main storyboard file base name 항목에 App Transport Security Settings 추가 -> 이어서 Allow Arbitrary Loads 추가 후 값을 NO에서 YES로 변경 
