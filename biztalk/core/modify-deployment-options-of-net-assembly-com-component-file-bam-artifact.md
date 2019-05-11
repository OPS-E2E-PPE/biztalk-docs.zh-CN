---
title: 如何修改.NET 程序集、 COM 组件、 文件或 BAM 项目的部署选项 |Microsoft Docs
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
ms.openlocfilehash: a516857d6f790dfd1d5f4c7ad51c34144913785b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65324585"
---
# <a name="how-to-modify-the-deployment-options-of-a-net-assembly-com-component-file-or-bam-artifact"></a>如何修改.NET 程序集、 COM 组件、 文件或 BAM 项目的部署选项
本主题介绍如何使用 BizTalk Server 管理控制台来修改以下资源项目的部署选项：  
  
- .NET 程序集  
  
- COM 组件  
  
- 特别文件  
  
- BAM 项目  
  
  你可能想要修改部署属性，以便更改在本地计算机上安装应用程序项目文件将复制到的目标位置。 如果未提供路径，该文件将不复制到本地计算机上安装。  
  
  此外，你可能想要修改.NET 程序集的以下选项：  
  
- **将添加到全局程序集缓存添加资源 (gacutil)。** 如果选择此选项，该程序集时将添加到全局程序集缓存 (GAC) 在本地计算机上该程序集添加到应用程序。 此外，如果您以后刷新该程序集 (右键单击它，然后单击**刷新**)，该程序集添加到 GAC。 清除此选项的复选框不会删除该程序集从 GAC 中，如果当前存在。  
  
- **将添加到 MSI 文件导入 (gacutil) 上的全局程序集缓存。** 当选中此选项时，如果应用程序导出到.msi 文件，并且该.msi 文件导入到 BizTalk 组，导入过程的一部分在本地计算机上的 GAC 中安装该程序集。  
  
- **添加到全局程序集缓存 (gacutil) 安装 MSI 文件。** 当选择此选项时，如果应用程序导出到.msi 文件，并根据该.msi 文件的计算机上安装应用程序时，作为安装过程的一部分在本地计算机上的 GAC 中安装该程序集。  
  
- **请对 COM 组件可见 (regasm)。** 时选择此选项时，如果应用程序导出到.msi 文件，并根据该.msi 文件的计算机上安装应用程序，托管的 COM 程序集添加到作为安装过程的一部分在本地计算机上的 Windows 注册表中。 如果指定此选项，还必须指定目标中的文件的位置。  
  
- **注册服务组件 (regsvcs)。** 时选择此选项时，如果应用程序导出到.msi 文件，并根据该.msi 文件的计算机上安装应用程序，托管的 COM + 程序集添加到作为安装过程的一部分在本地计算机上的 Windows 注册表中。 如果指定此选项，还必须指定目标中的文件的位置。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 此外，如果您选择立即将程序集添加到 GAC 的选项，你的帐户还必须是本地管理员组的成员。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-modify-the-deployment-properties-of-a-resource-artifact"></a>若要修改资源项目的部署属性  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开包含要修改部署选项，该项目的 BizTalk 组，然后展开包含该项目的应用程序。  
  
3. 单击**资源**文件夹，右键单击该项目，然后单击**修改**。  
  
4. 上**选项**选项卡上，根据需要，修改部署选项，然后单击**确定**。  
  
## <a name="see-also"></a>请参阅  
 [管理 .NET 程序集、证书和其他资源](../core/managing-net-assemblies-certificates-and-other-resources.md)