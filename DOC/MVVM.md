# MVVM MVC
## MVC
> MVC的全名是Model View Controller，是模型(model)－视图(view)－控制器(controller)的缩写，是一种软件设计典范。它是用一种业务逻辑、数据与界面显示分离的方法来组织代码，将众多的业务逻辑聚集到一个部件里面，在需要改进和个性化定制界面及用户交互的同时，不需要重新编写业务逻辑，达到减少编码的时间

>在通常的开发中，除了简单的 Model、View 以外的所有部分都被放在了 Controller 里面。Controller 负责显示界面、响应用户的操作、网络请求以及与 Model 交互。这就导致了 Controller：
* 逻辑复杂，难以维护
* 和view紧耦合，无法测试
> MVC流程：用户操作> View (负责接受用户的输入操作)>Controller（业务逻辑处理）>Model（数据持久化）>View（将结果通过View反馈给用户）

>数据关系
* View 接受用户交互请求
* View 将请求转交给Controller
* Controller 操作Model进行数据更新
* 数据更新之后，Model通知View更新数据变化
> 所有方式都是单向通信
View 更新变化数据
## MVVM
> MVVM是Model-View-ViewModel的简写。它本质上就是MVC 的改进版。MVVM 就是将其中的View 的状态和行为抽象化，让我们将视图 UI 和业务逻辑分开。

> 既然 View 和 Controller 是一对好基友，在 MVVM 里面，干脆把它们当做 View。
  现在将原来 Controller 的部分职责拆分出来由 View Model 承担，主要包括:
* 校验用户输入
* 网络请求
* 展示层逻辑：比如格式化字符串
* 其他不能放入 Model，与 View 无关的逻辑
> MVVM是将“数据模型数据双向绑定”的思想作为核心，因此在View和Model之间没有联系，通过ViewModel进行交互，而且Model和ViewModel之间的交互是双向的，因此试图的数据的变化会同时修改数据源，而数据源数据的变化也会立即反应到View上
* View 接收用户交互请求
* View 将请求转交给ViewModel
* ViewModel 操作Model数据更新
* Model 更新完数据，通知ViewModel数据发生变化
* ViewModel 更新View数据
> MVVM优点
* 可重用性。你可以把一些视图逻辑放在一个ViewModel里面，让很多view重用这段视图逻辑
* 独立开发。开发人员可以专注于业务逻辑和数据的开发（ViewModel），设计人员可以专注于页面设计，生成xml代码
* 可测试。界面素来是比较难于测试的，而现在测试可以针对ViewModel来写
