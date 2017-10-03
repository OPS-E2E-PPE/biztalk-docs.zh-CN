---
title: "无法从绑定来验证地址获取方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b002084a-63ae-4685-8ce3-88cc6489e19e
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c952e967a391011bbd887513d58e426d90d325a1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="cannot-obtain-scheme-from-binding-to-validate-address"></a>无法从绑定来验证地址获取方案
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|0|  
|事件源|0|  
|组件|0|  
|符号名称|0|  
|消息正文|无法从绑定中获取方案以验证地址。|  
  
## <a name="explanation"></a>解释  
 已经指定的传输绑定元素没有方案。  
  
## <a name="user-action"></a>用户操作  
 确保传输绑定元素拥有有效的方案，或选择了有效的传输绑定元素。 如果使用自定义绑定，请确保指定了有效的传输绑定元素。  
  
 有关其他信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  
  
-   [配置 WCF 自定义适配器](../core/configuring-the-wcf-custom-adapter.md)