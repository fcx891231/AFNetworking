分享我在使用过程中的点滴心得:

1.从xcode7开始,afn废除了AFHttpRequestOperationManager类,所有网络请求的发起请使用AFHttpSessionManager类.
  虽然很不习惯,但是还是得适应.
2.从xcode7开始,苹果默认不支持http请求,如果想让你的请求支持http,需要进行相关配置.
  方式一: 使用文本编辑Info.plist, 在当中添加:
<key>NSAppTransportSecurity</key>
<dict>
  <key>NSAllowsArbitraryLoads</key>
  <true/>
</dict>

  方式二: 在项目左侧找到Info.plist文件，可以通过Filter来搜索,在右侧点击Add Row添加NSAppTransportSecurity，类型为Dictionary，然后再添加子项目NSAllowsArbitraryLoads类行为Boolean值为YES即可.
  
