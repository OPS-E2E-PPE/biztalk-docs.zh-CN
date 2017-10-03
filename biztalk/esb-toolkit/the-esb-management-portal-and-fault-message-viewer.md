---
title: "ESB 管理门户和错误消息查看器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c4a1636c-2e45-4ee5-92c2-81c976582da3
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb9a6e7272e7b707b6ba7650cfb93506c3a54a00
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-esb-management-portal-and-fault-message-viewer"></a>ESB 管理门户和错误消息查看器
一个主要组件[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]是基于 Web 的门户，提供了各种各样的异常管理和警报通知功能; 此外，它作为有用的配置管理和通用、 描述、 发现和集成 （UDDI) 注册接口。 图 1 显示一个门户，它概述了运行状况当前正在运行的应用程序的主页。  
  
 ![门户主页上](../esb-toolkit/media/portalhomepage.gif "PortalHomePage")  
  
 **图 1**  
  
 **ESB 管理门户的主页页面**  
  
 用户可以选择在 ESB 管理门户中显示的错误消息以查看错误的环境和静态属性和错误消息中包含的原始消息的列表，如图 2 中所示。  
  
 ![Faul tViewer 页](../esb-toolkit/media/ch4-faultviewerpage.gif "第四章第 4 FaultViewerPage")  
  
 **图 2**  
  
 **ESB 管理门户的 ESB 错误查看器页上**  
  
 ESB 管理门户中显示的 ESB 错误消息可能时提交以供处理的原始消息的值中的错误的结果。 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]支持"修复并重新提交"功能，这将允许管理员或用户编辑失败的消息以及将其提交至入口进行处理。  
  
 选择其中一个包含的消息打开消息视图页在消息详细信息视图中，如图 3 中所示。 在此视图中，用户可以看到的消息内容，下载消息，或单击**编辑**切换到编辑视图，它们可以在位置修复并重新提交消息。  
  
 ![消息查看器页面](../esb-toolkit/media/ch4-messageviewerpage.gif "第四章第 4 MessageViewerPage")  
  
 **图 3**  
  
 **显示的错误详细信息视图的 ESB 消息查看器**  
  
 有关完整说明和 ESB 管理门户中，包括错误查看器、 消息重新提交过程中和有关列表，采用的技术的使用情况选项排序和分析错误，请参阅[借助 BizTalk ESB 管理工具包](../esb-toolkit/administration-with-the-biztalk-esb-toolkit.md)。