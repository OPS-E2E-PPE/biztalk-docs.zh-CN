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
ms.openlocfilehash: 4fd4a91535c7872bb5be7328755808eb91758db6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989310"
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
|  消息正文   | 无法创建标准元数据绑定方案"{0}"。 受支持的方案包括：http、https、net.pipe 和 net.tcp |
  
## <a name="explanation"></a>解释  
 此错误表示尝试使用元数据的服务是一个不受支持的方案。  
  
## <a name="user-action"></a>用户操作  
 针对新的元数据位置，使用有效的方案发布元数据，然后再次运行向导。  
  
 有关适配器和绑定的其他信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  
  
-   [WCF 适配器](../core/wcf-adapters.md)