---
title: 单一登录： 事件 10765 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e28fe42e-aa2b-4be4-b757-bc9c5c37526b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c0fbc04f4c8fc98a87de87a4cd48529a3ca7e2e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278413"
---
# <a name="single-sign-on-event-10765"></a>单一登录： 事件 10765
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10765|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|ENTSSO_E_NO_CREDENTIALS|  
|消息正文|尚未为此映射设置凭据。|  
  
## <a name="explanation"></a>解释  
 您请求了一个映射的 GetCredentials，但指定的映射没有凭据。  
  
## <a name="user-action"></a>用户操作  
 使用命令行或 MMC 管理单元为映射设置凭据。