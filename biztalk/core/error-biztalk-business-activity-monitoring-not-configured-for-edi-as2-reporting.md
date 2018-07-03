---
title: BizTalk 业务活动监视具有尚未配置 EDI-AS2 状态报告 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2f46c1c8-2771-4b16-8fb1-71952792ac4a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb2a6b9d6eaa6ac14f51c7f05e40a9f6ccffccd5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010526"
---
# <a name="biztalk-business-activity-monitoring-has-not-been-configured-for-edi-as2-status-reporting"></a>BizTalk 业务活动监视具有尚未配置 EDI-AS2 状态报告
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                              |
| 产品版本 |                                         [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                          |
|    事件 ID     |                                                                      -                                                                      |
|  事件源   |                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                            |
|    组件    |                                                                 AS2 引擎                                                                  |
|  符号名称  |                                                                      -                                                                      |
|  消息正文   | 尚未针对 EDI/AS2 状态报告配置 BizTalk 业务活动监视。 因此将禁用状态报告功能。 |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明未启用 EDI/AS2 状态报告，因为尚未通过 BizTalk 配置向导配置业务活动监视 (BAM)。 BAM 基础结构对于 EDI/AS2 状态报告来说是必不可少的。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请运行 BizTalk 配置向导并配置业务活动监视。