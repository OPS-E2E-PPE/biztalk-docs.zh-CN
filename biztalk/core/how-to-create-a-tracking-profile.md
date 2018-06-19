---
title: 如何创建跟踪配置文件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tracking profiles, creating
- creating, tracking profiles
ms.assetid: 676ae7e8-f3eb-45f1-ad2e-807b434c0bf9
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34f5d6cbb210cb292cd8ae7d0e2f4ff811984377
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248933"
---
# <a name="how-to-create-a-tracking-profile"></a>如何创建跟踪配置文件
创建跟踪配置文件可将 BAM 活动定义链接到部署的程序集和 BizTalk Server 消息传送属性。 跟踪配置文件编辑器打开时，你可以通过单击导入活动链接或导入菜单项来创建新的跟踪配置文件。  
  
## <a name="prerequisites"></a>先决条件  
 以下为执行本主题中的过程的前提条件：  
  
-   您有权访问现有的 BizTalk 管理数据库。  
  
-   TPE 配置为使用 BizTalk 管理数据库。  
  
-   BAM 主导入数据库中已有 BAM 活动定义。  
  
### <a name="to-create-a-tracking-profile"></a>创建跟踪配置文件  
  
1.  在计算机或已标识为源系统的计算机中，打开**跟踪配置文件编辑器**。 若要执行此操作，请单击**启动**，单击**运行**，类型**BTSTrkEditor.exe**，然后单击**确定**。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。 要执行此操作，右键单击该应用程序，，然后选择**以管理员身份运行**。  
  
2.  中间键入的左窗格中，单击**单击此处以导入 BAM 活动定义**链接。 这将打开**导入 BAM 活动定义**对话框。  
  
3.  从**BAM 活动定义名称**列表框中选择要作为跟踪依据的活动。 如果你的列表包含许多已部署的活动，你可以键入部分中的活动名称**中字符串**文本框中，然后单击**搜索**按钮。 这将使活动列表仅显示名称中包含您输入的部分名称的活动。  
  
4.  在选择活动，单击**确定**按钮。 此时将打开基于所选活动的新跟踪配置文件，并在 TPE 的左窗格中显示该配置文件。  
  
## <a name="see-also"></a>另请参阅  
 [创建跟踪配置文件](../core/creating-tracking-profiles.md)