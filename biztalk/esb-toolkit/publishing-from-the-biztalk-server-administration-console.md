---
title: 从 BizTalk Server 管理控制台发布 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b78b1981-b227-4cf5-9435-6fc57963552a
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5423c228b4ea9b8cd16bdac35a0e72c2fecbc232
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65301859"
---
# <a name="publishing-from-the-biztalk-server-administration-console"></a>从 BizTalk Server 管理控制台发布
如果你想要管理通过 BizTalk Server 管理控制台，而不是 ESB 管理门户发布的终结点，就可以做到在终结点的说明字段中输入一个通用描述、 发现和集成 (UDDI) 的名字对象若要将发布到 UDDI。 下面是示例名字对象。  
  
```  
uddi://TransportType=other;Status=Published.  
```  
  
 可以设置以下 UDDI 属性使用**说明**字段在 BizTalk Server 管理控制台：  
  
-   **ModifiedBy**。 此可选属性包含修改终结点; 的用户的帐户名称例如，MyDomainName\MyUserName。  
  
-   **UDDIContact**。 此可选属性是用户的为 UDDI 业务提供程序定义的联系人的名称。  
  
-   **UDDIUserType**。 此可选属性是用户定义的 UDDI 业务提供程序的用户类型。  
  
-   **UDDIEmail**。 此可选属性是用户的 UDDI 业务提供程序定义的电子邮件地址。  
  
-   **TransportType**。 此可选属性是终结点适配器类型，例如**文件中，MQS、 Wcf-wshttp、 SOAP、 HTTP**或**FTP**。  
  
-   **状态**。 此可选属性的状态是终结点，如**已发布**或**挂起**。 UDDI 发布服务使用此属性来发现终结点的状态。  
  
-   **BindingType**。 此可选属性是特定协议 （URL 类型），UDDI 绑定支持，如**mailto，http、 https、 ftp、 传真、 电话**或**其他**。 UDDI 发布服务使用此属性来创建终结点绑定。