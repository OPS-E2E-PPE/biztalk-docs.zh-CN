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
ms.openlocfilehash: 2a224625122fa498410dc9aed9036fe875e4b739
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346320"
---
# <a name="there-are-no-batch-elements-to-send-and-an-empty-message-cannot-be-sent-as-it-is-not-configured-for-party"></a>没有要发送的批处理元素并且无法发送空消息，因为它未配置为参与方
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
 此警告意味着任何批处理消息被基于计划的批处理过程中发送，因为当计划批处理发布，并不启用了空的批处理信号已不收到任何批处理元素。  
  
## <a name="user-action"></a>用户操作  
 要阻止发布此警告，请执行以下操作配置空的批处理信号：  
  
1.  打开 BizTalk Server 管理控制台。  
  
2.  将移动到参与方节点。  
  
3.  打开的参与方 EDI 属性对话框。  
  
4.  单击交换批处理创建设置节点 （适用于相应的编码）。  
  
5.  单击计划程序。  
  
6.  单击发送空的批处理信号属性。