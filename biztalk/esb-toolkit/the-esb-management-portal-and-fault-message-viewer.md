---
title: ESB 管理门户和故障消息查看器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4a1636c-2e45-4ee5-92c2-81c976582da3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97b577e280eabece88a9d8196432fb013780c46c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399723"
---
# <a name="the-esb-management-portal-and-fault-message-viewer"></a>ESB 管理门户和故障消息查看器
一个主要组件[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]是基于 Web 的门户，提供范围广泛的异常管理和警报通知功能; 此外，它是作为一种有用的配置管理和通用描述、 发现和集成 （UDDI) 注册接口。 图 1 显示了当前正在运行的应用程序的运行状况概述了在门户的主页。  
  
 ![门户主页](../esb-toolkit/media/portalhomepage.gif "PortalHomePage")  
  
 **图 1**  
  
 **ESB 管理门户的主页页面**  
  
 用户可以选择在 ESB 管理门户中显示的错误消息以查看该错误的环境和静态属性和错误消息中包含的原始消息的列表，如图 2 中所示。  
  
 ![Faul tViewer 页](../esb-toolkit/media/ch4-faultviewerpage.gif "Ch4-FaultViewerPage")  
  
 **图 2**  
  
 **ESB 管理门户的 ESB 故障查看器页**  
  
 ESB 管理门户中显示的 ESB 错误消息可能时提交以供处理的原始消息的值中的错误的结果。 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]支持"修复并重新提交"功能，允许管理员或用户编辑失败的消息并将其提交到接入点进行处理。  
  
 选择一个包含的消息将打开消息视图页中消息的详细信息视图中，如图 3 中所示。 在此视图中，用户可以看到消息内容，请下载该消息，或单击**编辑**切换到编辑视图，它们可以在其中修复并重新提交消息。  
  
 ![消息查看器页面](../esb-toolkit/media/ch4-messageviewerpage.gif "Ch4-MessageViewerPage")  
  
 **图 3**  
  
 **显示错误的详细信息视图的 ESB 消息查看器**  
  
 有关完整说明和 ESB 管理门户中，包括故障查看器，该消息重新提交过程中和有关列表，使用的技术的使用情况选项排序和分析错误，请参阅[使用 BizTalk ESB 管理工具包](../esb-toolkit/administration-with-the-biztalk-esb-toolkit.md)。