---
title: 单一登录： 事件 10806 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 23650d6b-b6a4-4c41-96cd-476e5b0f7f63
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd3f432a408cffcbd1ccd27508550fd0888c5213
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277173"
---
# <a name="single-sign-on-event-10806"></a>单一登录： 事件 10806
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10806|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|ENTSSO_E_APP_ASSIGNED_TO_ADAPTER|  
|消息正文|无法删除该应用程序，因为它当前已分配给某个适配器。|  
  
## <a name="explanation"></a>解释  
 应用程序被分配到适配器后无法删除。  
  
## <a name="user-action"></a>用户操作  
 取消将应用程序分配到适合器，然后再将其删除。