---
title: 无法导入服务终结点配置。 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6dae5154-04e2-4d9b-b2b2-85313683fd9e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85d6fb8006020c47dcec56aa2a173fa36a1aff28
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292756"
---
# <a name="unable-to-import-service-endpoint-configuration"></a>无法导入服务终结点配置。
## <a name="details"></a>详细信息  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  产品名称   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 产品版本 |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    事件 ID     |                                         0                                          |
|  事件源   |                                         0                                          |
|    组件    |                                         0                                          |
|  符号名称  |                                         0                                          |
|  消息正文   |                  无法导入服务终结点配置                   |
  
## <a name="explanation"></a>解释  
 可能有多个解释此错误。 配置文件可能包含无效字符。 可能缺少根元素。 根级别的数据可能无效。  
  
## <a name="user-action"></a>用户操作  
 验证配置文件的有效性。 尝试使用服务配置编辑器中打开配置文件 (**svcConfigEditor.exe**)，并验证每个属性。