---
title: 创建自定义适配器提供程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bb93acf8-fd9d-4315-8690-f0c152a954b5
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e6cc8b50a350e13c0269718783a33923d76490b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291508"
---
# <a name="creating-a-custom-adapter-provider"></a>创建自定义适配器提供程序
冲突解决程序执行，如前面各节中所述后，动态解析服务将检查结果是否为终结点 （未转换）。 如果它是一个终结点，服务实例化适配器管理器，它是实例的**AdapterMgr**类。  
  
 适配器管理器验证和修补程序的传输类型和出站传输位置。 如果仍未得到解决，传输类型和 URL 以"http"或"https"开头，适配器管理器设置为"Wcf-wshttp"的传输类型。  
  
 接下来，适配器管理器验证的传输类型等同于是有效的 Microsoft BizTalk Server 适配器，然后返回其属性命名空间。 此过程只运行一次所有适配器，并将结果存储在缓存中以避免重复的查询的其他使用相同的适配器的传入消息。  
  
 适配器管理器使用的传输类型 (而无需"**://**"后缀) 来确定相应的适配器提供程序。 适配器提供程序是必须实现的自定义程序集**IAdapterProvider**接口。 适配器提供程序使用的属性**解析**结构**字典**实例生成的设置，使消息的所有特定于协议的属性的冲突解决程序Microsoft BizTalk Server 运行时引擎执行动态解析。  
  
 如使用冲突解决程序 （在上一部分中所述，） 的动态解析机制使用条目 Esb.config 配置文件中查找适配器提供程序。 以下 XML 显示配置文件的一部分。  
  
```xml  
<adapterProviders cacheManager= "Adapter Providers Cache Manager"  absoluteExpiration="3600">  
     <adapterProvider name="WCF-WSHttp" type="Microsoft.Practices.ESB.Adapter.WcfWSHttp.AdapterProvider, Microsoft.Practices.ESB.Adapter.WcfWSHttp, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22" moniker="Http,Https" />  
     <adapterProvider name="WCF-BasicHttp" type="Microsoft.Practices.ESB.Adapter.WcfBasicHttp.AdapterProvider, Microsoft.Practices.ESB.Adapter.WcfBasicHttp, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22" moniker="Http,Https" />  
     <adapterProvider name="WCF-Custom" type="Microsoft.Practices.ESB.Adapter.WcfCustom.AdapterProvider, Microsoft.Practices.ESB.Adapter.WcfCustom, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22" moniker="mssql" />  
     <adapterProvider name="SMTP" type="Microsoft.Practices.ESB.Adapter.SMTP.AdapterProvider, Microsoft.Practices.ESB.Adapter.SMTP, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22" moniker="smtp" />  
     <adapterProvider name="FTP" type="Microsoft.Practices.ESB.Adapter.FTP.AdapterProvider, Microsoft.Practices.ESB.Adapter.FTP, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22">  
          <adapterConfig>  
               <add name="DefaultUsername" value="anonymous" />  
               <add name="DefaultPassword" value="" />  
          </adapterConfig>  
     </adapterProvider>  
     <adapterProvider name="MQSeries" type="Microsoft.Practices.ESB.Adapter.MQSeries.AdapterProvider, Microsoft.Practices.ESB.Adapter.MQSeries, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22" moniker="MQS" adapterAssembly="MQSeries, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />  
     <adapterProvider name="FILE" type="Microsoft.Practices.ESB.Adapter.FILE.AdapterProvider, Microsoft.Practices.ESB.Adapter.FILE, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22" moniker="File" />  
</adapterProviders>  
```  
  
## <a name="creating-a-custom-adapter-provider"></a>创建自定义适配器提供程序  
 适配器管理器 (的实例**AdapterMgr**类) 适配器提供程序配置文件中查找并加载相应的程序集。 动态解析机制缓存的所有已加载的具体实现**IAdapterProvider**接口以避免重复的读取配置信息和程序集加载时使用多个传入消息同一适配器提供程序。  
  
 最后，适配器管理器执行**SetEndPoint**方法的具体实现**IAdapterProvider**接口和管道组件将消息返回到 BizTalkMessagebox 数据库。  
  
 **若要创建自定义适配器提供程序**  
  
1.  创建派生自的程序集**BaseAdapterProvider**基本类和包含**SetEndPoint**设置的终结点的消息上下文属性的方法。  
  
2.  通过将其添加到 Esb.config 配置文件使用注册适配器提供程序**\<adapterProvider\>** 替换为作为适配器的名称元素**名称**属性，作为类的完全限定的名称**类型**属性，作为名字对象**名字对象**（多个值应由逗号分隔） 的属性，并根据需要的程序集作为实际适配器**adapterAssembly**属性。  
  
3.  在全局程序集缓存中注册新的程序集。