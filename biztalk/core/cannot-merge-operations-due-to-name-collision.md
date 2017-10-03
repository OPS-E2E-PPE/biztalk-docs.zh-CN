---
title: "无法合并由于名称冲突的操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81ddb8b7-6f7e-420c-b7c3-921c0e305326
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8f884b4eea6be64f1d1575b157805703d12cee3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="cannot-merge-operations-due-to-name-collision"></a>由于名称冲突，无法合并操作
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|0|  
|事件源|0|  
|组件|0|  
|符号名称|0|  
|消息正文|由于名称冲突而无法合并操作“{0}”。 Web Services 中的所有操作都必须具有唯一的名称。|  
  
## <a name="explanation"></a>解释  
 此错误表示端口名称或合并的两个不同端口的操作名称具有相同的名称。  
  
## <a name="user-action"></a>用户操作  
 使用端口配置向导，确保合并的所有端口都具有不同的端口名称和操作。  
  
 有关端口配置的其他信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  
  
-   [如何运行端口配置向导](../core/how-to-run-the-port-configuration-wizard.md)