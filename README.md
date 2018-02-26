# 电子处方WKWebview

#### wkwebview结构

#### ![](/assets/屏幕快照 2018-02-26 下午4.49.52.png)

#### 初始化H5页面的方法：

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

#### OC回传数据到JS：

```cpp
/**
 *  调用js的OnComplete函数
 *
 *  @param port       用于结果回调的标识
 *  @param resultData jsons数据
 *  @param Complete   完成的回调
 */
-(void)onCompleteWithPort:(NSString *)port resultData:(NSString *)resultData Complete:(CallBackComplete)completeBlock;
```

#### OC接收JS的指令：

js端通过prompt的形式发送端口和json参数给OC，OC通过 `runJavaScriptTextInputPanelWithPrompt`

接收js数据，并且判断js指令，详细交互和接口看 “电子处方JS与原生交互规则.docx”！

若需要增加与H5交互的原生接口，可以新建类并且继承`WKBaseWebViewController`

实现`- (void)excusePromptWithPrompt:(NSString *)prompt;`该方法来接收js传给OC的指令。

