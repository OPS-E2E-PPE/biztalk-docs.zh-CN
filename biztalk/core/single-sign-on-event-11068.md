---
title: 单一登录： 事件 11068 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f09a1191-ae67-4156-a8a5-d24e4439fc68
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be824a9205d81aaaeb9fd87129133b94b4f2e379
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277805"
---
# <a name="single-sign-on-event-11068"></a>单一登录： 事件 11068
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|11068|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|SSO_ERROR_LOOKUP_CALLBACK_ACCESS_DENIED_NO_REMOTE|  
|消息正文|查找服务器访问被拒绝。 此 SSO 服务器当前未配置为允许远程查找。 请使用“ssoconfig -remoteLookup yes”或 SSO 管理 MMC。%r|  
  
## <a name="explanation"></a>解释  
 由于 ENTSSO 服务器未配置为允许远程查找，因此查找服务器访问已被拒绝。  
  
## <a name="user-action"></a>用户操作  
 若要允许远程查找中**服务器管理单元中**，**高级**选项卡上，选择**允许远程查找**。  
  
 有关详细信息，请参阅[如何使用服务器管理单元](../core/how-to-use-the-servers-snap-in.md)。