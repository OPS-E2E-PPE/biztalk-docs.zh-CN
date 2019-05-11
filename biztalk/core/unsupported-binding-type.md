---
title: 不支持的绑定类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5556a7d7-f092-4f69-9561-88f51ac46cc9
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6714c1acdf2f802037b8cd9509468194fee9d360
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399452"
---
# <a name="unsupported-binding-type"></a>不支持的绑定类型
## <a name="details"></a>详细信息  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  产品名称   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 产品版本 |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    事件 ID     |                                         0                                          |
|  事件源   |                                         0                                          |
|    组件    |                                         0                                          |
|  符号名称  |                                         0                                          |
|  消息正文   |                              不支持的绑定类型                              |
  
## <a name="explanation"></a>解释  
 已经选择 MsmqIntegration 绑定，但 WCF 适配器不支持该绑定。  
  
## <a name="user-action"></a>用户操作  
 使用 WCF-NetMsmq 适配器。 如果需要交换本地 MSMQ 消息，则使用 BizTalk MSMQ 适配器。  
  
 有关配置适配器的详细信息，请参阅以下资源：  
  
-   [配置 WCF-NetMsmq 适配器](../core/configuring-the-wcf-netmsmq-adapter.md)