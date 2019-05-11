---
title: 无法创建标准元数据绑定方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce441c3e-0f6e-46ed-90cf-825dbf89d910
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d45e8e983e626db3b48c4875573fd7e3a92d50e1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357653"
---
# <a name="cannot-create-standard-metadata-binding-for-scheme"></a>无法为架构创建标准元数据绑定
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                 |
| 产品版本 |                             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                             |
|    事件 ID     |                                                         0                                                          |
|  事件源   |                                                         0                                                          |
|    组件    |                                                         0                                                          |
|  符号名称  |                                                         0                                                          |
|  消息正文   | 无法创建标准元数据绑定方案"{0}"。 支持的方案是 http、 https、 net.pipe 和 net.tcp |
  
## <a name="explanation"></a>解释  
 此错误表示从其元数据尝试使用此服务处于不受支持的方案。  
  
## <a name="user-action"></a>用户操作  
 发布具有有效的方案的元数据，然后再次运行向导，针对新的元数据位置。  
  
 有关适配器和绑定的其他信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  
  
-   [WCF 适配器](../core/wcf-adapters.md)