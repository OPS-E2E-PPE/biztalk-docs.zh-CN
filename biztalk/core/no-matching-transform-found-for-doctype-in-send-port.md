---
title: 发送端口中找到 DocType 为没有匹配的转换 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 23f62ac7-3849-49fe-a765-2be72880a4c9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9668694f5cde2e99775d1392c8722bad0645b251
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966206"
---
# <a name="no-matching-transform-found-for-doctype-in-send-port"></a>发送端口中找不到与 DocType 匹配的转换
## <a name="details"></a>详细信息  
  
|                 |                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------|
|  产品名称   |           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]           |
| 产品版本 |                       [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                       |
|    事件 ID     |                                                   -                                                    |
|  事件源   |         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI         |
|    组件    |                                               EDI 引擎                                               |
|  符号名称  |                             NoMatchingTransformFoundForSendPortAndDocType                              |
|  消息正文   | 不匹配转换找到 DocType{0}发送端口中{1}。 与 ExplorerOM 信息不一致 |
  
## <a name="explanation"></a>解释  
 此错误表明没有为给定的 DocType 和 SendPort 找到匹配的转换。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请继续执行以下操作：  
  
1.  打开 BizTalk 管理控制台，找到传输并右键单击传输名称。  
  
2.  单击 **“属性”**。  
  
3.  在端口类型列表中，选择正确的端口。 单击**配置**。  
  
4.  在 [端口名称] 发送端口属性对话框中，单击**出站映射**的左窗格中。  
  
5.  验证此处是否列出了映射以及该映射是否与正确的文档类型相对应。