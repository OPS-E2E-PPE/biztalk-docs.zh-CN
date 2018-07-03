---
title: 单一登录： 事件 10753 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6b538083-180b-4a15-bedf-aac4fc351c30
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10fb7980b8c039c6ef02e52952564c581e88054b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969078"
---
# <a name="single-sign-on-event-10753"></a>单一登录： 事件 10753
## <a name="details"></a>详细信息  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  产品名称   |                 企业单一登录                  |
| 产品版本 | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    事件 ID     |                           10753                            |
|  事件源   |                           ENTSSO                           |
|    组件    |                            N/A                             |
|  符号名称  |                  ENTSSO_E_MAPPING_EXISTS                   |
|  消息正文   |                映射已存在。                 |
  
## <a name="explanation"></a>解释  
 此映射已经存在于已经使用的 Windows 帐户或外部帐户。  
  
## <a name="user-action"></a>用户操作  
 检查现有映射和您尝试创建的映射。 如果您需要的映射已经存在，则使用该映射并删除新映射。 如果不存在，则删除新映射并重新创建。