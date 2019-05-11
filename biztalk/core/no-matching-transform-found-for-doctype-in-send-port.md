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
ms.openlocfilehash: fd58b772afe9695d526038f622d968c75b75d252
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65263404"
---
# <a name="no-matching-transform-found-for-doctype-in-send-port"></a>发送端口中找到 DocType 不匹配转换
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
 此错误指示不为给定的 DocType 和 SendPort 找到匹配的转换。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请继续阅读，如下所示：  
  
1.  打开 BizTalk 管理控制台中，找到传输并右键单击传输名称。  
  
2.  单击 **“属性”**。  
  
3.  在端口类型列表中，选择正确的端口。 单击**配置**。  
  
4.  在 [端口名称] 发送端口属性对话框中，单击**出站映射**的左窗格中。  
  
5.  验证此处列出了映射以及它对应于正确的文档类型。