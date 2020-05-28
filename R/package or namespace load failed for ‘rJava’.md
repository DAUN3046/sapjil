# 문제발생
에러: package or namespace load failed for ‘rJava’:
 .onLoad가 loadNamespace()에서 'rJava'때문에 실패했습니다:
  호출: fun(libname, pkgname)
  에러: No CurrentVersion entry in Software/JavaSoft registry! Try re-installing Java and make sure R and Java have matching architectures.
  
# 문제원인
KoNLP 패키지 설치 중 R과 내 컴퓨터 간의 자바 호환 문제 발생. Java 신버전 설치(32비트/64비트 확인 필수!).
그러자 다음과 같은 문제가 발생.

에러: package or namespace load failed for ‘rJava’:
 .onLoad가 loadNamespace()에서 'rJava'때문에 실패했습니다:
  호출: inDL(x, as.logical(local), as.logical(now), ...)
  에러: 공유된 객체 'C:/Users/~~~/Documents/R/win-library/3.6/rJava/libs/x64/rJava.dll'를 로드 할 수 없습니다:
  LoadLibrary failure:  지정된 모듈을 찾을 수 없습니다.

# 문제해결
Sys.setenv(JAVA_HOME="C:/Program Files/Java/jre1.8.0_251")

코드를 이용, 환경변수로 자바의 위치를 알려줬다.
그 뒤 KoNLP 패키지 zip 파일을 직접 install해주면 library(KoNLP)로 불러오기까지 성공.
드디어 KoNLP를 사용할 수 있다.
