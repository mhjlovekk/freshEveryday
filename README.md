# freshEveryday
每日优鲜
主要功能：
头部：点击返回图标会返回上一页浏览的页面
购物车页面：登录后才能访问购物车，删除已经加入的商品
订单结算页面：点击按钮商品的个数增加，并自动计算总计，点击提交订单按钮，将商品加入购物车数据库，并在购物车页面显示加入的商品
详情页面：根据每个商品的id显示各自的详情页面
主页面：实现了商品分页查询，点击左上角地址按钮会跳转到填写地址页面，点击商品图片会跳转到各自商品对应的详情页面，点击商品右下角的购物车图标，会将相应的商品加入用户的购物车。
登录页面：采用双向绑定获取用户输入内容，运用正则表达式对用户的输入内容进行判断，使用axios请求服务器，进入数据库查询有无此用户，若有，完成登录。验证码功能：自动生成验证码，点击刷新验证码，只有输入正确的验证码才能登录
注册页面：同样运用双向绑定用户输入的内容，利用正则表达式判断是否满足规则，若满足，则将用户输入的内容插入数据库中。
底部导航栏：点击导航栏按钮会跳转到相应的页面，当点击购物车按钮进行判断，如果用户没有登录，会弹出确认框，提示请先登录，点击“取消”，停留在当前页面，点击“确认”跳转到登录页面，登录完成后跳转用户购物车页面，如果用户已经登录，就直接跳转到购物车。
遇到的问题：
问题：主页面会左右晃动，并没有占满设备的屏幕，导致mint-ui组件库的弹出框不能显示在屏幕中心。
解决：在App.vue中写上组件库和app-container的样式。
问题：购物车商品如何获取点击的按钮下标，并且实现总计的累加？
解决：用自定义属性的方法将点击按钮的下标传给点击事件处理函数，处理函数对相应的商品个数进行加减。在computed中写上总计的计算过程，利用foreach获取每个商品对象，继而获得每个商品的个数和单价进行计算，并返回计算后的总价，利用双向绑定呈现在页面中。
问题：登录页面只有在checkbox选中的情况下，才能点击登录按钮。
通过在checkbox上绑定点击事件，获取事件对象的checked属性，然后再按钮上自定义属性disabled，当checked属性值为true时，按钮的disabled变为true，才能点击按钮，否则禁用按钮。
项目总结：通过这个项目让我明白了MVVM模式的优势所在，也深深感受到组件化开发的方便。
