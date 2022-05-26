### Table view

- 밀어서 tableViewCell 지우기 

  ```swift
    func tableView(_ tableView: UITableView, commit editingStyle: UITableViewCell.EditingStyle, forRowAt indexPath: IndexPath) {
          
          if editingStyle == .delete {
              
              todolist.remove(at: indexPath.row)
              tableView.deleteRows(at: [indexPath], with: .fade)
          }
      }
  ```

- Edit 버튼 눌러 삭제 하기

  ```swift
   @IBAction func editButton(_ sender: UIBarButtonItem) {
          if tableView.isEditing {
              sender.title = ""
              tableView.setEditing(false, animated: true)
          } else {
              sender.title = "Done"
              tableView.setEditing(true, animated: true)
          }
      }
  ```

- edit 버튼 눌러 Cell 위치 이동하기

  ```swift
    func tableView(_ tableView: UITableView, moveRowAt sourceIndexPath: IndexPath, to destinationIndexPath: IndexPath) {
             
             let moved = todolist[sourceIndexPath.row]
             todolist.remove(at: sourceIndexPath.row)
             todolist.insert(moved, at: destinationIndexPath.row)
         }
  ```

  