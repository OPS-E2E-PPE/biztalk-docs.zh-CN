---
title: 无法创建绑定个方案的标准元数据 |Microsoft 文档
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
ms.openlocfilehash: 3228da0dfee18581c5fa8105ce3dd480380cc034
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231165"
---
# <a name="cannot-create-standard-metadata-binding-for-scheme"></a>无法为架构创建标准元数据绑定
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|0|  
|事件源|0|  
|组件|0|  
|符号名称|0|  
|消息正文|无法为方案“{0}”创建标准元数据绑定。 受支持的方案包括：http、https、net.pipe 和 net.tcp|  
  
## <a name="explanation"></a>解释  
 此错误表示尝试使用元数据的服务是一个不受支持的方案。  
  
## <a name="user-action"></a>用户操作  
 针对新的元数据位置，使用有效的方案发布元数据，然后再次运行向导。  
  
 有关适配器和绑定的其他信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  
  
-   [WCF 适配器](../core/wcf-adapters.md)