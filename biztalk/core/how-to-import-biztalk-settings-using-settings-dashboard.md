---
title: 导入或导出 BizTalk 设置使用设置仪表板 |Microsoft Docs
description: 使用 BizTalk Server 管理导入或导出 BizTalk Server 环境之间的设置
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc2f0b44-d79b-4f95-811a-0843e3d6d1c8
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3713ee7906d735b6328b50d3b97a214422893d21
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970214"
---
# <a name="use-settings-dashboard-to-import-or-export-biztalk-settings"></a>使用设置仪表板导入或导出 BizTalk 设置 

## <a name="overview"></a>概述
使用“BizTalk 设置仪表板”，您可以从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境导出设置，然后将其导入到另一 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境，从而减少整个解决方案的时间。  这在以下情况时尤为有用：当 BizTalk 管理员尝试在临时环境中调整 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 性能，一旦达到预期结果，他们就会将设置导入生产环境。 本主题提供了使用设置仪表板导入 BizTalk 组、主机和的主机实例设置的分步过程。  

> [!TIP]
> 此外可以使用 BTSTask 命令行实用工具导入或导出的组、 主机和主机实例设置。 请参阅[导入或导出 BizTalk 设置使用 BTSTask](how-to-import-biztalk-settings-using-btstask.md)。

  
## <a name="prerequisites"></a>必要條件  
 若要执行此操作，必须以 BizTalk Server Administrators 组的成员的身份登录。  
  
## <a name="import-the-biztalk-group-host-and-host-instance-settings"></a>导入 BizTalk 组、 主机和主机实例设置  

> [!IMPORTANT]
>  若要从某个环境导入 BizTalk Server 设置，您应已保存这些设置并将它们导出到 XML 文件中。 **导出 BizTalk 设置**（在本主题中） 或[导入或导出 BizTalk 设置使用 BTSTask](how-to-import-biztalk-settings-using-btstask.md)可以帮助。
  
 通过导入到 XML 文件，您可以在目标计算机上复制所需的 BizTalk Server 设置。 使用设置仪表板，您可以导入组、主机和主机实例设置，并将一个设置的属性映射到另一个设置的属性。 以下是有关导入设置的必要假设：  
  
-   BizTalk Server 拓扑从源环境到目标环境是一致的。  
  
-   可以映射源和目标环境的主机定义。 您应该能够使用目标环境中的主机映射源环境中的全部主机。  
  
-   目标环境具有与源环境相似的硬件（即使不完全相同）。 因为某些设置取决于基础硬件，所以这很重要。  

### <a name="import-steps"></a>导入步骤
  
1. 在中**BizTalk Server 管理控制台**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击**BizTalk 组**，然后单击**设置**。  
  
2. 在中**BizTalk 设置仪表板**对话框中，单击**导入**。 **导入设置向导**对话框随即出现。  
  
   > [!NOTE]
   >  **目标组**显示你想要导入设置的目标计算机的组信息。  
  
    ![指定要导入设置的文件位置](../core/media/importsettings-filelocation.jpg "ImportSettings_FileLocation")  
  
3. 单击**指定文件位置**页上，然后依次![浏览设置文件](../core/media/importsettings-filelocationbrowse.gif "ImportSettings_FileLocationBrowse")。 此时会出现文件资源管理器。  
  
4. 选择包含源环境设置的 XML 文件，然后单击**打开**。 **文件位置**显示的 XML 文件的路径和**源组**填充的源计算机的组信息。 单击“下一步” 。  
  
5. 上**主机映射**页上，执行以下操作：  
  
   1.  从**目标主机**列表中，选择你想要指定源主机，然后单击目标主机**添加**。  
  
        ![主机映射](../core/media/importsettings-hostmapping.gif "ImportSettings_HostMapping")  
  
   2.  在中**选择源实体**对话框中，选择源主机，然后单击**确定**。  
  
       > [!NOTE]
       >  若要将映射到单个源主机的多个目标主机，请重复步骤**5a**并**5b**。  
  
   3.  在中**主机映射**页上，单击**下一步**。  
  
6. 在中**主机实例映射**页上，执行以下操作：  
  
   1.  从目标主机实例列表中，选择你想要指定源主机实例，并单击目标主机实例**添加**。  
  
       > [!NOTE]
       >  主机实例只能映射到已在主机映射中创建的对应主机。 例如，如果指定了一个映射其中**SourceHost1**映射到**DestinationHost1**，然后实例**DestinationHost1**只能映射到的实例**SourceHost1**。  
       >   
       >  导入向导会管理上述约束，您需要遵循此约束，否则 BizTalk 任务将会引发错误。  
       >   
       >  您需要使用约定**hostname: Machinename**在映射文件中指定的主机实例。 例如， **host1: server1**映射中文件表示的实例**Host1**正在运行或可在上找到**Server1**。  
  
        ![主机实例映射](../core/media/importsettings-hostinstancemapping.gif "ImportSettings_HostInstanceMapping")  
  
   2.  在中**选择源实体**对话框中，选择源主机实例，并单击**确定**。  
  
       > [!NOTE]
       >  若要将多个目标主机实例映射到单个源主机实例，重复步骤**6a**到**6b**。  
  
   3.  在中**主机实例映射**选项卡上，单击**下一步**。  
  
7. 在中**导入摘要**对话框中，验证你创建的目标和源环境的所有导入设置是否为所需，，然后单击**导入**。 **进度**页将显示导入设置的进度。  
  
   > [!WARNING]
   >  不能撤销 BizTalk Server 设置的导入。 如果单击**导入**，启动从源环境的设置导入到目标环境的过程并**取消**被禁用。 确保你想要继续进行之前单击导入**导入**。  
  
8. 在中**导入结果**选项卡上，检查组、 主机和主机实例设置的导入状态，然后单击**完成**才能完成导入操作。 此时，所有导入的源环境设置都已应用到目标环境。  
  
    ![将结果导入](../core/media/importsettings-importresults.gif "ImportSettings_ImportResults")  

## <a name="export-the-biztalk-group-host-and-host-instance-settings"></a>导出 BizTalk 组、 主机和主机实例设置  

1. 在中**BizTalk Server 管理控制台**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击**BizTalk 组**，然后单击**设置**。  
  
2. 在中**BizTalk 设置仪表板**对话框中，单击**导出**。 将显示 **“另存为”** 对话框。  
  
3. 浏览至要保存当前 BizTalk 设置的位置。 输入的文件名，选择类型为 XML 格式，然后单击**保存**。  

> [!IMPORTANT]
>  我们做不建议手动更新导出的 XML 文件。 已更新的 XML 文件导入到生产环境中，导入过程可能会由于某些数据类型不匹配或由手动编辑导致其他错误而失败。  

## <a name="see-also"></a>请参阅  
 [使用设置仪表板进行 BizTalk Server 性能调整](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)