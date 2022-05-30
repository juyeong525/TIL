#### UserDefault

- 화면이 사라졌을때 

- ```swift
  private func setData() {
          let data = todolist.map {
              [
                  "title": $0.todoTitle,
                  "content": $0.todoText
              ]
          }
          UserDefaults.standard.set(data, forKey: "item")
          UserDefaults.standard.synchronize()
      }
  ```

  1. todolist배열 값을 data 배열에 저장
  2. Userdefaults에 key 값이 item ,value가 data인 딕셔너리 형태로 저장

  .Map : 배열을 하나씩 순서대로 가져오는것

- 화면이 나타났을때

- ```swift
  func loadData() {
          guard let data = UserDefaults.standard.object(forKey: "item") as? [[String: AnyObject]] else {
              return
          }
          todolist = data.map {
              let title = $0["title"] as? String
              let content = $0["content"] as? String
  
              return ToDoList(todoTitle: title!, todoText: content!)
          }
      }
  ```

  1. data에 userdaults값 저장 guard로 오류 검사 
  2. todolist 배열에 data.map 으로 값 넘겨주기 