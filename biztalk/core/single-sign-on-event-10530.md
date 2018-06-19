---
title: 单一登录： 事件 10530 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4bb37305-26fe-46a7-958d-3ed7f6876a7b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8cf8759d2fe3b2281b87ffe9841bdd4e6b44081a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270669"
---
# <a name="single-sign-on-event-10530"></a>单一登录： 事件 10530
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10530|  
|事件源|ENTSSO|  
|组件|N\A|  
|符号名称|SSO_INFO_GOT_PREVIOUS_SECRET|  
|消息正文|从主密钥服务器获取以前的密钥。%r<br /><br /> 机密的服务器名称: %1 %r<br /><br /> MSID: %2|  
  
## <a name="explanation"></a>解释  
 此信息事件指示 SSO 具有以前的主密钥。  
  
## <a name="user-action"></a>用户操作  
  
-   不需要用户进行任何操作。  
  
 有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  
  
-   [如何生成主密钥](../core/how-to-generate-the-master-secret.md)  
  
-   [管理主密钥](../core/managing-the-master-secret.md)