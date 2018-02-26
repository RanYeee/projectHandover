# 电子处方WKWebview

#### wkwebview结构

#### ![](/assets/屏幕快照 2018-02-26 下午4.49.52.png)

####  初始化H5页面的方法：

```c
/**
 初始化webview

 @param htmlName 本地html文件名
 @param jsonData 需要传的参数
 @return webview对象
 */
- (instancetype)initWithHtmlName:(NSString *)htmlName jsonData:(NSDictionary *)jsonData;
```

例如：

`WKDetailViewController *searchVC = [[WKDetailViewControlleralloc]initWithHtmlName:@"filtrate"jsonData:nil];`

