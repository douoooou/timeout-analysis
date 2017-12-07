# connect-timeout analysis
## 一. Readme文档    
1. 安装
  $npm install connect-timeout
2. API 

   App.use(timeout('5s')) 
   当请求超过给定的超时时，库发出超时事件，节点继续处理缓慢的请求，直到它终止，即使您在超时回调中返回HTTP响应，缓慢的请求也将继续使用CPU和内存。为了更好控制CPU、内存、您可能需要查找很长时间的事件（第三方HTTP请求，磁盘I/O请求，数据库调用），并找到取消他们的方法，和/或关闭附加的套接字。 
   
3. 超时（时间，[选项]）  
  返回以time 毫秒为单位的超时的中间件。Time 也可以是ms模块接受的字符串。超时后，req发出‘timeout’。 
  
   **选项** 
   该timeout函数采用options可能包含以下任何键的可选对象。    
   >响应    
   > 控制此模块是否会以转发错误的形式“回应”。如果true传递超时错误，next()以便您可以自定义响应行为。这个错误有一个.timeout属性以及.status == 503。这个默认为true。  
   
   >req.clearTimeout（）  
   >清除请求的超时时间。超时被完全删除，将来不会触发此请求。  
     
   >req.timedout  
   >true如果超时被解雇; false除此以外
   
##  二.文件解读  
### 1. package.json 文件中的依赖项  
> http-errors 创建HTTP错误

 
