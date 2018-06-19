---
title: 单一登录： 事件 10547 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: be25cdc9-d6c1-488d-9ead-877a2454c3d1
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f6162461b1eb04993ca681049fe1fbb797ca014
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270717"
---
# <a name="single-sign-on-event-10547"></a>单一登录： 事件 10547
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10547|  
|事件源|ENTSSO|  
|组件|CO|  
|符号名称|SSO_WARN_UPDATE_FAILED|  
|消息正文|无法在重新加密过程中更新 SSO 数据库中的凭据。|  
  
## <a name="explanation"></a>解释  
 此警告事件表示不可能更新凭据以完成新的加密。 当更改主密钥（通过生成新密钥或还原旧密钥）时，将在 SSO 数据库上执行重新加密，以解密使用旧密钥加密的所有密钥，并使用新密钥对其重新加密。 如果已经删除凭据，则会发生此事件，因为凭据正处于重新加密的过程中。  
  
## <a name="user-action"></a>用户操作  
 若要解决此警告问题，请执行以下操作：  
  
-   稍候一小段时间等待另一次重新加密；如果未自动发生，请重新启动 SSO 服务，这将触发新的重新加密（如果需要的话）。  
  
 有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  
  
-   [了解 SSO](../core/understanding-sso.md)