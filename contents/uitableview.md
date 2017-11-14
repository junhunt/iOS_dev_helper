# UITableView

## Storyboard 中为 UITableView 添加 tableHeaderView 和 tableFooterView

### 自适应高度的 tableHeaderView 和 tableFooterView
> tableHeaderView/tableFooterView 根据内容自适应高度,需要用到 -systemLayoutSizeFittingSize: 方法来实现.
实现自适应高度的前提,约束要完整,要保证 View 内部上下左右所有方向都有约束支撑.

```
// some where assign value
headerView.contentLabel.text = "~~~~~~~~~~"

// override
override func viewDidLayoutSubviews() {
      super.viewDidLayoutSubviews()

      if let h = tableView.tableHeaderView?.systemLayoutSizeFitting(UILayoutFittingCompressedSize).height {
          print(h)
          var rect = tableView.tableHeaderView?.frame
          rect?.size.height = h

          headerView.frame = rect!
          tableView.tableHeaderView = headerView

          // OR
          //            tableView.tableHeaderView?.frame = rect!
          //            tableView.tableHeaderView = tableView.tableHeaderView
      }
  }
```  

[在Storyboard中为UITableView添加Header和Footer](http://jerrytian.com/2016/03/05/%E5%9C%A8Storyboard%E4%B8%AD%E4%B8%BAUITableView%E6%B7%BB%E5%8A%A0Header%E5%92%8CFooter/)  
[在Storyboard、Xib中优雅的给UITableView设置tableHeaderView 、tableFooterView](http://www.jianshu.com/p/86482f476d1c)
