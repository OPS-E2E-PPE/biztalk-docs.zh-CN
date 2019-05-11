---
title: 通信模式错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 06656073-9bae-4d6f-98ae-2714a72ee79c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20a878f34b1e78509bec85fedbc2cf115a7140ad
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357042"
---
# <a name="communication-pattern-errors"></a>通信模式错误
诊断和解决 WCF 通信模式错误的信息。  

## <a name="fault-messages-are-not-supported-on-one-way-ports"></a>单向端口不支持错误消息
  
|                 |                                                       错误详细信息                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                     |
| 产品版本 |                                [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                 |
|    事件 ID     |                                                             0                                                             |
|  事件源   |                                                             0                                                             |
|    组件    |                                                             0                                                             |
|  符号名称  |                                                             0                                                             |
|  消息正文   | 单向端口不支持错误消息。 更正服务说明"{0}"端口类型"{1}"，然后重新运行向导 |
  
## <a name="explanation"></a>解释  
 此错误表示尝试使用该服务是单向服务且指定了错误。  
  
## <a name="user-action"></a>用户操作  
 通过切换到请求-响应从单向通信模式来更正该服务。 或在代码中删除该故障。
 
 