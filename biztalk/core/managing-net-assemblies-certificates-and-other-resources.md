---
title: "管理.NET 程序集、 证书和其他资源 |Microsoft 文档"
description: "若要添加绑定文件、 证书、 程序集、 虚拟目录、 文件和 BizTalk Server 中的详细信息的链接"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: efe27a11-19d8-4eb3-9f8c-f4336e4c3d66
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fdb74762bdf08e6e9e2a79650a26dedb0915ea8f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="manage-net-assemblies-certificates-and-other-resources"></a>管理.NET 程序集、 证书和其他资源

## <a name="overview"></a>概述
本部分介绍如何使用 BizTalk Server 管理控制台或 BTSTask 命令行工具管理 BizTalk 应用程序的以下几类资源项目。 由于无法通过 Visual Studio 将这些资源项目自动部署到 BizTalk 应用程序中，因而必须手动将它们添加至应用程序。 但是，将它们添加至某个应用程序后，即可将它们作为一个单元随同此应用程序和此应用程序的其他项目一起导入、导出和安装。  
  
-   **文件。** 可以包括特别文件，如自述文件。 在安装应用程序时，将把文件复制到安装文件夹中。  
  
-   **证书。** 可以向应用程序添加证书文件，以便可以将证书与应用程序打包在一起从一个 BizTalk 组传输到另一个组。 可将证书指定给发送端口和接收位置来验证标识和建立安全链接。  
  
-   **COM 和 COM + 组件。** 可以将托管 COM 和托管 COM+ 组件包括在 BizTalk 程序中，以提供其他功能。  
  
-   **.NET 程序集。** 可以将不是特殊 BizTalk 程序集的 .NET 程序集包括在 BizTalk 应用程序中。 （BizTalk 程序集是包含 BizTalk 业务流程、管道、架构和映射的 .NET 程序集。）  
  
-   **BAM 定义文件。** 为使 BAM 部署更为方便，可以创建 BizTalk 应用程序，然后向其添加 BAM 定义。 然后可以使用此 BizTalk 应用程序的部署功能将 BAM 定义部署到不同的环境中。  
  
-   **绑定文件。** 可以将绑定文件添加至应用程序，以使应用程序从一个部署环境到另一个部署环境的移动更加快捷方便。  
  
-   **虚拟目录。** 可以将虚拟目录添加至应用程序，以便将它们和应用程序一起部署。  
  
> [!NOTE]
>  Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。 有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="next-steps"></a>后续步骤
  
-   [将文件添加到应用程序](../core/how-to-add-a-file-to-an-application.md)  
  
-   [将证书添加到应用程序](../core/how-to-add-a-certificate-to-an-application.md)  
  
-   [将 COM 组件添加到应用程序](../core/how-to-add-a-com-component-to-an-application.md)  
  
-   [将.NET 程序集添加到应用程序](../core/how-to-add-a-net-assembly-to-an-application.md)  
  
-   [将一个 BAM 项目添加到应用程序](../core/how-to-add-a-bam-artifact-to-an-application.md)  
  
-   [将绑定文件添加到应用程序](../core/how-to-add-a-binding-file-to-an-application2.md)  
  
-   [将虚拟目录添加到应用程序](../core/how-to-add-a-virtual-directory-to-an-application.md)  
  
-   [修改.NET 程序集、 COM 组件、 文件或 BAM 项目的部署选项](../core/modify-deployment-options-of-net-assembly-com-component-file-bam-artifact.md)  
  
-   [删除从应用程序的.NET 程序集、 证书或其他资源项目](../core/remove-a-net-assembly-certificate-or-resource-artifact-from-an-application.md)