---
title: 创建 Oracle 数据库应用程序的先决条件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- strong-name key file, creating a
ms.assetid: 7a6b2e50-8153-468c-a25e-c15612792773
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5ed7056ad860af9f54a247a7014189fb3b45527
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979974"
---
# <a name="prerequisites-to-create-oracle-database-applications"></a>创建 Oracle 数据库应用程序的先决条件
在开发 BizTalk 应用程序使用之前必须做什么[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 部分还列出了一些 BizTalk Server 工具，用于开发 BizTalk 应用程序。  

## <a name="create-a-strong-named-key-file"></a>创建强名称密钥文件

必须创建一个强名称密钥文件，若要在 Microsoft 中生成项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。 强名称包含项目的标识，其简单文本名称、 版本号和区域性信息 （如果有的话）;加上公钥和数字签名。 强名称密钥文件包含公钥和私钥。  

> [!IMPORTANT]
>  创建强名称密钥文件是一次性任务。 为您开发的所有 BizTalk 应用程序，可以使用相同的密钥。  

### <a name="prerequisites"></a>必要條件  
 必须具有 Microsoft[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]想要创建一个强名称密钥的计算机上安装。  

### <a name="create-a-strong-name-key-file"></a>创建强名称密钥文件  

1.  打开 Visual Studio 开发人员命令提示。  

2.  在命令提示符处，导航到你想要创建的密钥文件的位置。 例如，键入`cd C:\Sample`，然后按 ENTER。  

3.  在命令提示符下，键入 `sn -k <key file name>.snk`，然后按 Enter。  

    > [!NOTE]
    >  应会收到一条消息表明密钥对已写入到强名称密钥文件的命令提示符处。  

4.  在命令提示符下，键入 `exit`，然后按 Enter。  

## <a name="learn-the-biztalk-server-tools"></a>了解 BizTalk Server 工具

有关如何使用主题[!INCLUDE[adapteroracle_short_md](../../includes/adapteroracle-short-md.md)]中[开发 BizTalk 应用程序与 Oracle 数据库的构建基块](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)编写时会假定您具有大量的工作知识的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]工具。 使用以下工具来开发 BizTalk 应用程序使用[!INCLUDE[adapteroracle_md](../../includes/adapteroracle-md.md)]:  

- Microsoft [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)] 

- BizTalk 浏览器  

- 业务流程 eesigner  

- 管道设计器  

- BizTalk 映射器  

- BizTalk Server 管理控制台  

### <a name="prerequisites"></a>必要條件  
 必须安装 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]可以访问之前[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]工具。  

### <a name="biztalk-server-tools"></a>BizTalk Server 工具  
 下表包含本节中的主题[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]说明了如何使用每个列出的工具的文档。  


|                                   工具                                    |                                                                                                                                                                                              本节中的主题[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]核心文档                                                                                                                                                                                               |
|---------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] | -   [使用 Visual Studio](../../core/using-visual-studio.md) <br />-   [使用 BizTalk 项目](../../core/working-with-biztalk-projects.md)<br />-   [部署 BizTalk 程序集从 Visual Studio 到 BizTalk 应用程序](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)<br /><br /> 了解更多有关 Visual Studio 解决方案、 项目和项在[解决方案和项目在 Visual Studio 中的](https://msdn.microsoft.com/library/b142f8e7.aspx)。 |
|                          业务流程设计器                           |                                                                                                                                                                                          [创建业务流程使用业务流程设计器](../../core/creating-orchestrations-using-orchestration-designer.md)                                                                                                                                                                                           |
|                             管道设计器                             |                                                                                                                                                                                                    [使用管道设计器创建管道](../../core/creating-pipelines-using-pipeline-designer.md)                                                                                                                                                                                                     |
|                              BizTalk 映射器                               |                                                                                                                                                                                                            [使用 BizTalk 映射器创建映射](../../core/creating-maps-using-biztalk-mapper.md)                                                                                                                                                                                                             |
|                   BizTalk Server 管理控制台                   |                                                                                                                                                                                               [使用 BizTalk Server 管理控制台](../../core/using-the-biztalk-server-administration-console.md)                                                                                                                                                                                                |

## <a name="next"></a>Next
[若要开发与 Oracle 数据库的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)