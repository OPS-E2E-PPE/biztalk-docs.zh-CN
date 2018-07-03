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
ms.openlocfilehash: e18a657679c63f02d543a842615e459f732dc88a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010990"
---
# <a name="how-to-uninstall-a-biztalk-application"></a>如何卸载 BizTalk 应用程序
本主题介绍如何使用“添加或删除程序”控制面板或 BTSTask 命令行工具卸载 BizTalk 应用程序。 它们是用于卸载应用程序的唯一支持的方法。 如果您为此应用程序安装了多个 .msi 文件（例如为了更新该应用程序），则双击该 .msi 文件或者使用 msiexec 可能不会完全卸载该应用程序，因此不是支持的卸载方法。  
  
> [!CAUTION]
>  在 BizTalk 应用程序正在运行时卸载它可能导致应用程序中出现错误。 若要避免此问题，最佳的做法是，我们建议你验证存在先决条件，没有正在运行的服务实例应用程序，如中所述[如何搜索所有服务实例](../core/how-to-search-for-all-service-instances.md)。 如果有必要，您可以停止应用程序通过使用完全停止选项来完全停止所有正在运行的实例，如中所述[如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)。 请注意，在您这样做的时候，进程内消息将不会完成。  
  
 预处理脚本或后处理脚本应该包括在应用程序 .msi 文件中，以便在卸载应用程序时删除与该应用程序关联的所有文件和设置。 如果未包括预处理脚本或后处理脚本，则本主题中的过程将从本地文件系统中删除应用程序的文件和设置，但有以下例外。  
  
- 如果应用程序包括某一虚拟目录，则该虚拟目录及其文件通常会被删除。但是，如果在安装应用程序后向该虚拟目录添加了文件， 则该虚拟目录以及所添加的文件将不会被删除。 如果您要删除该虚拟目录以及添加的文件，必须执行显式删除。  
  
- 预处理脚本和后处理脚本将被删除，但不会删除在安装或卸载期间由脚本添加的任何文件，也不会撤消脚本执行的任何操作。 如果您要删除脚本所添加的文件或撤消其操作，必须显式执行此任务。  
  
  > [!NOTE]
  >  在卸载期间，只有在导入应用程序时在其部署属性中指定了目标位置的预处理脚本或后处理脚本才会运行。 有关详细信息，请参阅[How to Add 的预处理或后处理脚本保存到应用程序](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md)。  
  
- 在卸载 BizTalk 应用程序时，永远不会删除证书。 如果您要删除某一证书，必须执行显式删除。 此外，未从 Windows 注册表和 BizTalk 程序集删除的组件也不会从全局程序集缓存 (GAC) 删除。 如果您要删除它们，必须执行显式删除。 有关详细信息，请参阅[如何删除其他文件和 BizTalk 应用程序设置](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md)。  
  
  如果在卸载完成之前取消卸载操作，则 BizTalk Server 将回滚卸载，但在取消该操作之前由预处理或后处理脚本执行的操作除外。 若要将应用程序恢复到其开始卸载前的状态，请双击 .msi 文件，然后重新安装该应用程序。 如果为此应用程序安装了多个 .msi 文件，则您应该双击每个 .msi 文件，按照这些 .msi 文件的原始安装顺序重新安装该应用程序。  
  
  有关后续处理脚本的详细信息，请参阅[使用预处理和后处理脚本自定义应用程序部署到](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)。  
  
> [!NOTE]
>  若要完全取消部署 BizTalk 应用程序，您还必须删除它从 BizTalk 组中，如中所述[如何从 BizTalk 组中删除 BizTalk 应用程序](../core/how-to-delete-a-biztalk-application-from-the-biztalk-group.md)。  
  
## <a name="prerequisites"></a>必要條件  
 为了执行本主题中的过程，您必须使用适当的权限登录。 有关详细信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="to-uninstall-a-biztalk-application"></a>卸载 BizTalk 应用程序  
  
#### <a name="using-uninstall-or-change-a-program"></a>使用卸载或更改程序  
  
1.  在运行该应用程序的计算机，单击**启动**，单击**控制面板**，然后双击**程序和功能**。  
  
2.  上**卸载或更改程序**页上，右键单击 BizTalk 应用程序，以删除，然后单击**卸载**。  
  
     Windows Installer 将删除指定的应用程序。  
  
3.  如果该应用程序正在多台计算机上运行，请在每台计算机上重复这些步骤。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1. 按如下所示打开命令提示符： 单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2. 键入以下命令，替换适当的值下, 表中所述：  
  
    **BTSTask UninstallApp** [**/ApplicationName:**<em>值</em>]  
  
    例如：  
  
    **BTSTask UninstallApp /ApplicationName:MyApplication**  
  
   |参数|ReplTest1|  
   |---------------|-----------|  
   |**/ 应用程序名称**|要卸载的 BizTalk 应用程序的名称。 如果名称包含空格，则必须将其括在双引号 （"）。|  
  
## <a name="see-also"></a>请参阅  
 [正在取消部署 BizTalk 应用程序](../core/undeploying-biztalk-applications.md)   
 [UninstallApp 命令](../core/uninstallapp-command.md)