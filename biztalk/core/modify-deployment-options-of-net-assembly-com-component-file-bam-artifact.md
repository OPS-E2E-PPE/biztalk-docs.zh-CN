---
title: 如何修改.NET 程序集、 COM 组件、 文件或 BAM 项目的部署选项 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [.NET assemblies], deploying
- deploying, virtual directories
- managing [applications], deploying
- managing [applications], modifying
- definition files [BAM], modifying
- modifying, artifacts
- deploying, artifacts
- managing [certificates], deploying
- deploying, .NET assemblies
- COM components, deploying
- definition files [BAM], deploying
- virtual directories, deploying
- deploying, certificates
- modifying, deployment options
- virtual directories, modifying
- deploying, COM components
ms.assetid: 4955d420-d9ff-4d5a-82f4-fb16477a828c
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6469f06b7b42ae1f8b45419fa0214682bd9fa67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263973"
---
# <a name="how-to-modify-the-deployment-options-of-a-net-assembly-com-component-file-or-bam-artifact"></a>如何修改.NET 程序集、 COM 组件、 文件或 BAM 项目的部署选项
本主题将介绍如何使用 BizTalk Server 管理控制台修改以下资源项目的部署选项：  
  
-   .NET 程序集  
  
-   COM 组件  
  
-   特别文件  
  
-   BAM 项目  
  
 您可能要修改部署属性，以便更改在本地计算机上安装应用程序时项目文件将复制到的目标位置。 如果未提供路径，则在安装时该文件将不会复制到本地计算机。  
  
 此外，您可能要修改 .NET 程序集的以下选项：  
  
-   **将添加到全局程序集缓存在添加资源 (gacutil)。** 如果选择此选项，则在将程序集添加到应用程序时，该程序集将添加到本地计算机上的全局程序集缓存 (GAC) 中。 此外，如果你更高版本刷新程序集 (右键单击它，然后单击**刷新**)，此程序集添加到 GAC。 清除此选项的复选框并不从 GAC 删除该程序集（如果该程序集当前在 GAC 中存在）。  
  
-   **将添加到 MSI 文件导入 (gacutil) 上的全局程序集缓存。** 如果您选择了此选项，则在应用程序导出到某一 .msi 文件，然后该 .msi 文件导入到 BizTalk 组时，程序集将作为导入过程的一部分安装到本地计算机上的 GAC 中。  
  
-   **将添加到 MSI 文件安装 (gacutil) 上的全局程序集缓存。** 如果您选择了此选项，则在应用程序导出到某一 .msi 文件，然后应用程序根据该 .msi 文件安装到某一计算机时，程序集将作为安装过程的一部分安装到本地计算机上的 GAC 中。  
  
-   **使对 COM 组件 (regasm) 可见。** 在选择此选项时，如果应用程序导出到某一 .msi 文件，并且应用程序根据该 .msi 文件安装到计算机上，则托管的 COM 程序集将作为安装过程的一部分添加到本地计算机上的 Windows 注册表中。 如果您指定该选项，则还必须为目标中的文件指定位置。  
  
-   **提供服务的注册组件 (regsvcs)。** 在选择此选项时，如果应用程序导出到某一 .msi 文件，并且应用程序根据该 .msi 文件安装到计算机上，则托管的 COM+ 程序集将作为安装过程的一部分添加到本地计算机上的 Windows 注册表中。 如果您指定该选项，则还必须为目标中的文件指定位置。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 此外，如果您选择立即将程序集添加到 GAC 中的选项，则您的帐户必须也是本地管理员组的成员。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-modify-the-deployment-properties-of-a-resource-artifact"></a>修改资源项目的部署属性  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，依次展开 [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、包含要修改其部署选项的项目的 BizTalk 组，以及包含该项目的应用程序。  
  
3.  单击**资源**文件夹，右键单击该项目，然后单击**修改**。  
  
4.  上**选项**选项卡上，根据需要，修改的部署选项，然后单击**确定**。  
  
## <a name="see-also"></a>另请参阅  
 [管理.NET 程序集、 证书和其他资源](../core/managing-net-assemblies-certificates-and-other-resources.md)