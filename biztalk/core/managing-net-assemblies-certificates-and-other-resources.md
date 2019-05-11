---
title: 管理.NET 程序集、 证书和其他资源 |Microsoft Docs
description: 若要添加绑定文件、 证书、 程序集、 虚拟目录、 文件和 BizTalk Server 中的详细信息的链接
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: efe27a11-19d8-4eb3-9f8c-f4336e4c3d66
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9052b9a5bdee58e9d4cb3d51820905b492818fc3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65326595"
---
# <a name="manage-net-assemblies-certificates-and-other-resources"></a>管理.NET 程序集、 证书和其他资源

## <a name="overview"></a>概述
本部分说明了使用 BizTalk Server 管理控制台和 BTSTask 命令行工具来管理以下类型的 BizTalk 应用程序的资源项目。 这些资源项目无法自动部署到 BizTalk 应用程序从 Visual Studio 中，因此必须手动向应用程序中添加。 添加到应用程序后，但是，您可以导入、 导出和安装它们作为一个单元与应用程序的其他项目。  
  
-   **文件。** 可以包括特别文件，如自述文件。 在安装应用程序时，文件复制到安装文件夹。  
  
-   **证书。** 可以向应用程序添加证书文件，以便可以传输到另一个，与应用程序打包在一起的证书从一个 BizTalk 组。 分配证书，以发送端口和接收位置来验证凭据，并建立安全链接。  
  
-   **COM 和 COM + 组件。** 可以包含托管的 COM 和托管的 COM + 组件以提供 BizTalk 应用程序中的其他功能。  
  
-   **.NET 程序集。** 可以包括不专门 BizTalk 程序集的 BizTalk 应用程序中的.NET 程序集。 （BizTalk 程序集是包含 BizTalk 业务流程、 管道、 架构或映射的.NET 程序集。）  
  
-   **BAM 定义文件。** 若要使 BAM 部署更容易，可以创建 BizTalk 应用程序并向其添加 BAM 定义。 然后可以使用 BizTalk 应用程序部署功能部署到不同的环境的 BAM 定义。  
  
-   **绑定文件。** 可以将绑定文件添加到应用程序以使在不同部署环境之间移动应用程序更快、 更轻松。  
  
-   **虚拟目录。** 可以向应用程序添加虚拟目录，以便它们将与应用程序部署。  
  
> [!NOTE]
>  Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。 有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="next-steps"></a>后续步骤
  
-   [向应用程序添加文件](../core/how-to-add-a-file-to-an-application.md)  
  
-   [向应用程序添加证书](../core/how-to-add-a-certificate-to-an-application.md)  
  
-   [向应用程序添加 COM 组件](../core/how-to-add-a-com-component-to-an-application.md)  
  
-   [向应用程序添加 .NET 程序集](../core/how-to-add-a-net-assembly-to-an-application.md)  
  
-   [向应用程序添加 BAM 项目](../core/how-to-add-a-bam-artifact-to-an-application.md)  
  
-   [向应用程序添加绑定文件](../core/how-to-add-a-binding-file-to-an-application2.md)  
  
-   [向应用程序添加虚拟目录](../core/how-to-add-a-virtual-directory-to-an-application.md)  
  
-   [修改.NET 程序集、 COM 组件、 文件或 BAM 项目的部署选项](../core/modify-deployment-options-of-net-assembly-com-component-file-bam-artifact.md)  
  
-   [从应用程序中删除 .NET 程序集、证书或其他资源项目](../core/remove-a-net-assembly-certificate-or-resource-artifact-from-an-application.md)