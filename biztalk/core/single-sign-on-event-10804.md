---
title: 单一登录： 事件 10804 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4d98bef-fdc3-4627-bb5b-663fa502b965
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b65c59ce736804215cd7c70428905d776d8e0e4b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276645"
---
# <a name="single-sign-on-event-10804"></a>单一登录： 事件 10804
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10804|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|ENTSSO_E_INCORRECT_COMPUTER|  
|消息正文|此适配器未配置为此计算机使用。|  
  
## <a name="explanation"></a>解释  
 每个适配器都配置为在特定计算机上运行，由长名称识别。 名称不正确，或正在尝试在不同计算机上运行适配器。  
  
## <a name="user-action"></a>用户操作  
 请查看此适配器的配置以确定相应计算机的正确名称。