---
title: "接收位置找不到地址 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 637f3925-06ff-47b2-99db-f85e829ee318
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1242ffc77976fb2ffcc469752d13a6f6366d7a1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="receive-location-for-address-not-found"></a>找不到地址接收位置
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|0|  
|事件源|0|  
|组件|0|  
|符号名称|0|  
|消息正文|找不到地址“{0}”的接收位置。 （BizTalk 接收位置可能已被禁用。）|  
  
## <a name="explanation"></a>解释  
 此错误表明发布的独立 WCF 接收位置找不到相应的接收位置。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作： 在 BizTalk 管理控制台中，请确保由 receiveLocationName 特性的 Web.config 文件中指定接收位置 BizTalk WCF 发布向导生成存在，并且已启动。  
  
 有关创建接收位置的其他信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  
  
-   [使用独立的 WCF 发布 WCF 服务接收适配器](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [如何配置 WCF BasicHttp 接收位置](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [如何配置 WCF WSHttp 接收位置](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [如何配置 WCF CustomIsolated 接收位置](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [演练： 使用 WCF BasicHttp 适配器的 WCF 服务发布](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)