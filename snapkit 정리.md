### snap kit 정리

Snapkit 기본 세팅:

```swift
 var box = UIView().then {
        $0.backgroundColor = .green
    }
    
    
    override func viewDidLoad() {
        super.viewDidLoad()
        view.backgroundColor = .blue
        addSubView()
        layout()
    }
    
    func layout() {
        // 우리가 작성하는 코드는 여기에 들어갑니다!
        
    }
    
    func addSubView() {
        view.addSubview(box)
    }
```

- #### inset

  - ```swift
     box.snp.makeConstraints {
                $0.top.left.right.bottom.equalToSuperview().inset(50)
     }
    ```

  - 한마디로 안으로 들어오는것 

- #### offset

  - ```swift
    box.snp.makeConstraints {
                $0.top.left.equalToSuperview().offset(50)
                $0.bottom.right.equalToSuperview().offset(-50)
            }
    ```

  - 밖으로 나가는것

- #### leading, trailing

  - Leading은 읽는 방향으로 왼쪽
  - 지역에 따라 반대일 경우 있음
  - trailing은 후행이라는 뜻으로 읽는 방향 반대

!!! Layout 설정할때 사용

```swift
override func viewWillLayoutSubviews() {
        setUp()
}
```



