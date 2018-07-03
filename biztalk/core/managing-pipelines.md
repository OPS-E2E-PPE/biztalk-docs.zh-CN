---
title: 管理管道 |Microsoft Docs
description: 若要启用跟踪和管道属性在发送端口或接收位置在 BizTalk Server 中的快速链接
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d60b54e0-0a5a-4264-b0e5-96bb187d782b
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b15931468b5ba3bf43f227563dd270aabbfa29b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995254"
---
# <a name="managing-pipelines"></a>管理管道

## <a name="overview"></a>概述
本部分说明如何使用 BizTalk Server 管理控制台来管理 BizTalk 组中的管道。 您既可为事件和消息配置跟踪，也可为特定发送端口或接收位置配置管道属性。  
  
 管道对传入消息和传出消息执行操作，例如将其从本机格式转换为 XML 格式、加密或解密数据、执行属性升级等等。  
  
 不能向应用程序单独添加管道，而应按照以下方式向应用程序添加管道：  
  
- 当添加包含到应用程序中，管道的 BizTalk 程序集，如中所述[如何将 BizTalk 程序集添加到应用程序](../core/how-to-add-a-biztalk-assembly-to-an-application.md)。  
  
- 某一.msi 文件导入包含包含管道的 BizTalk 程序集，如中所述的应用程序[导入 BizTalk 应用程序的方式](../core/how-to-import-a-biztalk-application.md)。  
  
- 当开发人员部署到应用程序的程序集包含在 Visual Studio 中，管道中所述[从到 BizTalk 应用程序的 Visual Studio 部署 BizTalk 程序集](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。  
  
  有关管道的背景信息，请参阅[管道](../core/pipelines.md)。 有关开发管道的信息，请参阅[管道使用管道设计器创建](../core/creating-pipelines-using-pipeline-designer.md)。  
  
> [!NOTE]
>  Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。 有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="next-steps"></a>后续步骤
  
-   [为管道配置跟踪](../core/how-to-configure-tracking-for-a-pipeline.md)  
  
-   [为发送端口配置基于实例的管道属性](../core/how-to-configure-per-instance-pipeline-properties-for-a-send-port.md)  
  
-   [为接收位置配置基于实例的管道属性](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md)