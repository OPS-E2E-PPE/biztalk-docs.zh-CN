---
title: 如何将应用和删除跟踪配置文件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, tracking profiles
- tracking profiles, testing
- tracking profiles, deleting
- testing, tracking profiles
ms.assetid: 77cef14b-c390-4da7-a383-b3abe414a168
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e98745e48edc1dea194e33bb8ac3cde9a70d8b7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387202"
---
# <a name="how-to-apply-and-remove-a-tracking-profile"></a>如何将应用和删除跟踪配置文件
创建或修改跟踪配置文件后下, 一步是将其应用到测试数据库并验证通过集成测试的结果。 您可以应用跟踪配置文件与在跟踪配置文件编辑器 (TPE) 自身或使用命令行。  
  
## <a name="prerequisites"></a>先决条件  
 以前创建的跟踪配置文件保存到您的硬盘。  
  
### <a name="to-apply-the-tracking-profile-from-within-the-tpe"></a>若要将跟踪配置文件从 TPE 内应用  
  
1. 单击**启动**，依次指向**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**跟踪配置文件编辑器**。  
  
   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。 要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。  
  
2. 上**文件**菜单上，单击**打开**。 导航到你硬盘上的.btt 文件。 单击**打开**加载它。  
  
3. 上**工具**菜单上，单击**应用跟踪配置文件**将该.btt 文件应用于已从设置管理数据库**设置管理数据库**上的菜单项**工具**菜单。 验证通过集成测试的结果。  
  
4. 通知的人员负责部署在组织中的跟踪配置文件测试正确并且已准备好进行部署。  
  
### <a name="to-apply-the-tracking-profile-from-the-command-line"></a>若要从命令行应用跟踪配置文件  
  
-   从命令提示符处，运行位于 \Tracking 文件夹中，如下所示的 bttdeploy.exe 工具：  
  
    ```  
    bttdeploy.exe <profile name>.btt  
    ```  
  
> [!NOTE]
>  必须具有 BizTalk 管理员权限才能使用此工具。  
  
> [!NOTE]
>  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。 要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。  
  
> [!IMPORTANT]
>  在部署期间，bttdeploy 验证跟踪配置文件中包含的程序集版本，并其与已部署的程序集的版本。 如果当前未部署该程序集，则 Bttdeploy 将失败。  
  
> [!IMPORTANT]
>  当从命令行应用跟踪配置文件，bttdeploy 将适用于运行配置向导时所指定的 BizTalk 管理数据库配置文件。 如果在跟踪配置文件编辑器选项中指定了其他数据库设置为使用"设置管理数据库"，然后该设置。 如果您指定为 bttdeploy 的命令行选项的一部分的管理服务器和数据库，然后在命令行选项将覆盖所有其他。 有关使用 bttdeploy 的详细信息，请参阅[跟踪配置文件部署实用程序](../core/tracking-profile-deployment-utility.md)。  
  
### <a name="to-remove-a-tracking-profile"></a>若要删除的跟踪配置文件  
  
1. 单击**启动**，依次指向**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**跟踪配置文件编辑器**。  
  
   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。 要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。  
  
2. 上**文件**菜单上，单击**打开**。 导航到你硬盘上的.btt 文件。 单击**打开**加载它。  
  
3. 上**工具**菜单上，单击**删除跟踪配置文件**删除跟踪配置文件基于该.btt 文件从 BizTalk 管理数据库。  
  
## <a name="see-also"></a>请参阅  
 [创建跟踪配置文件](../core/creating-tracking-profiles.md)