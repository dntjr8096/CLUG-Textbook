### GCC
GCC는 GNU Compiler Collection의 약자로, C, C++, Java, Objective-C, Fortran, Ada, Go 등 많은 언어의 컴파일러 컬렉션이다. GNU 시스템의 공식 컴파일러이다.

* (C언어 기준) gcc를 통한 빌드 과정
&nbsp;
![](https://drive.google.com/uc?id=154kl4-A5LUiQbymFGCm7akJUbxRsLFWR)

* 터미널에서 명령어 man gcc을 통해 자세한 과정을 알 수 있다. (preprocessing, compilation proper, assembly, linking 순서로 이루어진다고 되어있다.) 명령어 gcc를 입력하면, 모든 빌드 과정을 차례로 수행하게 된다.
&nbsp;
* **gcc명령어 옵션**

|옵션| 설명|
|-|-|
| -o| 출력파일명을 지정한다.
|-c| 컴파일 단계까지만 수행. 오브젝트 파일을 만든다.
|-l| 따로 생성한 헤더파일을 포함시켜주기 위해 지정해 줄 때 사용한다.
|-L | 사용할 라이브러리의 위치를 지정할 때 사용한다.
그 외에도 -g옵션은 디버깅 관련 옵션, -O는 최적화 관련 옵션이다.
&nbsp;

##### TIP
* **-o 옵션**
사용하지 않을 시 a. out으로 통일되어 실행파일이 만들어지는데, 이 경우 여러 번 gcc 명령어를 실행할 때마다 경고없이 실행파일이 덮어쓰기된다. 따라서 실행파일명을 지정해주는 것이 좋다.

* **-c 옵션**
규모가 큰 프로그램의 경우 하나의 프로그램을 여러 파일로 분리해서 작성하게 되는데, 이들을 한번에 묶어서 컴파일할 때 사용된다.

* **실행파일이 만들어진 후 실행하기**
별다른 출력파일명을 지정해 주지 않았을 경우 a.out으로 지정이 되어 실행파일이 만들어진다. 이 때 실행하기 위해서는 ./a.out 을 하게 되는데, 이는 실행파일이 있는 경로를 지정해주기 위함이다. .은 현재 디렉토리를 가리키는 것이고 / 는 디렉토리를 구분하기 위한 것이다.