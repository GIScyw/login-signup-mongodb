# login-signup-mongodb
MongoDB+jade+express的用户认证的例子

1.在MongoDB中，要是连接指定的数据库名字不存在，就会创建一个数据库,如下就会创建一个名为my-website的数据库

```
mongoose.connect('mongodb://127.0.0.1/my-website');
```

2.通过后台定义schema和model，可以动态地在数据库中创建文档和几何

3.因为本应用中要进行表单处理，所以要用到bodyParser中间件；由于还要对用户进行验证，并将信息保留下来，所以还要用到session中间件，它以来Connect中的cookieParser中间件

4.操作：

- 创建文档：Collection.insert( )
- 查询文档：Collection.findOne( ),find()和findById()(这个是Mongoose添加的一个方法)
- 删除文档：Collection.remove()
- 更新文档：Collection.update()
- 计数：Collection.count()

5.输入框的名字遵循下面的格式：user[field]

```
input(name="user[name]",type="text")
```

当bodyParser遇到这样的格式，后台获取要这样

```
req.body.user.name
```

6.Mongodb有一个ensureIndex命令，不管索引是否存在，都可以调用这个命令来确保在查询前建立了索引。

7.MongoDb模型定义的文件可以在任何地方，无所谓Mongoose是否已经与数据库连接

8.模型可以静态方式使用，也可以当构造器使用
