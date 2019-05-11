---
title: 如何卸载 BizTalk 应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [applications], uninstalling
- applications, uninstalling
- uninstalling, applications
- undeploying, uninstalling
ms.assetid: ab721c6e-194e-4b8a-bfd1-d0139d284373
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec0383549edc37d1767e69d9fcb6ac571a56ae04
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333784"
---
# <a name="how-to-uninstall-a-biztalk-application"></a>如何卸载 BizTalk 应用程序
本主题介绍如何使用添加或删除程序控制面板或 BTSTask 命令行工具卸载 BizTalk 应用程序。 这些是用于卸载应用程序的唯一受支持的方法。 如果你安装此应用程序的多个.msi 文件，例如若要更新应用程序中，双击该.msi 文件或使用 msiexec 可能无法完全卸载该应用程序，因此不支持的卸载方法。  
  
> [!CAUTION]
>  卸载 BizTalk 应用程序在运行时可导致应用程序中出现错误。 若要避免此问题，最佳的做法是，我们建议你验证存在先决条件，没有正在运行的服务实例应用程序，如中所述[如何搜索所有服务实例](../core/how-to-search-for-all-service-instances.md)。 如果有必要，您可以停止应用程序通过使用完全停止选项来完全停止所有正在运行的实例，如中所述[如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)。 请注意时执行此操作时，将无法完成进程内消息数。  
  
 预处理或后处理脚本应包含在应用程序.msi 文件中删除所有的文件和应用程序时将其卸载相关的设置。 如果尚未包括预处理或后处理脚本，此主题中的过程将从本地文件系统，但存在以下例外删除应用程序的文件和设置。  
  
- 如果应用程序中包括虚拟目录，虚拟目录和其文件被删除，除非应用程序安装后将文件添加到虚拟目录。 在这种情况下，虚拟目录以及添加的文件不会删除。 如果你想要删除的虚拟目录以及添加的文件，您必须执行显式删除。  
  
- 预处理和后处理脚本将被删除，但不是会删除在安装或卸载期间由脚本添加任何文件，也不会撤消脚本执行任何操作。 如果你想要删除脚本所添加的文件或撤消其操作，您必须执行显式删除。  
  
  > [!NOTE]
  >  仅 pre-或后处理脚本时导入应用程序在其部署属性中指定了目标位置将在卸载期间运行。 有关详细信息，请参阅[How to Add 的预处理或后处理脚本保存到应用程序](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md)。  
  
- 卸载 BizTalk 应用程序时，永远不会删除证书。 如果你想要删除证书，你必须执行显式删除。 此外，不会从 Windows 注册表删除组件和 BizTalk 程序集不会从全局程序集缓存 (GAC) 中删除。 如果你想要将其删除，你必须执行显式删除。 有关详细信息，请参阅[如何删除其他文件和 BizTalk 应用程序设置](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md)。  
  
  如果在完成之前取消卸载操作，BizTalk Server 将回滚卸载，除了由预处理或后处理脚本在执行操作之前执行任何操作已取消。 若要开始卸载之前，请还原到其状态的应用程序，请双击该.msi 文件并重新安装该应用程序。 如果为此应用程序安装了多个.msi 文件，应该双击每个.msi 文件以重新安装该应用程序最初安装的.msi 文件的顺序。  
  
  有关后续处理脚本的详细信息，请参阅[使用预处理和后处理脚本自定义应用程序部署到](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)。  
  
> [!NOTE]
>  若要完全取消部署 BizTalk 应用程序，您还必须删除它从 BizTalk 组中，如中所述[如何从 BizTalk 组中删除 BizTalk 应用程序](../core/how-to-delete-a-biztalk-application-from-the-biztalk-group.md)。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须具有相应权限的身份登录。 有关详细信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="to-uninstall-a-biztalk-application"></a>若要卸载 BizTalk 应用程序  
  
#### <a name="using-uninstall-or-change-a-program"></a>使用卸载或更改程序  
  
1.  在运行该应用程序的计算机，单击**启动**，单击**控制面板**，然后双击**程序和功能**。  
  
2.  上**卸载或更改程序**页上，右键单击 BizTalk 应用程序，以删除，然后单击**卸载**。  
  
     Windows 安装程序中删除指定的应用程序。  
  
3.  如果多台计算机上运行该应用程序，重复的每台计算机上的这些步骤。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1. 打开命令提示符，如下所示：单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2. 键入以下命令，替换适当的值下, 表中所述：  
  
    **BTSTask UninstallApp** [**/ApplicationName:**<em>value</em>]  
  
    例如：  
  
    **BTSTask UninstallApp /ApplicationName:MyApplication**  
  
   |参数|ReplTest1|  
   |---------------|-----------|  
   |**/ApplicationName**|若要卸载的 BizTalk 应用程序的名称。 如果名称包含空格，则必须将其括在双引号 （"）。|  
  
## <a name="see-also"></a>请参阅  
 [正在取消部署 BizTalk 应用程序](../core/undeploying-biztalk-applications.md)   
 [UninstallApp 命令](../core/uninstallapp-command.md)