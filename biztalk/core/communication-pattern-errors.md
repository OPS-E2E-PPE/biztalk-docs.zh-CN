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
ms.openlocfilehash: ef9f7f4419d6c95b9b11343f395ab8e3d17c7c34
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021080"
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
|  消息正文   | 单向端口上不支持错误消息。 更正服务说明"{0}"端口类型"{1}"，然后重新运行向导 |
  
## <a name="explanation"></a>解释  
 此错误表示尝试使用的服务是单向服务，并且指定了错误。  
  
## <a name="user-action"></a>用户操作  
 通过将通信模式从单向模式切换到请求-响应模式来更正服务。 或者从代码中删除此错误。
 
 