---
title: SOAP 适配器性能计数器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 40b54d4e-0a2e-483f-982a-97ab9fb59202
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d5f13708fc59c02a9a74b652508aa74cf1a36f00
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65314046"
---
# <a name="soap-adapter-performance-counters"></a>SOAP 适配器性能计数器
性能计数器允许你监视的工作上的站点或系统服务执行的特定方面。 性能计数器可以帮助您确定和解决服务器性能问题。  
  
 以下性能计数器都可以访问每个主机实例下**biztalk: Soap Receive Adapter**并**biztalk: Soap Send Adapter**性能对象类别：  
  
|**类别**|**计数器**|**说明**|  
|------------------|-----------------|---------------------|  
|Biztalk: Soap 接收适配器|接收的消息|接收适配器接收的 SOAP 消息的总数。 此计数器递增后请求消息完全读取的适配器从 SOAP 客户端。|  
||收到的消息数/秒|适配器每秒接收的 soap 接收的消息数。 计数器仅应用于已完全读取的适配器从 SOAP 客户端的请求消息。|  
|BizTalk:SOAP Send Adapter|发送的消息|发送适配器发送的 SOAP 消息的总数。 仅对已到达目标 URL 的消息是增加计数器的数值。|  
||发送的消息数/秒|适配器每秒发送的 soap 发送的消息数。 计数器仅应用于已到达目标 URL 的消息。|  
  
## <a name="to-access-performance-counters"></a>若要访问性能计数器  
 使用以下步骤访问性能计数器。  
  
#### <a name="if-you-are-using-windows-server-2008"></a>如果使用 Windows Server 2008  
  
1.  单击**启动**，依次指向**管理工具**，然后单击**性能监视器**。  
  
2.  在中**性能监视器**对话框框中，展开**监视工具**，选择**性能监视器**，然后单击**添加**。  
  
3.  在中**添加计数器**对话框中，从**可用的计数器**列表中，展开**biztalk: Soap**性能计数器对象，然后选择要监视的计数器  
  
4.  在中**选定对象的实例**列表中，选择要监视的所选的计数器，然后单击的特定实例**添加**。 若要选择的所有可用的计数器实例，请选择\<**所有实例**\>。  
  
5.  添加计数器之后, 单击**确定**。  
  
     所选的性能计数器随即显示在**性能监视器**屏幕。