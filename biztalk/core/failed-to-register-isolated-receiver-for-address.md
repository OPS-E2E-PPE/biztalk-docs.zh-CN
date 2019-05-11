---
title: 无法注册独立的接收器地址 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 313b436a-d7c5-4b46-bfe3-bbad0d8efe42
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7db73ecd84218f19dbc576ae3e94dec6cef4218d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388137"
---
# <a name="failed-to-register-isolated-receiver-for-address"></a>无法为地址注册独立的接收器
## <a name="details"></a>详细信息  
  
|                 |                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------|
|  产品名称   |           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]            |
| 产品版本 |                       [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                        |
|    事件 ID     |                                                    0                                                    |
|  事件源   |                                                    0                                                    |
|    组件    |                                                    0                                                    |
|  符号名称  |                                                    0                                                    |
|  消息正文   | 未能注册独立的接收器，地址为"{0}"; 接收位置不存在或已禁用。 |
  
## <a name="explanation"></a>解释  
 此错误表明发布的独立的 WCF 接收位置找不到相应接收位置。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：在 BizTalk 管理控制台中，请确保 Web.config 文件中 receiveLocationName 属性指定的接收位置 BizTalk WCF 服务发布向导生成存在并且已启动。  
  
 有关其他信息创建接收位置，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  
  
-   [通过独立 WCF 接收适配器发布 WCF 服务](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [如何配置 Wcf-basichttp 接收位置](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [如何配置 Wcf-wshttp 接收位置](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [如何配置 Wcf-customisolated 接收位置](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [演练：使用 Wcf-basichttp 适配器发布 WCF 服务](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)