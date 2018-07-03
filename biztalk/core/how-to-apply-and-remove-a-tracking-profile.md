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
ms.openlocfilehash: ffc3b321647a5861a4b4b3d24251f1ecf013ee09
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985022"
---
# <a name="how-to-apply-and-remove-a-tracking-profile"></a>如何应用和删除跟踪配置文件
创建或修改完跟踪配置文件后，下一步是将其应用到测试数据库并通过集成测试来验证结果。 可以从跟踪配置文件编辑器 (TPE) 自身内应用跟踪配置文件，也可以使用命令行来应用跟踪配置文件。  
  
## <a name="prerequisites"></a>必要條件  
 硬盘上保存有以前创建的跟踪配置文件。  
  
### <a name="to-apply-the-tracking-profile-from-within-the-tpe"></a>从 TPE 内应用跟踪配置文件  
  
1. 单击**启动**，依次指向**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**跟踪配置文件编辑器**。  
  
   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。 要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。  
  
2. 上**文件**菜单上，单击**打开**。 导航到硬盘中需要的 .btt 文件。 单击**打开**加载它。  
  
3. 上**工具**菜单上，单击**应用跟踪配置文件**将该.btt 文件应用于已从设置管理数据库**设置管理数据库**上的菜单项**工具**菜单。 通过集成测试验证结果。  
  
4. 通知您的组织中负责部署的人员跟踪配置文件测试正确并且已准备好进行部署。  
  
### <a name="to-apply-the-tracking-profile-from-the-command-line"></a>通过命令行应用跟踪配置文件  
  
-   在命令提示符处，运行位于 \Tracking 文件夹中的 bttdeploy.exe 工具，如下所示：  
  
    ```  
    bttdeploy.exe <profile name>.btt  
    ```  
  
> [!NOTE]
>  必须具有 BizTalk 管理员权限才能使用此工具。  
  
> [!NOTE]
>  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。 要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。  
  
> [!IMPORTANT]
>  在部署期间，bttdeploy 会验证跟踪配置文件中包含的程序集版本，并将其与已部署的程序集的版本进行比较。 如果当前未部署配置文件中指定的程序集，则 bttdeploy 将失败。  
  
> [!IMPORTANT]
>  通过命令行应用跟踪配置文件时，bttdeploy 会将跟踪配置文件应用到在运行配置向导时所指定的 BizTalk 管理数据库。 如果您在跟踪配置文件编辑器选项“设置管理数据库”中指定了其他数据库设置，则会使用该设置。 如果将管理服务器和数据库指定为 bttdeploy 的命令行选项，则该命令行选项将覆盖所有其他设置。 有关使用 bttdeploy 的详细信息，请参阅[跟踪配置文件部署实用程序](../core/tracking-profile-deployment-utility.md)。  
  
### <a name="to-remove-a-tracking-profile"></a>删除跟踪配置文件  
  
1. 单击**启动**，依次指向**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**跟踪配置文件编辑器**。  
  
   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。 要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。  
  
2. 上**文件**菜单上，单击**打开**。 导航到硬盘中需要的 .btt 文件。 单击**打开**加载它。  
  
3. 上**工具**菜单上，单击**删除跟踪配置文件**删除跟踪配置文件基于该.btt 文件从 BizTalk 管理数据库。  
  
## <a name="see-also"></a>请参阅  
 [创建跟踪配置文件](../core/creating-tracking-profiles.md)