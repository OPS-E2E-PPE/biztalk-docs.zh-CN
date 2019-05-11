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
ms.openlocfilehash: 4f4693321e02d0da6d8cec9b5ae1542fd62af6c5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400542"
---
# <a name="there-are-no-orchestrations-with-public-receive-ports-in-this-biztalk-assembly"></a>在此 BizTalk 程序集中的业务流程不具有公共接收端口
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                               |
| 产品版本 |                                                          [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                           |
|    事件 ID     |                                                                                       0                                                                                       |
|  事件源   |                                                                                       0                                                                                       |
|    组件    |                                                                                       0                                                                                       |
|  符号名称  |                                                                                       0                                                                                       |
|  消息正文   | 在此 BizTalk 程序集中的业务流程不具有公共接收端口。 单击后退，并指定 BizTalk 程序集包含业务流程具有公共接收端口 |
  
## <a name="explanation"></a>解释  
 此错误表示选择的业务流程不具有公共端口。  
  
## <a name="user-action"></a>用户操作  
 使用以下过程来配置公共端口。  
  
#### <a name="to-configure-a-public-port"></a>若要配置的公共端口  
  
1.  找到业务流程并公开所需接收端口。  
  
    1.  打开端口配置向导。  
  
    2.  在中**选择端口类型**，更改**访问限制**从**内部**（默认值） 到**公有-无限制**。  
  
2.  重新编译该程序集。  
  
     \- 或 -  
  
     加载 BizTalk 程序集具有公共接收端口。