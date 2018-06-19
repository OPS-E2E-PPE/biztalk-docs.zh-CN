---
title: 无法创建一个或多个 BizTalk 接收位置 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b564f87b-34ba-400e-9a71-bd66081fc1b8
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b87f8e4874f2f59f26a58a8c4f40f93e5073207c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286733"
---
# <a name="unable-to-create-one-or-more-biztalk-receive-locations"></a>无法创建一个或多个 BizTalk 接收位置
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|0|  
|事件源|0|  
|组件|0|  
|符号名称|0|  
|消息正文|无法创建一个或多个 BizTalk 接收位置。|  
  
## <a name="explanation"></a>解释  
 此错误表示 BizTalk WCF 发布向导创建宿主独立 WCF 适配器的接收位置时失败。  
  
## <a name="user-action"></a>用户操作  
 确保已启动 BizTalk 实例。  
  
 有关创建接收位置的其他信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 文档中的以下资源：  
  
-   [使用独立的 WCF 发布 WCF 服务接收适配器](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [如何配置 WCF BasicHttp 接收位置](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [如何配置 WCF WSHttp 接收位置](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [如何配置 WCF CustomIsolated 接收位置](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [演练： 使用 WCF BasicHttp 适配器的 WCF 服务发布](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)