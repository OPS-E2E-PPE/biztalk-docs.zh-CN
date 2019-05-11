---
title: 如何创建跟踪配置文件 |Microsoft Docs
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
ms.openlocfilehash: bb5951042bc3f3bbc3c2379cc83ab07de0d35c0e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385555"
---
# <a name="how-to-create-a-tracking-profile"></a>如何创建跟踪配置文件
创建跟踪配置文件可将 BAM 活动定义链接到已部署程序集和 BizTalk Server 消息传送属性。 当您打开跟踪配置文件编辑器时，可以通过单击导入活动链接或导入菜单项来创建新的跟踪配置文件。  
  
## <a name="prerequisites"></a>先决条件  
 在本主题中执行该过程的先决条件如下：  
  
-   现有的 BizTalk 管理数据库对其具有权限。  
  
-   TPE 配置为使用 BizTalk 管理数据库。  
  
-   BAM 主导入数据库中的现有 BAM 活动定义。  
  
### <a name="to-create-a-tracking-profile"></a>若要创建跟踪配置文件  
  
1.  在计算机或计算机已标识为源系统中，打开**跟踪配置文件编辑器**。 若要执行此操作，请单击**启动**，单击**运行**，类型**BTSTrkEditor.exe**，然后单击**确定**。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。 要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。  
  
2.  中间 TPE 的左窗格中，单击**单击此处可导入 BAM 活动定义**链接。 这将打开**导入 BAM 活动定义**对话框。  
  
3.  从**BAM 活动定义名称**列表框选择要跟踪所基于的活动。 如果列表包含许多已部署的活动，则可以键入中的活动名称的一部分**字符串中**文本框中，然后单击**搜索**按钮。 这将限制为那些名称中包含输入的部分名称显示的活动列表。  
  
4.  一旦选择活动后，单击**确定**按钮。 这将打开基于所选活动的新跟踪配置文件，并在 TPE 的左窗格中显示该配置文件。  
  
## <a name="see-also"></a>请参阅  
 [创建跟踪配置文件](../core/creating-tracking-profiles.md)