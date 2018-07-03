---
title: 应用程序部署和管理工具 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de85b52b-7eb7-4cf1-b8b4-41f7488b4d2f
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 582090de6328ff999cb525e53881ebedb02b7a45
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993726"
---
# <a name="application-deployment-and-management-tools"></a>应用程序部署和管理工具

## <a name="overview"></a>概述
本主题简要介绍了可以用于部署和管理 BizTalk 应用程序的工具，并且概括了可以使用每种工具执行的操作。 本主题结尾处的表格总结了可以使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台和 BTSTask 执行的任务。  

- **BizTalk Server 管理控制台。** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，Microsoft 管理控制台 (MMC) 是主要管理工具[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 该控制台提供了一个图形化用户界面用于执行 BizTalk 应用程序的所有部署和管理操作。 例如，从管理控制台中，您可以启动导入向导、安装向导和导出向导，添加或删除应用程序项目，以及对应用程序进行其他修改。  

   也可以通过使用导出 MSI 文件向导或 BTSTask（参见下文）为 BizTalk 应用程序生成 BizTalk .msi 文件。 然后，可以通过 .msi 文件将应用程序安装到计算机或从 .msi 文件中将应用程序导入其他 BizTalk 组。 有关在管理控制台的详细信息，请参阅[使用 BizTalk Server 管理控制台](../core/using-the-biztalk-server-administration-console.md)。  

- **BTSTask 命令行工具。** BTSTask 允许您通过命令行执行许多应用程序管理任务。 有关使用 BTSTask 的详细信息，请参阅[BTSTask 命令行参考](../core/btstask-command-line-reference.md)。  

- **脚本和可编程 Api**。 使用 Microsoft Windows 管理规范 (WMI) 可以创建和运行自动执行许多应用程序管理任务的脚本。 有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  

- **Visual Studio。** 开发人员可以创建中的 BizTalk 程序集[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]和部署命令用于自动将其部署到 BizTalk 应用程序。 有关详细信息，请参阅[从到 BizTalk 应用程序的 Visual Studio 部署 BizTalk 程序集](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。  

   实例时都提供 SQL Server 登录名。  

  > [!IMPORTANT]
  >  切勿从在生产计算机上运行的 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中部署程序集。 这样可能会中断正在运行的应用程序。 有关详细信息，请参阅[部署 BizTalk 应用程序的最佳做法](../core/best-practices-for-deploying-a-biztalk-application.md)。  

## <a name="tool-by-the-task"></a>任务的工具  
 下表概括了可使用管理控制台和 BTSTask 执行的任务。  


|                                        任务                                         |                                                                                       工具                                                                                       |
|-------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                           导出应用程序 .msi 文件                           |           -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台 <br/>-导出 MSI 文件向导<br />-BTSTask           |
|                           导入应用程序 .msi 文件                           |             -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台 <br/>– 导入 MSI 向导<br />-BTSTask              |
|                           创建或删除应用程序                           |                          -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台<br />-BTSTask                          |
|                               安装应用程序                                | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台 <br/>– 安装向导 （或双击应用程序.msi 文件） |
|                              卸载应用程序                               |                                                              BTSTask（或使用“添加或删除程序”控制面板）                                                               |
|       向应用程序添加项目或从应用程序中删除项目       |                          -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台<br />-BTSTask                          |
|                    导入和导出绑定和绑定文件                     |                          -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台<br />-BTSTask                          |
|                             导入和导出策略                              |                          -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台<br />-BTSTask                          |
|                            启动和停止应用程序                            |                                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台                                     |
| 更改项目的状态： 启动、 停止、 启用、 禁用、 登记和取消登记 |                                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台                                     |
|                              编辑项目属性                               |                                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台                                     |
|       创建发送端口、发送端口组、接收位置或接收端口        |                                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台                                     |

## <a name="see-also"></a>请参阅  
[管理用户和性能工具](../core/administration-tools.md)  
 [了解 BizTalk 应用程序的部署和管理](../core/understanding-biztalk-application-deployment-and-management.md)