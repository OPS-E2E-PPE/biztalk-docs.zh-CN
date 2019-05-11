---
title: 单一登录：Event 10753 | Microsoft Docs
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
ms.openlocfilehash: ca0c0066e1643ec6cc84f19eaf1ca5ece9822e69
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65307793"
---
# <a name="single-sign-on-event-10753"></a>单一登录：事件 10753
## <a name="details"></a>详细信息  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  产品名称   |                 企业单一登录                  |
| 产品版本 | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    事件 ID     |                           10753                            |
|  事件源   |                           ENTSSO                           |
|    组件    |                            不可用                             |
|  符号名称  |                  ENTSSO_E_MAPPING_EXISTS                   |
|  消息正文   |                映射已存在。                 |
  
## <a name="explanation"></a>解释  
 此映射已经存在于已在使用中的 Windows 帐户或外部帐户。  
  
## <a name="user-action"></a>用户操作  
 检查现有映射以及想要创建的映射。 如果存在所需的映射，使用它，并删除新映射。 如果没有，请删除新映射并重新创建它。