---
title: 找不到元数据的接收位置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3c397fb5-f400-4cff-85b9-5bf0d2069557
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8910b5877e05d72e52707c93b0fb0bf99ae78cd9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398239"
---
# <a name="receive-location-for-metadata-not-found"></a>未找到元数据的接收位置
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                           |
| 产品版本 |                                      [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                       |
|    事件 ID     |                                                                   0                                                                   |
|  事件源   |                                                                   0                                                                   |
|    组件    |                                                                   0                                                                   |
|  符号名称  |                                                                   0                                                                   |
|  消息正文   | 接收位置"{0}"找不到元数据。 （检查 Web.config 中的接收位置映射并验证该接收位置存在。） |
  
## <a name="explanation"></a>解释  
 此错误表明发布的独立的 WCF 接收位置找不到相应的接收位置的元数据。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：在 BizTalk 管理控制台中，请确保 Web.config 文件中 receiveLocationName 属性指定的接收位置 BizTalk WCF 发布向导生成存在并且已启动。  
  
 有关其他信息接收位置，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  
  
-   [发布 WCF 服务](../core/publishing-wcf-services.md)  
  
-   [如何配置 Wcf-basichttp 接收位置](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [如何配置 Wcf-wshttp 接收位置](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [如何配置 Wcf-customisolated 接收位置](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [演练：使用 Wcf-netmsmq 适配器发布 WCF 服务](../core/walkthrough-publishing-wcf-services-with-the-wcf-netmsmq-adapter.md)