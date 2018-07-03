---
title: 在此 BizTalk 程序集中的业务流程不具有公共接收端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb901d49-ce3c-4bc6-806a-eb5964d32bb4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c062f5e23972ed841c4c9d614ad58967a07a4fe2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978212"
---
# <a name="there-are-no-orchestrations-with-public-receive-ports-in-this-biztalk-assembly"></a>此 BizTalk 程序集未包含具有公共接收端口的业务流程
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                               |
| 产品版本 |                                                          [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                           |
|    事件 ID     |                                                                                       0                                                                                       |
|  事件源   |                                                                                       0                                                                                       |
|    组件    |                                                                                       0                                                                                       |
|  符号名称  |                                                                                       0                                                                                       |
|  消息正文   | 此 BizTalk 程序集中的业务流程不具有公共接收端口。 单击“上一步”，并指定包含具有公共接收端口的业务流程的 BizTalk 程序集 |
  
## <a name="explanation"></a>解释  
 此错误表明选择的业务流程不具有公共端口。  
  
## <a name="user-action"></a>用户操作  
 使用以下过程配置公共端口。  
  
#### <a name="to-configure-a-public-port"></a>配置公共端口  
  
1.  找到业务流程，并使所需接收端口成为公共端口。  
  
    1.  打开端口配置向导。  
  
    2.  在中**选择端口类型**，更改**访问限制**从**内部**（默认值） 到**公有-无限制**。  
  
2.  重新编译程序集。  
  
     \- 或 -  
  
     加载具有公共接收端口的 BizTalk 程序集。