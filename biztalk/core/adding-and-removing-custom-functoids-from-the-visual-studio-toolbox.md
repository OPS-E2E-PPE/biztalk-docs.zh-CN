---
title: 添加和删除自定义 Functoid 从 Visual Studio 工具箱 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 28f798cc-da97-4332-a842-ba87ac7b13b8
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 955c526c39a1cbb376a0d83848554bdeb6cc15c7
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965611"
---
# <a name="adding-and-removing-custom-functoids-from-the-visual-studio-toolbox"></a>从 Visual Studio 工具箱添加和删除自定义 Functoid
本主题将介绍如何向 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 工具箱添加以及从中删除自定义 functoid。  
  
## <a name="adding-custom-functoids-to-visual-studio"></a>向 Visual Studio 添加自定义 functoid  
 自定义 functoid 只有在添加到 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 工具箱后才可以在映射中使用。 使用以下过程可以添加自定义 functoid。  
  
#### <a name="to-add-a-custom-functoid"></a>添加自定义 functoid  
  
1.  向 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 工具箱添加 functoid。  
  
    1.  用 Windows 资源管理器找到实现自定义 functoid 的程序集。  
  
    2.  将复制到的程序集\< *BizTalk Server 安装文件夹*\>**\Developer Tools\Mapper 扩展**目录。 这是 BizTalk 映射器查找自定义 functoid 的位置。  
  
    3.  从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk 项目，在**工具**菜单上，单击**选择工具箱项**。  
  
    4.  在**选择工具箱项**对话框中，单击**BizTalk 映射程序 Functoid**选项卡。  
  
    5.  单击**重置**，然后单击**确定**。 此进程可能需要花费一些时间。  
  
         现在，自定义 functoid 应该出现在工具箱中的与其类别相匹配的选项卡下。  
  
     \- 或 -  
  
    1.  从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk 项目，在**工具**菜单上，单击**选择工具箱项**。  
  
    2.  在**选择工具箱项**对话框中，单击**BizTalk 映射程序 Functoid**选项卡。  
  
    3.  单击**重置**，然后单击**确定**。  
  
        > [!NOTE]
        >  如果自定义 functoid 没有公开任何内联代码，请确保全局程序集缓存中包含其程序集。  
  
    4.  上**文件**菜单上，单击**退出**关闭[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
    5.  启动**Visual Studio 命令提示**。  
  
    6.  在命令提示符处，键入**devenv /setup**。  
  
    7.  启动**Microsoft Visual Studio**。  
  
         此时自定义 functoid 应出现在相应的选项卡中。  
  
2.  将相应程序集添加到全局程序集缓存中。 如果程序集只包含内联 functoid，则可以跳过此步骤。  
  
    1.  启动**Visual Studio 命令提示**。  
  
    2.  切换到包含你的程序集的文件夹。  
  
    3.  在命令提示符处，键入**gacutil /if < assembly_path >**。 例如，如果你的程序集名称为 FunctoidLibrary.dll，然后键入**gacutil /if FunctoidLibrary.dll**。  
  
    4.  当完成后时，请键入**退出**。  
  
## <a name="removing-custom-functoids-from-visual-studio"></a>从 Visual Studio 中删除自定义 functoid  
 使用以下过程可以删除自定义 functoid。  
  
#### <a name="to-remove-a-custom-functoid"></a>删除自定义 functoid  
  
1.  删除从 functoid[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱。  
  
    1.  从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk 项目，在**工具**菜单上，单击**选择工具箱项**。  
  
    2.  在**选择工具箱项**对话框中，单击**BizTalk 映射程序 Functoid**选项卡。  
  
    3.  查找在列表中，选择自定义 functoid**删除**复选框，并依次**确定**。  
  
     \- 或 -  
  
    1.  编辑映射中的时[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk 项目，单击**工具箱**选项卡以打开工具箱调色板。  
  
    2.  单击包含自定义 functoid 的 functoid 组。  
  
    3.  右键单击你想要删除，，然后单击的 functoid**删除**或按 delete 键。  
  
2.  删除 functoid 集**开发人员 Tools\Mapper 扩展**目录。  
  
    > [!CAUTION]
    >  如果程序集包含活动的 functoid，请不要删除它。 因为这样做将中断其他映射。  
  
    1.  启动 Windows 资源管理器并导航到**开发人员 Tools\Mapper 扩展**目录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
    2.  右键单击删除 functoid，包含的程序集，然后单击**删除**来删除该文件。  
  
3.  从全局程序集缓存中删除 functoid 程序集。 如果程序集只包含内联 functoid，则可以跳过此步骤。  
  
    > [!CAUTION]
    >  如果该程序集包含活动的 functoid，请不要从全局程序集缓存中删除它。 因为这样做将中断其他映射。  
  
    1.  启动**Visual Studio 命令提示**。  
  
    2.  在命令提示符处，键入**gacutil /u < assembly_display_name >**。 例如，如果你的程序集名称为 FunctoidLibrary.dll，然后键入**gacutil /if FunctoidLibrary**。  
  
    3.  当完成后时，请键入**退出**。  
  
## <a name="see-also"></a>另请参阅  
 [开发自定义 Functoid](../core/developing-custom-functoids.md)