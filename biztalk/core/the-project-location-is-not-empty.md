---
title: "项目位置不为空 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: db353050-3662-4ab6-8898-4e4d3bd78ac1
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2de1e1dd381a75f596b4980430ddcc5d6d8982b6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-project-location-is-not-empty"></a>项目位置不为空
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|0|  
|事件源|0|  
|组件|0|  
|符号名称|0|  
|消息正文|项目位置“{0}”不为空。 你需要执行下列操作之一： 1。 选择新的项目中，2 的不同位置。 指定覆盖才能重复使用现有的位置或 3。 手动删除的项目位置的内容。|  
  
## <a name="explanation"></a>解释  
 此错误表明尝试发布服务的虚拟目录不为空。  
  
## <a name="user-action"></a>用户操作  
 选择覆盖位置以重新使用相同的位置。 或者指定一个新位置。  在 WCF 服务发布向导中，选择**覆盖现有位置**单击**下一步**。 此步骤将覆盖该位置。