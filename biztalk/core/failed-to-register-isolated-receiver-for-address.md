---
title: "未能注册地址的独立接收方 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 313b436a-d7c5-4b46-bfe3-bbad0d8efe42
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: edd55360a1638128ed687cf83f2e05bf52ad9dfe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="failed-to-register-isolated-receiver-for-address"></a>无法为地址注册独立的接收器
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|0|  
|事件源|0|  
|组件|0|  
|符号名称|0|  
|消息正文|无法为地址“{0}”注册独立的接收器；接收位置不存在或已禁用。|  
  
## <a name="explanation"></a>解释  
 此错误表明发布的独立 WCF 接收位置找不到相应的接收位置。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作： 在 BizTalk 管理控制台中，请确保由 receiveLocationName 特性的 Web.config 文件中指定接收位置的 BizTalk WCF 服务发布向导生成存在并且启动。  
  
 有关创建接收位置的其他信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  
  
-   [使用独立的 WCF 发布 WCF 服务接收适配器](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [如何配置 WCF BasicHttp 接收位置](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [如何配置 WCF WSHttp 接收位置](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [如何配置 WCF CustomIsolated 接收位置](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [演练： 使用 WCF BasicHttp 适配器的 WCF 服务发布](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)