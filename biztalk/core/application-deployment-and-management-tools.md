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
ms.openlocfilehash: 89d0d1881eeb8d5480afea46747ecc17e425de38
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359085"
---
# <a name="application-deployment-and-management-tools"></a>应用程序部署和管理工具

## <a name="overview"></a>概述
本主题简要介绍了可用于部署和管理 BizTalk 应用程序的工具，并概括了可以使用每种工具执行的操作。 本主题末尾处的表格总结了可以使用执行的任务[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台和 BTSTask。  

- **BizTalk Server 管理控制台。** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，Microsoft 管理控制台 (MMC) 是主要管理工具[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 它提供用于执行的所有 BizTalk 应用程序部署和管理操作的图形用户界面。 例如，从管理控制台中，可以将启动导入、 安装和导出向导，以及添加和删除应用程序的项目并对应用程序进行其他修改。  

   你还生成 BizTalk.msi 文件的 BizTalk 应用程序通过使用导出 MSI 文件向导或 BTSTask 下, 一步所述。 然后可以根据该.msi 文件的计算机上安装应用程序或应用程序从.msi 文件导入到其他 BizTalk 组。 有关在管理控制台的详细信息，请参阅[使用 BizTalk Server 管理控制台](../core/using-the-biztalk-server-administration-console.md)。  

- **BTSTask 命令行工具。** BTSTask 允许您从命令行执行许多应用程序管理任务。 有关使用 BTSTask 的详细信息，请参阅[BTSTask 命令行参考](../core/btstask-command-line-reference.md)。  

- **脚本和可编程 Api**。 可以使用 Microsoft Windows Management Instrumentation (WMI) 来创建和运行自动执行许多应用程序管理任务的脚本。 有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  

- **Visual Studio.** 开发人员可以创建中的 BizTalk 程序集[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]和部署命令用于自动将其部署到 BizTalk 应用程序。 有关详细信息，请参阅[从到 BizTalk 应用程序的 Visual Studio 部署 BizTalk 程序集](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。  

   .  

  > [!IMPORTANT]
  >  绝不应该将部署中的程序集[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]生产计算机上运行。 这可能会中断正在运行的应用程序。 有关详细信息，请参阅[部署 BizTalk 应用程序的最佳做法](../core/best-practices-for-deploying-a-biztalk-application.md)。  

## <a name="tool-by-the-task"></a>任务的工具  
 下表总结了可以使用管理控制台和 BTSTask 执行的任务。  


|                                        任务                                         |                                                                                       Tool                                                                                       |
|-------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                           导出应用程序.msi 文件                           |           -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台 <br/>-导出 MSI 文件向导<br />-   BTSTask           |
|                           应用程序.msi 文件导入                           |             -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台 <br/>– 导入 MSI 向导<br />-   BTSTask              |
|                           创建或删除应用程序                           |                          -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台<br />-   BTSTask                          |
|                               安装应用程序                                | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台 <br/>– 安装向导 （或双击应用程序.msi 文件） |
|                              卸载应用程序                               |                                                              BTSTask （或使用添加或删除程序控制面板）                                                               |
|       将项目添加到应用程序或从应用程序中删除项目       |                          -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台<br />-   BTSTask                          |
|                    导入和导出绑定和绑定文件                     |                          -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台<br />-   BTSTask                          |
|                             导入和导出策略                              |                          -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台<br />-   BTSTask                          |
|                            启动和停止应用程序                            |                                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台                                     |
| 更改项目的状态： 启动、 停止、 启用、 禁用、 登记和取消登记 |                                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台                                     |
|                              编辑项目属性                               |                                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台                                     |
|       创建发送端口、 发送端口组、 接收位置，或接收端口        |                                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台                                     |

## <a name="see-also"></a>请参阅  
[管理用户和性能工具](../core/administration-tools.md)  
 [了解 BizTalk 应用程序的部署和管理](../core/understanding-biztalk-application-deployment-and-management.md)