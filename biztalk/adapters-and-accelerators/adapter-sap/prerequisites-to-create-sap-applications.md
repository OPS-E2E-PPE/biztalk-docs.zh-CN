---
title: 创建 SAP 应用程序的先决条件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51ae9569-4081-4142-9ee2-8ae0069e9d90
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72225a059d5b655555f46f06758df11de3eaa8e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978566"
---
# <a name="prerequisites-to-create-sap-applications"></a>创建 SAP 应用程序的先决条件
本部分提供有关在开发 BizTalk 应用程序使用之前必须执行的任务的信息[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 部分还列出了一些 BizTalk Server 工具，用于开发 BizTalk 应用程序。  

## <a name="create-a-strong-name-key-file"></a>创建强名称密钥文件

必须创建一个强名称密钥文件，若要在 Microsoft 中生成项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。 强名称包含项目的标识，其简单文本名称、 版本号和区域性信息 （如果提供），加上公钥和数字签名。 强名称密钥文件包含公钥和私钥。  

> [!IMPORTANT]
>  创建强名称密钥文件是一次性任务。 为您开发的所有 BizTalk 应用程序，可以使用相同的密钥。  

1.  打开 Visual Studio 开发人员命令提示。  

2.  在命令提示符处导航到你想要创建的密钥文件的位置。 例如，键入**cd C:\Sample**，然后按 ENTER。  

3.  在命令提示符下，键入 `sn -k <key file name\>.snk`，然后按 Enter。  

    > [!NOTE]
    >  应会收到一条消息表明密钥对已写入到强名称密钥文件的命令提示符处。  

4.  在命令提示符处，键入**退出**，然后按 ENTER。  

## <a name="learn-the-biztalk-server-tools"></a>了解 BizTalk Server 工具

有关如何使用主题[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]中[开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)假定你有多个 BizTalk Server 工具的实践知识。 将使用以下工具来开发 BizTalk 应用程序使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]:  

- Microsoft [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)] 

- 业务流程 eesigner  

- 管道设计器  

- BizTalk 映射器  

- [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 管理控制台  


### <a name="prerequisites"></a>必要條件  
 必须安装[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]可以访问之前[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]工具。  

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
[生成块以创建 SAP 应用程序](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)