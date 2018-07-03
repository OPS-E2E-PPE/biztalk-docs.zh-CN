---
title: 找不到地址接收位置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 637f3925-06ff-47b2-99db-f85e829ee318
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55b3744f6590ee706bcc3df4124f964306634ca5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994942"
---
# <a name="receive-location-for-address-not-found"></a>找不到地址接收位置
## <a name="details"></a>详细信息  
  
|                 |                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------|
|  产品名称   |      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]       |
| 产品版本 |                  [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                   |
|    事件 ID     |                                               0                                               |
|  事件源   |                                               0                                               |
|    组件    |                                               0                                               |
|  符号名称  |                                               0                                               |
|  消息正文   | 地址的接收位置"{0}"找不到。 （BizTalk 接收位置可能已被禁用。） |
  
## <a name="explanation"></a>解释  
 此错误表明发布的独立 WCF 接收位置找不到相应的接收位置。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下： 在 BizTalk 管理控制台中，请确保 Web.config 文件中 receiveLocationName 属性指定的接收位置 BizTalk WCF 发布向导生成存在并且已启动。  
  
 有关创建接收位置的其他信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  
  
-   [通过独立 WCF 接收适配器发布 WCF 服务](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [如何配置 Wcf-basichttp 接收位置](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [如何配置 Wcf-wshttp 接收位置](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [如何配置 Wcf-customisolated 接收位置](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [演练：通过 WCF-BasicHttp 适配器发布 WCF 服务](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)