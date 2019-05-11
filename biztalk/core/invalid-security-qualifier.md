---
title: 安全限定符无效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dce36f4b-ab59-41c0-8b92-3020f6393db9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48d7c57d7918557c3c17a4fa9931bb74f8c6a06b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330597"
---
# <a name="invalid-security-qualifier"></a>安全限定符无效
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                       X12Ta1InvalidSecurityQualifierDescription                        |
|  消息正文   |                               安全限定符无效                               |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法处理传入的交换，因为 ISA03 字段中的安全限定符或 UNB6.2 字段中的收件人引用密码限定符与服务架构（BaseArtifacts.dll 中的 X12ServiceSchema 或 EdifactServiceSchema）建立的枚举中的值不匹配。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保 ISA03 字段或 UNB6.2 字段与服务架构建立的枚举中的其中一个值匹配。 然后重新发送交换。