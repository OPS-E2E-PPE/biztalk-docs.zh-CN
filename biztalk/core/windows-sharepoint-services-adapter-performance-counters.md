---
title: "Windows SharePoint Services 适配器性能计数器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 41583fde-530a-4070-9647-f1ab6273aadf
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1af70299f5e308d1fc40fa6206f0ebfabff22a06
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="windows-sharepoint-services-adapter-performance-counters"></a>Windows SharePoint Services 适配器性能计数器
使用性能计数器可以监视服务在站点或系统上执行的工作的特定方面。 性能计数器能够帮助您标识和解决有关服务器性能的问题。  
  
 以下性能计数器进行访问每个主机实例下**biztalk: Windows Sharepoint Services Adapter**性能对象类别：  
  
|**类别**|**计数器**|**Description**|  
|------------------|-----------------|---------------------|  
|BizTalk:Windows SharePoint Services Adapter|% Receive Message Failures|由于接收错误而未经 BizTalk Server 处理的 Windows SharePoint Services 文件的百分比。|  
||% Send Message Failures|BizTalk Server 尝试发往 Windows SharePoint Services 的失败消息的百分比。|  
||% Web Service Call Failures|Windows SharePoint Services 适配器 Web Services 调用失败的百分比。|  
||Total Receive Commit Failures|更新 SharePoint 文档状态时引发的 Windows SharePoint Services 错误的总数。|  
||Total Receive Message Failures|由于错误而未经 BizTalk Server 处理的已接收 Windows SharePoint Services 文件的总数。|  
||Total Received Messages|Windows SharePoint Services 适配器接收的 Windows SharePoint Services 文件的总数，其中包括无法处理的文件。|  
||Total Send Message Failures|BizTalk Server 尝试发往 Windows SharePoint Services 的失败消息的总数。|  
||Total Sent Messages|BizTalk Server 发往 Windows SharePoint Services 的消息总数，其中包括无法处理的文件。|  
||Total Web Service Call Failures|Windows SharePoint Services 适配器 Web Services 调用失败的总数。|  
||Web Service Calls per Second|Windows SharePoint Services 适配器 Web Services 的每秒调用数。|  
  
## <a name="to-access-performance-counters"></a>访问性能计数器  
 依照下述步骤访问性能计数器。  
  
#### <a name="if-you-are-using-windows-2008"></a>如果您使用的是 Windows 2008  
  
1.  单击**启动**，指向**管理工具**，然后单击**性能监视器**。  
  
2.  在**性能监视器**对话框框中，展开**监视工具**，选择**性能监视器**，然后单击**添加**。  
  
3.  在**添加计数器**对话框中，从**可用计数器**列表中，展开**biztalk: Windows Sharepoint Services Adapter**性能计数器对象，并选择要监视的计数器  
  
4.  在**实例的所选对象**列表中，选择要监视的所选计数器，然后单击的特定实例**添加**。  若要选择的所有可用的计数器实例，选择\<**所有实例**\>。  
  
5.  添加计数器后, 单击**确定**。  
  
     所选的性能计数器显示在**性能监视器**屏幕。