---
title: "从 BizTalk Server 管理控制台发布 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b78b1981-b227-4cf5-9435-6fc57963552a
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 313bfb773a94914ed9bebd3930dfd0033ecf4ac3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="publishing-from-the-biztalk-server-administration-console"></a>从 BizTalk Server 管理控制台发布
如果你想要管理通过终结点发布[!INCLUDE[prague](../includes/prague-md.md)]而不是 ESB 管理门户管理控制台中，你可以做到这一点在的说明字段中输入一个通用、 描述、 发现和集成 (UDDI) 的名字对象若要将发布到 UDDI 的终结点。 下面是示例标记。  
  
```  
uddi://TransportType=other;Status=Published.  
```  
  
 你可以设置以下 UDDI 属性使用**说明**字段[!INCLUDE[prague](../includes/prague-md.md)]管理控制台：  
  
-   **ModifiedBy**。 此可选属性包含的用户的修改终结点，该帐户名例如，MyDomainName\MyUserName。  
  
-   **UDDIContact**。 此可选属性是为 UDDI 业务提供程序定义的用户的联系人姓名。  
  
-   **UDDIUserType**。 此可选属性是用户定义 UDDI 业务提供程序的用户类型。  
  
-   **UDDIEmail**。 此可选属性是为 UDDI 业务提供程序定义的用户的电子邮件地址。  
  
-   **TransportType**。 此可选属性是终结点适配器类型，如**文件、 MQS、 WCF WsHttp、 SOAP、 HTTP、**或**FTP**。  
  
-   **状态**。 此可选属性是，终结点的状态，如**已发布**或**挂起**。 UDDI 发布服务使用此属性来发现终结点的状态。  
  
-   **BindingType**。 此可选属性是特定的协议 （URL 类型） UDDI 绑定支持，如**mailto，http、 https、 ftp、 传真、 phone**或**其他**。 UDDI 发布服务使用此属性来创建终结点绑定。