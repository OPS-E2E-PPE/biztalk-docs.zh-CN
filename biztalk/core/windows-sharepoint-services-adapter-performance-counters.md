---
title: Windows SharePoint Services 适配器性能计数器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41583fde-530a-4070-9647-f1ab6273aadf
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1346bc558bd9881d9eb925856f79277a831c2665
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65240362"
---
# <a name="windows-sharepoint-services-adapter-performance-counters"></a>Windows SharePoint Services 适配器性能计数器
性能计数器允许你监视的工作上的站点或系统服务执行的特定方面。 性能计数器可以帮助您确定和解决服务器性能问题。  
  
 以下性能计数器都可以访问每个主机实例下**biztalk: Windows Sharepoint Services 适配器**性能对象类别：  
  
|**类别**|**计数器**|**说明**|  
|------------------|-----------------|---------------------|  
|Biztalk: Windows Sharepoint Services 适配器|%接收消息失败|未处理的 BizTalk Server 由于接收错误的 Windows SharePoint Services 文件的百分比。|  
||%发送消息失败|BizTalk Server 尝试发往 Windows SharePoint Services 的失败消息的百分比。|  
||%Web 服务调用失败|Windows SharePoint Services 适配器 Web services 调用失败的百分比。|  
||Total receive 接收提交失败|更新的 SharePoint 文档状态时出现的 Windows SharePoint Services 错误的总数。|  
||Total receive 接收消息失败|收到尚未处理由 BizTalk Server 由于错误而导致的 Windows SharePoint Services 文件总数。|  
||收到的消息总数|接收的 Windows SharePoint Services 适配器，包括无法处理的文件的 Windows SharePoint Services 文件的总数。|  
||总发送消息失败|BizTalk Server 尝试发往 Windows SharePoint Services 的失败消息的总数。|  
||发送的消息总计|BizTalk Server 发送到 Windows SharePoint Services，包括无法处理的文件的消息的总数。|  
||全面的 Web 服务调用失败|Windows SharePoint Services 适配器 Web services 调用失败的总数。|  
||每秒的 web 服务调用|每秒调用 Windows SharePoint Services 适配器 Web 服务数。|  
  
## <a name="to-access-performance-counters"></a>若要访问性能计数器  
 使用以下步骤访问性能计数器。  
  
#### <a name="if-you-are-using-windows-2008"></a>如果您使用的 Windows 2008  
  
1.  单击**启动**，依次指向**管理工具**，然后单击**性能监视器**。  
  
2.  在中**性能监视器**对话框框中，展开**监视工具**，选择**性能监视器**，然后单击**添加**。  
  
3.  在中**添加计数器**对话框中，从**可用的计数器**列表中，展开**biztalk: Windows Sharepoint Services 适配器**性能计数器对象，并选择要监视的计数器  
  
4.  在中**选定对象的实例**列表中，选择要监视的所选的计数器，然后单击的特定实例**添加**。  若要选择的所有可用的计数器实例，请选择\<**所有实例**\>。  
  
5.  添加计数器之后, 单击**确定**。  
  
     所选的性能计数器随即显示在**性能监视器**屏幕。