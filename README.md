# dragObject
第一次学习pyqt5 QPainter

学习等到的几点：

1.继承类时，可以多用super().xxxx()调用父类的方法，如果父类有返回值，可以先定义一个值接受，然后return 那个值，达到与父类一样的效果


2.写connect时，可以直接在connect()中写方法，如 lineEdit.returnPressed.connect(lambda :self.myRect.SetText(lineEdit.text()))
但是，要注意到，如果我们需要传参数这个方法就行不通了，需要采用lambda表达式才能传递参数：：lineEdit.text()
但是connect后面跟方法的话，就不需要这么写了，如 lineEdit.returnPressed.connect(self.TextShow)   后面不需要加(),不加()不意味着后面没有参数，也可以是有的，但是要注意，就收的参数要跟前面信号传来的参数一致


3.说道信号了，就讲一下如何自定义信号。loadOk（信号名） = pyqtSignal(list,list)，后面定义传了两个参数，所以发送时：self.loadOk.emit(listprice, listtitle)，要把这两个参数传出去，所以接受时：self.mythread.loadOk.connect(self.showItem)，  所以槽函数：def showItem(self, listprice, listtitle)，要接受两个参数 
