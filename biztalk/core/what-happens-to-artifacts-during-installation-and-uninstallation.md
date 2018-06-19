---
title: 会发生什么情况项目安装和卸载期间 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- uninstalling, artifacts
- artifacts, uninstalling
- installing, artifacts
- artifacts, installing
- uninstalling
ms.assetid: f7b5bd8b-bfdf-4536-ae64-fa98c4885be6
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6274c32656ddece5a0afd81317538126d48b2f89
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289637"
---
# <a name="what-happens-to-artifacts-during-installation-and-uninstallation"></a>在安装和卸载期间什么操作到项目
本主题介绍在安装和卸载 BizTalk 应用程序时 BizTalk Server 如何处理包含在应用程序中的基于文件的项目。  
  
> [!NOTE]
>  发送端口、发送端口组、接收位置以及接收端口都不是基于文件的项目，不受安装和卸载的影响。 业务流程、架构、映射和管道都是作为包含它们的 BizTalk 程序集的一部分来部署和托管的。  
  
-   **BizTalk 程序集。** 在安装过程中，如果在将 BizTalk 程序集添加到应用程序中时指定了目标路径，则会将程序集文件复制到该路径。 如果在添加程序集时指定了此选项，还会将程序集安装到全局程序集缓存 (GAC) 中。 卸载应用程序时，如果程序集文件存在于文件系统中，会将其从中删除，但是不会将其从 GAC 中卸载，除非开发人员在应用程序中包含了一个后处理脚本来执行此操作。 如有必要，可以手动从 GAC 中卸载 BizTalk 程序集。 有关详细信息，请参阅[如何从 GAC 中卸载程序集](http://msdn.microsoft.com/library/464706a8-f902-4d05-a724-19169facd2b4)。  
  
-   **.NET 程序集。** 在安装过程中，如果在将 .NET 程序集添加到应用程序中时指定了目标路径，则会将程序集文件复制到该路径。 如果在添加程序集时指定了这些选项，还会将程序集安装到 GAC 和 Windows 注册表中。 卸载应用程序时，如果程序集文件位于文件系统中但不在 Windows 注册表中，会将其从文件系统中删除。 不会从 GAC 或 Windows 注册表中删除程序集，除非开发人员在应用程序中包含了一个后处理脚本来执行此操作。 如有必要，可以手动从 GAC 或 Windows 注册表中删除 BizTalk 程序集。 有关详细信息，请参阅[如何从 GAC 中卸载程序集](http://msdn.microsoft.com/library/464706a8-f902-4d05-a724-19169facd2b4)和[如何的 BizTalk 应用程序删除其他文件和设置](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md)。  
  
-   **文件。** 在安装过程中，如果在将文件添加到应用程序中时指定了目标路径，则会将文件复制到本地文件系统中。 卸载应用程序时，会从文件系统中删除该文件。  
  
-   **证书。** 在安装过程中，证书将添加到本地计算机上的“其他人”证书存储中。 卸载应用程序时，不会删除证书，除非开发人员在应用程序中包含了一个后处理脚本来执行此操作。 如有必要，可以手动删除证书。 有关详细信息，请参阅[如何的 BizTalk 应用程序删除其他文件和设置](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md)。  
  
-   **虚拟目录。** 如果应用程序所在的计算机上存在 Internet 信息服务 (IIS)，则会创建虚拟目录。 如果使用指定端口的具有相同名称的虚拟目录已经存在，则会将应用程序 .msi 文件中的虚拟目录资源写入现有虚拟目录，并且现有虚拟目录的安全设置保持不变。 您应当验证这些安全设置是否满足要求。 如果在安装应用程序时本地计算机上不存在虚拟目录所绑定到的应用程序池，会将虚拟目录绑定到默认应用程序池。  
  
     卸载应用程序时，将删除虚拟目录及其文件，除非该虚拟目录在安装前已经存在，或者在安装后向虚拟目录中添加了文件。 在这种情况下，只会删除从应用程序 .msi 文件中安装的文件， 而不会删除该虚拟目录以及在应用程序安装后向其中添加的文件。 仅当虚拟目录为空时才会将其删除。  
  
-   **COM 组件。** 在安装过程中，如果在将 COM 组件添加到应用程序中时指定了相关选项，则会将该组件添加到 Windows 注册表中。 此外，如果在将该组件添加到应用程序中时指定了目标位置，则会将文件复制到本地文件系统中。 卸载应用程序时，不会从 Windows 注册表或文件系统中删除 COM 组件，除非开发人员在应用程序中包含了一个后处理脚本来执行此功能。 如有必要，可以手动从 Windows 注册表和文件系统中删除 COM 组件。 有关详细信息，请参阅[如何的 BizTalk 应用程序删除其他文件和设置](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md)。  
  
-   **预处理和后续处理脚本。** 在安装过程中，如果在将脚本文件添加到应用程序中时指定了目标路径，则会将这些文件复制到本地文件系统中。 预处理脚本在导入或删除应用程序之前以及卸载应用程序之后运行。 后处理脚本在导入或删除应用程序之后以及安装应用程序之前运行。 卸载应用程序时，会从文件系统中删除脚本文件。 但是，如果预处理脚本或后处理脚本向文件系统中添加了文件，则不会删除这些文件。 如有必要，可以手动删除这些文件。 有关详细信息，请参阅[如何的 BizTalk 应用程序删除其他文件和设置](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md)。  
  
-   **BAM 项目。** 在安装过程中，会将 BAM 项目文件复制到在将项目添加到应用程序中时指定的目标路径。 安装应用程序时不会部署 BAM 项目。 卸载应用程序时，会删除 BAM 项目文件。  
  
## <a name="see-also"></a>另请参阅  
 [如何安装 BizTalk 应用程序](../core/how-to-install-a-biztalk-application.md)   
 [如何卸载 BizTalk 应用程序](../core/how-to-uninstall-a-biztalk-application.md)   
 [会发生什么情况项目在应用程序部署过程](../core/what-happens-to-artifacts-during-application-deployment.md)