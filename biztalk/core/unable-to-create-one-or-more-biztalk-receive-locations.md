---
title: 无法创建一个或多个 BizTalk 接收位置 |Microsoft Docs
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
ms.openlocfilehash: 06f8fa39d5998b37e994cd599466eee123798292
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292807"
---
# <a name="unable-to-create-one-or-more-biztalk-receive-locations"></a>无法创建一个或多个 BizTalk 接收位置
## <a name="details"></a>详细信息  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  产品名称   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 产品版本 |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    事件 ID     |                                         0                                          |
|  事件源   |                                         0                                          |
|    组件    |                                         0                                          |
|  符号名称  |                                         0                                          |
|  消息正文   |              无法创建一个或多个 BizTalk 接收位置。               |
  
## <a name="explanation"></a>解释  
 此错误表示 BizTalk WCF 发布向导无法创建接收位置承载独立的 WCF 适配器。  
  
## <a name="user-action"></a>用户操作  
 请确保启动 BizTalk 实例。  
  
 有关其他信息创建接收位置，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]文档：  
  
-   [通过独立 WCF 接收适配器发布 WCF 服务](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [如何配置 Wcf-basichttp 接收位置](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [如何配置 Wcf-wshttp 接收位置](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [如何配置 Wcf-customisolated 接收位置](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [演练：使用 Wcf-basichttp 适配器发布 WCF 服务](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)