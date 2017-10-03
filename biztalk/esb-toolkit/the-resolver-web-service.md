---
title: "解析程序 Web 服务 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 236cff15-562a-41d5-bfdc-d250186fb616
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 916181431686ca729c0751d9362570afb7dddeee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-resolver-web-service"></a>解析程序 Web 服务
冲突解决程序 Web 服务是网关置于 ESB 动态解决机制。 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包括此服务的两个版本： ASP.NET (ASMX) 版本和 Windows Communication Foundation (WCF) 版本。 服务名称**ESB。ResolverServices**和**ESB。ResolverServices.WCF**分别和服务公开以下方法：  
  
-   **解决。** 此方法将作为其单个参数**字符串**，其中包含该请求，这符合标准连接字符串的已注册的解析程序如冲突解决程序连接字符串**静态、 BRE、 UDDI，XPATH、 路线，路线静态、 BRI，**或**LDAP。**  
  
-   **ResolveMessage。** 此方法将其第一个参数作为一个字符串，包含该请求，这符合标准连接字符串的已注册的解析程序如的冲突解决程序连接字符串**静态、 BRE、 UDDI、 XPATH、 路线，路线静态、 BRI，**或**LDAP**。 此外，该方法将接受可选的第二个参数，作为**字符串**，其中包含此服务可以使用作为可选的事实数据以帮助解决问题的 XML 消息文档; 例如，BRE 冲突解决程序可能需要消息正文封装事实。  
  
 有关的冲突解决程序和 ResolverDictionary 类和其用法的详细信息，请参阅[使用帮助器类](../esb-toolkit/using-the-helper-classes.md)。  
  
## <a name="resolver-connection-strings"></a>冲突解决程序连接字符串  
 ESB 动态解决机制使用前面是名字对象，该值指示可执行的解决方法的类型的连接字符串。 支持的名字对象包括**静态、 BRE、 UDDI、 UDDI3、 XPATH、 路线，路线静态、 BRI，**和**LDAP**。 以下连接字符串举例说明**UDDI**名字对象：  
  
```  
  
//UDDI  
UDDI:\\serverUrl=http://localhost/uddi;serviceName=PurchaseOrder;serviceProvider=Microsoft.Practices.ESB  
```  
  
 有关支持的动态解决机制的连接字符串的类型的信息，请参阅[使用动态解析和路由](../esb-toolkit/using-dynamic-resolution-and-routing.md)。  
  
> [!NOTE]
>  你必须配置此服务以使用任一 Windows 集成安全性和内置的网络服务帐户下运行。  
>   
>  默认情况下，冲突解决程序 Web 服务未配置为要求安全套接字层 (SSL) 时的客户端访问。 你应配置服务，因此需要 SSL 的客户端访问和保护 Internet Information Services (IIS) Web 服务主机计算机和使用网络级别 IPSec 和相应的文件级访问你 BizTalk Server 之间的连接控制列表 (ACL) 权限。 若要避免安全风险，建议不要公开此服务的受信任的子系统的边界之外。