---
title: 无法导入客户端终结点配置 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8375e153-ed1c-4bf4-b461-ac026a4b3478
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30be7958ca07dde47d147711da06a276e86ff714
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286605"
---
# <a name="unable-to-import-client-endpoint-configuration"></a>无法导入客户端终结点配置
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|0|  
|事件源|0|  
|组件|0|  
|符号名称|0|  
|消息正文|无法导入客户端终结点配置|  
  
## <a name="explanation"></a>解释  
 对于此错误可能有多种解释。 配置文件可能包含无效的字符。 根元素可能丢失。 根级别的数据可能无效。  
  
## <a name="user-action"></a>用户操作  
 验证配置文件是否有效。 尝试打开用服务配置编辑器中的配置文件 (**svcConfigEditor.exe**) 并验证每个属性。