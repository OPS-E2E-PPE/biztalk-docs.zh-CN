---
title: "管理管道 |Microsoft 文档"
description: "若要启用跟踪和发送端口上的管道属性或在 BizTalk Server 接收位置的快速链接"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d60b54e0-0a5a-4264-b0e5-96bb187d782b
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0edfbdd97e134abc6f153acf136ff62a979f8b0c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="managing-pipelines"></a>管理管道

## <a name="overview"></a>概述
本部分说明如何使用 BizTalk Server 管理控制台来管理 BizTalk 组中的管道。 您既可为事件和消息配置跟踪，也可为特定发送端口或接收位置配置管道属性。  
  
 管道对传入消息和传出消息执行操作，例如将其从本机格式转换为 XML 格式、加密或解密数据、执行属性升级等等。  
  
 不能向应用程序单独添加管道，而应按照以下方式向应用程序添加管道：  
  
-   当你添加 BizTalk 程序集包含应用程序，管道中所述[如何将 BizTalk 程序集添加到应用程序](../core/how-to-add-a-biztalk-assembly-to-an-application.md)。  
  
-   当你导入的应用程序中所述包括 BizTalk 程序集包含管道，.msi 文件[如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)。  
  
-   当开发人员将部署到应用程序包含从 Visual Studio 中，管道的程序集中所述[部署 BizTalk 中的程序集到 BizTalk 应用程序的 Visual Studio](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。  
  
 有关管道的背景信息，请参阅[管道](../core/pipelines.md)。 有关开发管道的信息，请参阅[创建管道使用管道设计器](../core/creating-pipelines-using-pipeline-designer.md)。  
  
> [!NOTE]
>  Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。 有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="next-steps"></a>后续步骤
  
-   [配置为管道的跟踪](../core/how-to-configure-tracking-for-a-pipeline.md)  
  
-   [配置每个实例管道发送端口属性](../core/how-to-configure-per-instance-pipeline-properties-for-a-send-port.md)  
  
-   [配置每个实例的管道属性接收位置](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md)