---
title: 没有要发送的批处理元素并且无法发送空消息，因为它未配置为参与方 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0752079a-173e-4de3-96f4-e5de01b799b5
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73d0d44c8a5a206748eb128cd2461d1d04b54c93
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976662"
---
# <a name="there-are-no-batch-elements-to-send-and-an-empty-message-cannot-be-sent-as-it-is-not-configured-for-party"></a>There are no batch elements to send and an empty message cannot be sent as it is not configured for party
## <a name="details"></a>详细信息  
  
|                 |                                                                                                               |
|-----------------|---------------------------------------------------------------------------------------------------------------|
|  产品名称   |              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]               |
| 产品版本 |                          [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                           |
|    事件 ID     |                                                       -                                                       |
|  事件源   |            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI             |
|    组件    |                                                批处理引擎                                                |
|  符号名称  |                                            EmptyMessageNotAllowed                                             |
|  消息正文   | 没有要发送的批处理元素并且无法发送空消息，因为它未配置为参与方 {0} |
  
## <a name="explanation"></a>解释  
 此警告表明在基于计划的批处理过程中没有发送批处理消息，因为当计划批处理发布时未收到任何批处理元素，并且尚未启用空的批处理信号。  
  
## <a name="user-action"></a>用户操作  
 若要阻止发布此警告，请通过执行以下操作配置空的批处理信号：  
  
1.  打开 BizTalk Server 管理控制台。  
  
2.  移动到“参与方”节点。  
  
3.  打开该参与方的“EDI 属性”对话框。  
  
4.  单击“交换批处理创建设置”节点（对于相应的编码）。  
  
5.  单击“计划程序”。  
  
6.  单击“发送空的批处理信号”属性。