---
title: SMTP 适配器性能计数器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c7aa7dd-1674-4bbb-b22f-92204d55c4b8
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3503b5a37a7b2ab48be2478879cc61187895029
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973387"
---
# <a name="smtp-adapter-performance-counters"></a>SMTP 适配器性能计数器
使用性能计数器可以监视服务在站点或系统上执行的工作的特定方面。 性能计数器能够帮助您标识和解决有关服务器性能的问题。  
  
 以下性能计数器进行访问每个主机实例下**BizTalk:SMTP 发送适配器**性能对象类别：  
  
|**类别**|**计数器**|**Description**|  
|------------------|-----------------|---------------------|  
|BizTalk:SMTP Send Adapter|发送的消息|SMTP 适配器已发送的消息总数。 只有消息已传输到 SMTP 服务器时，该计数器的值才会增加。|  
||每秒发送的消息数|SMTP 适配器每秒发送的消息数。 计数器仅适用于已传送到 SMTP 服务器的消息。|  
  
## <a name="to-access-performance-counters"></a>访问性能计数器  
 依照下述步骤访问性能计数器。  
  
#### <a name="if-you-are-using-windows-2008"></a>如果您使用的是 Windows 2008  
  
1.  单击**启动**，指向**管理工具**，然后单击**性能监视器**。  
  
2.  在**性能监视器**对话框框中，展开**监视工具**，选择**性能监视器**，然后单击**添加**。  
  
3.  在**添加计数器**对话框中，从**可用计数器**列表中，展开**BizTalk:SMTP 发送适配器**性能计数器对象，然后选择要将的计数器监视  
  
4.  在**实例的所选对象**列表中，选择要监视的所选计数器，然后单击的特定实例**添加**。  若要选择的所有可用的计数器实例，选择\<**所有实例**\>。  
  
5.  添加计数器后, 单击**确定**。  
  
     所选的性能计数器显示在**性能监视器**屏幕。