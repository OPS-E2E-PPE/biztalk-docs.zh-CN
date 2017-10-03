---
title: "要创建 Siebel 应用程序系统必备组件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2c08f853-7f72-4e08-aa63-debdab68c972
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eeea15b7a05eb50b498c4c177c987f5c5c736a85
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="prerequisites-to-create-siebel-applications"></a>创建 Siebel 应用程序的先决条件
在开发使用的 BizTalk 应用程序之前必须执行什么[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。 此主题还列出一些用于开发 BizTalk 应用程序的 BizTalk Server 工具。  
  
## <a name="create-a-strong-named-key-file"></a>创建具有强名称密钥文件

你必须创建一个强名称密钥文件，以生成在 Microsoft 中的项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。 强名称的项目的标识组成 — 其简单文本名称、 版本号和区域性信息 （如果有的话）;加上一个公钥和数字签名。 强名称密钥文件包含公钥和私钥。  
  
> [!IMPORTANT]
>  创建强名称密钥文件是一次性的任务。 相同的密钥可用于开发的所有 BizTalk 应用程序。  
  
### <a name="prerequisites"></a>先决条件  
 你必须具有 Microsoft[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]你想要创建强名称密钥在计算机上安装。  
  
### <a name="create-a-strong-name-key-file"></a>创建强名称密钥文件  
  
1.  打开 Visual Studio 开发人员命令提示。  
  
2.  在命令提示符处，导航到你想要创建的密钥文件的位置。 例如，键入`cd C:\Sample`，然后按 ENTER。  
  
3.  在命令提示符下，键入 `sn -k <key file name>.snk`，然后按 Enter。  
  
    > [!NOTE]
    >  你应该会收到一条消息，指出的密钥对已写入到强名称密钥文件的命令提示符处。  
  
4.  在命令提示符下，键入 `exit`，然后按 Enter。  
  
## <a name="learn-the-biztalk-server-tools"></a>了解 BizTalk Server 工具

有关如何使用主题[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]中[使用 Siebel 适配器创建 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)通过假设你有大量的工作知识编写[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]工具。 使用以下工具来开发 BizTalk 应用程序使用[!INCLUDE[adaptersiebel_md](../../includes/adaptersiebel-md.md)]:  
  
-   Microsoft [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)] 
  
-   BizTalk 浏览器  
  
-   业务流程 eesigner  
  
-   管道设计器  
  
-   BizTalk 映射程序  
  
-   BizTalk Server 管理控制台  
  
### <a name="prerequisites"></a>先决条件  
 你必须安装 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]可以访问之前[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]工具。  
  
### <a name="biztalk-server-tools"></a>BizTalk Server 工具  
 下表包含中的主题[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]说明如何使用每个列出的工具的文档。  
  
|工具|中的主题[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]核心文档|  
|---|---|  
|[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]|-   [使用 Visual Studio](../../core/using-visual-studio.md) <br />-   [使用 BizTalk 项目](../../core/working-with-biztalk-projects.md)<br />-   [部署到 BizTalk 应用程序从 Visual Studio BizTalk 程序集](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)<br /><br /> 了解更多有关 Visual Studio 解决方案、 项目和项在[解决方案和 Visual Studio 中的项目](https://msdn.microsoft.com/library/b142f8e7.aspx)。|  
|业务流程设计器|[创建使用业务流程设计器的业务流程](../../core/creating-orchestrations-using-orchestration-designer.md)|  
|管道设计器| [创建管道使用管道设计器](../../core/creating-pipelines-using-pipeline-designer.md)|  
|BizTalk 映射程序| [创建使用 BizTalk 映射程序图](../../core/creating-maps-using-biztalk-mapper.md)|  
|BizTalk Server 管理控制台|[使用 BizTalk Server 管理控制台](../../core/using-the-biztalk-server-administration-console.md)|  
  
## <a name="next"></a>Next
[构建基块创建带有 Siebel 适配器 BizTalk 应用程序](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)