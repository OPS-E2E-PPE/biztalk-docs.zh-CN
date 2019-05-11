---
title: 安装和卸载期间对项目采取 |Microsoft Docs
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
ms.openlocfilehash: 16d40587751f095f2a170a747c9b969d3b08460c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395170"
---
# <a name="what-happens-to-artifacts-during-installation-and-uninstallation"></a>安装和卸载期间对项目采取
本主题介绍 BizTalk Server 如何处理包含在 BizTalk 应用程序时安装和卸载应用程序的基于文件的项目。  
  
> [!NOTE]
>  发送端口、 发送端口组、 接收位置和接收端口都不是基于文件的项目和不受安装和卸载。 业务流程、 架构、 映射和管道是所有部署和管理包含它们的 BizTalk 程序集的一部分。  
  
-   **BizTalk 程序集。** 在安装期间，BizTalk 程序集文件复制到目标路径中，如果指定了程序集添加到应用程序时。 它还会安装该程序集到全局程序集缓存 (GAC) 如果添加该程序集时指定此选项。 卸载应用程序时，程序集文件是从系统中删除文件如果它存在，但不是卸载从 GAC 中，除非开发人员要执行此操作的应用程序中包含了一个后处理脚本。 如有必要，你可以手动从 GAC 卸载 BizTalk 程序集。 有关详细信息，请参阅[如何从 GAC 卸载程序集](http://msdn.microsoft.com/library/464706a8-f902-4d05-a724-19169facd2b4)。  
  
-   **.NET 程序集。** 在安装期间，.NET 程序集文件复制到目标路径中，如果指定了程序集添加到应用程序时。 它还会安装该程序集到 GAC 和 Windows 注册表如果添加该程序集时指定了这些选项。 卸载应用程序时，如果它存在并且不是在 Windows 注册表中是从文件系统中删除程序集文件。 除非开发人员要执行此操作的应用程序中包含了一个后处理脚本，该程序集不从 GAC 或 Windows 注册表中删除。 如有必要，您可以手动从 GAC 或 Windows 注册表删除 BizTalk 程序集。 有关详细信息，请参阅[如何从 GAC 卸载程序集](http://msdn.microsoft.com/library/464706a8-f902-4d05-a724-19169facd2b4)并[如何删除其他文件和 BizTalk 应用程序设置](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md)。  
  
-   **文件。** 在安装期间，该文件复制到本地文件系统中，如果该文件添加到应用程序时指定了目标路径。 卸载应用程序时，该文件是从文件系统中删除。  
  
-   **证书。** 在安装期间，将证书添加到本地计算机上的其他人证书存储。 卸载应用程序时，不删除证书，除非开发人员要执行此操作的应用程序中包含了一个后处理脚本。 如有必要，可以手动删除证书。 有关详细信息，请参阅[如何删除其他文件和 BizTalk 应用程序设置](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md)。  
  
-   **虚拟目录。** 如果在安装应用程序的计算机上存在 Internet 信息服务 (IIS)，创建虚拟目录。 如果已具有相同名称的虚拟目录存在，它使用指定的端口，应用程序.msi 文件中的虚拟目录资源写入到现有的虚拟目录，并保留现有的虚拟目录的安全设置保持不变。 您应该验证这些安全设置足够。 如果虚拟目录绑定到的应用程序池不存在本地计算机上安装应用程序时，虚拟目录是绑定到默认应用程序池。  
  
     卸载应用程序时，虚拟目录和其文件被删除，除非在安装之前，已存在虚拟目录或文件已添加到安装后的虚拟目录。 在这种情况下，会删除已从应用程序.msi 文件安装文件。 不会删除虚拟目录和应用程序安装完成后添加到该文件。 只有当它为空，删除虚拟目录。  
  
-   **COM 组件。** 在安装期间，COM 组件添加到 Windows 注册表如果该组件添加到应用程序时指定此选项。 此外，该文件复制到本地文件系统中，如果该组件添加到应用程序时指定目标位置。 卸载应用程序时，COM 组件是不从 Windows 注册表或文件系统删除，除非开发人员要执行此功能的应用程序中包含了一个后处理脚本。 如有必要，您可以手动从 Windows 注册表和文件系统删除 COM 组件。 有关详细信息，请参阅[如何删除其他文件和 BizTalk 应用程序设置](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md)。  
  
-   **预处理和后处理脚本。** 在安装期间，脚本文件复制到本地文件系统中，如果该文件添加到应用程序时指定了目标路径。 预处理脚本运行应用程序导入或删除之前和之后卸载。 应用程序导入或删除后且在安装之前，运行后续处理脚本。 卸载应用程序时，将从文件系统中删除脚本文件。 但是，如果预处理或后处理脚本文件添加到文件系统中它们不会删除。 如有必要，可以手动删除文件。 有关详细信息，请参阅[如何删除其他文件和 BizTalk 应用程序设置](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md)。  
  
-   **BAM 项目。** 在安装期间，BAM 项目文件复制到该项目添加到应用程序时指定的目标路径。 安装应用程序时，不会部署 BAM 项目。 卸载应用程序时，会删除 BAM 项目文件。  
  
## <a name="see-also"></a>请参阅  
 [如何安装 BizTalk 应用程序](../core/how-to-install-a-biztalk-application.md)   
 [如何卸载 BizTalk 应用程序](../core/how-to-uninstall-a-biztalk-application.md)   
 [在应用程序部署期间对项目采取的操作](../core/what-happens-to-artifacts-during-application-deployment.md)