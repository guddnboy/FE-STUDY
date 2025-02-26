# 제로 런타임 CSS는 무엇인가요?

제로 런타임 CSS를 알기 위해서는 먼저 브라우저에서 CSS를 적용하는 과정에 대해서 알아야 합니다.

## css는 어떻게 적용되나요?

1. 브라우저가 HTML을 로드합니다.
2. 로드한 HTML을 기반으로 DOM으로 생성합니다.
3. link 태그를 맞이하면, css 리소스를 로드합니다.
4. 로드한 css 리소스로 구문 분석을 진행하여 cssom이라는 구조체를 생성합니다.
5. 생성했던 DOM과 cssom을 결합하여 렌더 트리(Render Tree)를 생성합니다
   - 선택자 유형 별로 다른 규칙을 '다른 버킷'으로 정렬하는 것을 렌더 트리라고 합니다.
6. 렌더 트리는 규칙이 적용된 후에 표시되어야 하는 구조로 배치됩니다.
7. 페인팅 작업을 통해 페이지에 스타일이 적용됩니다.

![alt text](img/css과정.JPG)

제로 런타임 css는 런타임 과정에서 css가 적용되는 것이 아니라, 빌드 과정에서 css가 계산되어 사용자가 페이지 로드 시, 최적화된 css를 제공하는 방식입니다.

### 제로 런타임의 장점

- 런타임이 아닌 빌드타임에서 css를 계산하기 때문에 페이지 로딩 시, **불필요한 계산이 줄어들어 성능이 개선**되는 장점을 가지고 있습니다.
- 또한, 최적화된 스타일로 **최종 css 파일 크기를 줄이고, 브라우저의 렌더링 성능을 높여**줍니다.

### 제로 런타임의 단점

- 동적으로 스타일을 적용하기 위해서는 추가적인 로직이 필요합니다.

# 추가로 학습한 부분

## 웹 컴포넌트 스타일링 관리에는 어떤 방식들이 있나요?

### CSS-IN-CSS (Module CSS)

컴포넌트에 대한 css 모듈을 생성합니다. 컴포넌트들 **각각의 스타일을 독립적으로 관리**할 수 있는 장점이 있습니다.

### CSS-IN-JS

Javascript 내에서 css를 정의합니다. **컴포넌트의 상태에 따라 스타일을 쉽게 변경**할 수 있는 장점이 있습니다.

### 두 방식의 공통된 단점

런타임에 css가 적용되므로, 스타일의 크기가 클 경우에는 성능에 영향을 끼칩니다.
