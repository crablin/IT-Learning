# Resources

## 基礎知識

1. [C# 編碼慣例](https://docs.microsoft.com/zh-tw/dotnet/csharp/programming-guide/inside-a-program/coding-conventions)

## 任務執行 - Hangfire
Fire-and-forget tasks、Delayed tasks、Recurring tasks。  

1. [Hangfire](https://www.hangfire.io/)
2. [執行後台任務的利器——Hangfire](https://read01.com/zh-tw/7O4E4n.html#.WjeT1zd-VhE)
3. [使用Hangfire處理ASP.NET MVC/Web API長時間與排程工作](http://blog.kkbruce.net/2015/09/hangfire-aspnet-mvc-webapi.html#.WjeT0jd-VhE)
4. [Hangfire解析](https://kknews.cc/zh-tw/other/6nz5obv.html)

------------

## Web API表達工具 - Swagger
 
1. [Swagger 官網](https://swagger.io/)
2. [ASP.NET Web API 文件產生器 1 - 使用 Swagger ](http://kevintsengtw.blogspot.tw/2015/12/aspnet-web-api-swagger.html)
3. [ASP.NET Web API 文件產生器 2 - 使用 Swagger ](http://blog.kkbruce.net/2015/04/aspnet-web-api-2-swagger.html)
4. [Swashbuckle - Swagger for Web Api 顯示內容的調整 ](http://kevintsengtw.blogspot.tw/2015/12/swashbuckle-swagger-for-web-api.html)

------------

## 程式守門員 - Testing

### 在測試之前先瞭解 - Dependancy Injection (DI) 觀念
目標物件與外部相依的方式僅相依於 interface，而相依 interface 的 instance 透過 constructor 或 public property 來讓外部可以注入相依實體
1. [91 的 IoC and DI 說明](https://dotblogs.com.tw/hatelove/2009/10/02/10894)
2. [保哥整理的資源](https://blog.miniasp.com/post/2009/09/27/Unity-Application-Block-and-ASPNET-MVC-Learning-Resources.aspx) - 注意「觀念建立」的段落
3. [黃忠成的觀念教學](http://blog.csdn.net/code6421/article/details/1282139)

### DI Framework: Autofac
1. [Auctofac](https://autofac.org/)
2. [ASP.NET MVC 使用 Autofac 實作 DI Framework](https://dotblogs.com.tw/chonny/2016/09/12/132259)
3. [在專案中加入Autofac](https://ithelp.ithome.com.tw/articles/10133301)
4. [ASP.net MVC 使用 DI Framework - Autofac](https://dotblogs.com.tw/mantou1201/2014/06/13/145527)
5. [Autofac筆記 1](http://blog.darkthread.net/post-2011-06-07-autofac-notes-1.aspx)

### 測試入門觀念
1. [TDD 30天入門](https://dotblogs.com.tw/hatelove/2013/01/11/learning-tdd-in-30-days-catalog-and-reference) - 基本測試觀念：「TDD 概念大綱」與「測試相關」兩大落段
2. [單元測試基本概念](https://msdn.microsoft.com/zh-tw/library/hh694602.aspx) - 注意AAA(3A)原則
3. [保哥的單元測試系列](https://blog.miniasp.com/category/Unit-Testing.aspx)
4. [保哥的與 Roy Osherove 探討單元測試的藝術 (心得筆記)](https://blog.miniasp.com/post/2010/02/21/The-Art-of-Unit-Testing-with-Roy-Osherove-Notes.aspx)

### 測試框架(Testing Framework) - MSTest
1. [MsTest](https://docs.microsoft.com/zh-tw/visualstudio/test/unit-test-your-code)
2. [如何撰寫單元測試](https://dotblogs.com.tw/hatelove/2012/11/07/learning-tdd-in-30-days-day3-how-to-write-a-unit-test-code)
3. [Web API的單元測試](https://docs.microsoft.com/en-us/aspnet/web-api/overview/testing-and-debugging/unit-testing-with-aspnet-web-api)
4. [Unit Test Tricks 如何驗證兩個自訂型別物件集合相等](https://dotblogs.com.tw/hatelove/2014/06/06/how-to-assert-two-collection-equal)
5. [Unit Test Controller - DataAnnotation Validation](http://geekswithblogs.net/80n/archive/2012/03/13/unittesting-controller-dataannotation-validation-in-mvc3--modelstate.isvalid-always-true.aspx)

### 測試框架(Testing Framework) - NUnit
1. [NUnit](http://nunit.org/)
2. [NUnit - 測試案例 TestCaseAttribute](https://blog.johnwu.cc/article/nunit-test-case-attribute.html)
3. [NUnit - 測試案例生命週期 Life Cycle](https://blog.johnwu.cc/article/nunit-life-cycle.html)
4. [NUnit - 測試案例 TestCaseSourceAttribute](https://blog.johnwu.cc/article/nunit-test-case-source-attribute.html)

### Isolation Framework / Mock Framework
1. [Stub, Mock, Fake 簡介](https://dotblogs.com.tw/hatelove/2012/11/29/learning-tdd-in-30-days-day7-unit-testing-stub-mock-and-fake-object-introduction)
2. [91 - Stub的原理 Why we need mock rather than stub](https://dotblogs.com.tw/hatelove/2010/08/14/stub-and-mock-by-nunit)
2. 模擬目標物件的部分
    3-1. [Stub Objcet](https://www.microsoft.com/en-us/research/project/stubs-lightweight-test-stubs-for-net/) - 通常使用在驗證目標回傳值，以及驗證目標物件狀態的改變。
    3-2. [Mock Objcet](https://blog.miniasp.com/post/2010/09/16/ASPNET-MVC-Unit-Testing-Part-03-Using-Mock-moq.aspx) - 驗證目標物件與外部相依介面的互動方式。Mock 的驗證比起 stub 要複雜許多，變動性通常也會大一點，但往往在驗證一些 void 的行為會使用到，例如：在某個條件發生時，要記錄 Log。這種情境，用 stub 就很難驗證，因為對目標物件來說，沒有回傳值，也沒有狀態變化，就只能透過 mock object 來驗證，目標物件是否正確的與Log 介面進行互動。
    3-3. [Fake Object]() - 當目標物件使用到靜態方法，或 .net framework 本身的物件，甚至於針對一般直接相依的物件，我們都可以透過 fake object 的方式，直接模擬相依物件的行為。
3. [Microsoft Fakes 入門](http://www.huanlintalk.com/2012/10/microsoft-fakes.html)
4. [NSubstitute](http://nsubstitute.github.io/) - A friendly substitute for .NET mocking frameworks
5. [單元測試 Mock Framework - NSubstitute](https://dotblogs.com.tw/yc421206/2015/02/16/149495)
6. [如何使用 NSubstitute 模擬被測物件與其它物件互動](https://dotblogs.com.tw/yc421206/2015/02/17/149512)


### Others
1. [.Net 測試工具與Framework清單](https://github.com/dariusz-wozniak/List-of-Testing-Tools-and-Frameworks-for-.NET/blob/master/README.md)

------------

## AutoMapper
1. [Doc](http://docs.automapper.org/en/stable/Getting-started.html)

------------

## C#
1. [Class **?.** Property](https://stackoverflow.com/questions/28352072/what-does-question-mark-and-dot-operator-mean-in-c-sharp-6-0)

------------

## SQL
1. [ParentChildHierarchy](https://www.codeproject.com/Articles/818694/SQL-queries-to-manage-hierarchical-or-parent-child)
2. [FOR XML PATH](https://dotblogs.com.tw/kevinya/2012/06/01/72553)

------------
## JWT
1. https://stackoverflow.com/questions/40281050/jwt-authentication-for-asp-net-web-api
2. http://jakubskoczen.pl/2017/04/12/en-token-authentication-in-asp-net-core-web-api/
3. [實作:  驗證帶Token來的 Request](https://stormpath.com/blog/token-authentication-asp-net-core)
4. [解釋Token機制 與 CreateToken的實作](http://jakubskoczen.pl/2017/04/12/en-token-authentication-in-asp-net-core-web-api/)
5. https://stackoverflow.com/questions/40281050/jwt-authentication-for-asp-net-web-api