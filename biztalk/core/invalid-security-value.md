---
title: 安全值无效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ee380da7-c05e-4b9b-84ee-f7ffee90eb0e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ded2a080511992f5e85cda91b39dced703f452f5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381212"
---
# <a name="invalid-security-value"></a>安全值无效
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                         X12Ta1InvalidSecurityValueDescription                          |
|  消息正文   |                                 安全值无效                                 |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道不无法处理传入的交换，因为 ISA04 字段中的安全信息或 UNB6.1 字段中的收件人引用密码值不符合的数据类型和建立服务架构 （X12ServiceSchema 或 EdifactServiceSchema 在 BaseArtifacts.dll 中） 的数字个数。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保 ISA04 字段为 X12_AN 数据类型且为 10 个字符 （带或不带尾部空格） 或者 UNB6.1 字段为 EDIFACT_AN 数据类型的并且是介于 1 到 14 个字符之间。 然后重新发送交换。