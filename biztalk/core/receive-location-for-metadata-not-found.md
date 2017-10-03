---
title: "接收位置找不到的元数据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3c397fb5-f400-4cff-85b9-5bf0d2069557
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3eb45272f7d3ef4491b59d5b019eb4499bcf5dff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="receive-location-for-metadata-not-found"></a>未找到元数据的接收位置
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|0|  
|事件源|0|  
|组件|0|  
|符号名称|0|  
|消息正文|找不到元数据的接收位置“{0}”。 （检查在 Web.config 中的接收位置映射，并验证接收位置存在）。|  
  
## <a name="explanation"></a>解释  
 此错误表明发布的独立 WCF 接收位置找不到元数据的相应接收位置。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作： 在 BizTalk 管理控制台中，请确保由 receiveLocationName 特性的 Web.config 文件中指定接收位置 BizTalk WCF 发布向导生成存在，并且已启动。  
  
 有关接收位置的其他信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  
  
-   [发布的 WCF 服务](../core/publishing-wcf-services.md)  
  
-   [如何配置 WCF BasicHttp 接收位置](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [如何配置 WCF WSHttp 接收位置](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [如何配置 WCF CustomIsolated 接收位置](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [演练： 使用 WCF NetMsmq 适配器的 WCF 服务发布](../core/walkthrough-publishing-wcf-services-with-the-wcf-netmsmq-adapter.md)