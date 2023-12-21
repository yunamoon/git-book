# Describe-Context-It 패턴

### Describe-Context-It 패턴

BDD 테스트 코드 작성 패턴으로, 코드의 행동을 설명하는 테스크 코드를 작성합니다. 다른 BBD 패턴은 Given-When-Then과 비슷한 철학을 가지고 있지만 미묘하게 다른 점이 있습니다.

Describe-Context-It은 상황을 설명하기 보다는 테스트 대상을 주인공 삼아 행동을 더 섬세하게 설명하는 것에 적합합니다.

* Describe : 테스트  대상이 되는 클래스나 메소드 이름을 명시합니다. 즉, 설명할 테스트 대상을 명시하는 것입니다.
* Context : 테스트 할 메소드에 입력할 파라미터를 설명합니다. 즉,   테스트 대상이 놓인 상황을 설명하는 것입니다.
* It : 테스트 대상 메소드가 무엇을 리턴하는지 설명합니다. 이는 테스트 대상의 행동을 설명하는 것입니다.

영어로 Context 문을 작성할 때 반드시 With이나 When으로 시작해야 하며, It 구문은 It returns true, It responese 404와 같이 심플하게 설명하는 것이 가장 좋습니다.

### Describe-Context-It 패턴의 테스트 코드 예시

```javascript

Describe("sun", func() {
    Context("300+200", func() {
    It("returns 500" , func() {
    Expect(Sum(300,200)).to.(Equal(500))
})
})

Context("(-300)+200", fucn() {
    It("returns -100", func() {
    Expect(Sum(-300,200)).To.(Equal(-100))
    })
})
})

```
