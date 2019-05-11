---
title: 解析程序 Web 服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 236cff15-562a-41d5-bfdc-d250186fb616
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bbb3f1478e0c6436dceafcc8874de23ee10cb2b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399703"
---
# <a name="the-resolver-web-service"></a>解析程序 Web 服务
解析程序 Web 服务是在 ESB 动态解析机制的网关。 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] 包括此服务的两个版本： ASP.NET (ASMX) 版本和 Windows Communication Foundation (WCF) 版本。 服务名称是**ESB。ResolverServices**和**ESB。ResolverServices.WCF**分别和服务公开以下方法：  
  
- **解决。** 此方法采用当作其单个参数**字符串**，其中包含请求，这符合标准的连接字符串的已注册冲突解决程序如冲突解决程序连接字符串**静态，BRE，UDDI，XPATH，路线，路线静态的 BRI，** 或**LDAP。**  
  
- **ResolveMessage。** 此方法将作为其第一个参数包含请求，这符合标准的连接字符串的已注册冲突解决程序如的冲突解决程序连接字符串的字符串**静态、 BRE、 UDDI、 XPATH、 路线，静态路线 BRI，** 或**LDAP**。 此外，该方法接受一个可选的第二个参数作为**字符串**，其中包含该服务可以使用作为可选的事实来帮助解决问题的 XML 消息文档; 例如，BRE 冲突解决程序可能需要消息正文封装的事实。  
  
  有关的冲突解决程序和 ResolverDictionary 类和其用法的详细信息，请参阅[的帮助程序类](../esb-toolkit/using-the-helper-classes.md)。  
  
## <a name="resolver-connection-strings"></a>冲突解决程序的连接字符串  
 ESB 动态解析机制使用前面有一个名字对象，指示可执行解决方法的类型的连接字符串。 受支持的名字对象包括**静态、 BRE、 UDDI、 UDDI3、 XPATH、 路线，路线静态的 BRI，** 并**LDAP**。 下面的连接字符串显示的示例**UDDI**名字对象：  
  
```  
  
//UDDI  
UDDI:\\serverUrl=http://localhost/uddi;serviceName=PurchaseOrder;serviceProvider=Microsoft.Practices.ESB  
```  
  
 有关支持的动态解析机制的连接字符串的类型的信息，请参阅[使用动态解析和路由](../esb-toolkit/using-dynamic-resolution-and-routing.md)。  
  
> [!NOTE]
>  必须配置为使用任一 Windows 集成安全性和内置网络服务帐户下运行此服务。  
>   
>  默认情况下，冲突解决程序 Web 服务未配置为需要安全套接字层 (SSL) 客户端进行访问时。 应配置服务，因此它需要 SSL 客户端访问和保护 Internet 信息服务 (IIS) Web 服务主机计算机和使用网络级别 IPSec 和相应的文件级访问 BizTalk Server 之间的连接控制列表 (ACL) 权限。 若要避免安全风险，建议不要公开此服务的受信任的子系统边界之外。