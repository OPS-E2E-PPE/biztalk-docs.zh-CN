---
title: 无效的方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3bb3e70a-d23c-45e9-bde5-edae6731e58a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b29ee2fb5361aed12c7f90a094e3abeb7296e495
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381271"
---
# <a name="invalid-scheme"></a>方案无效
## <a name="details"></a>详细信息  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  产品名称   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 产品版本 |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    事件 ID     |                                         0                                          |
|  事件源   |                                         0                                          |
|    组件    |                                         0                                          |
|  符号名称  |                                         0                                          |
|  消息正文   |                  方案无效;应为方案"{0}"或"{1}"                   |
  
## <a name="explanation"></a>解释  
 发生以下情况之一： URI （统一资源标识符） 字段中指定的地址必须以 http:// 或 https:// 开头。 或方案不匹配的传输绑定元素实现中指定的内容。  
  
## <a name="user-action"></a>用户操作  
 输入有效的代理地址以 http:// 或 https:// 开头的 URI