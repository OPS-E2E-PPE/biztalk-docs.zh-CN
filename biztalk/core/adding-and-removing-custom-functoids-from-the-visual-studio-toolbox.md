---
title: 添加和删除自定义 Functoid 从 Visual Studio 工具箱 |Microsoft Docs
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
ms.openlocfilehash: 7e3493608606df11a5237287a89cbf79d384800a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360907"
---
# <a name="adding-and-removing-custom-functoids-from-the-visual-studio-toolbox"></a>添加和从 Visual Studio 工具箱中删除自定义 Functoid
本主题介绍如何添加到自定义 functoid 和删除自定义 functoid 从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱。  
  
## <a name="adding-custom-functoids-to-visual-studio"></a>向 Visual Studio 添加自定义 Functoid  
 必须将自定义 functoid 添加到[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱后才可以映射中使用它们。 使用以下过程添加自定义 functoid。  
  
#### <a name="to-add-a-custom-functoid"></a>若要添加自定义 functoid  
  
1. 添加到 functoid[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱。  
  
   1. 使用 Windows 资源管理器，找到实现自定义 functoid 的程序集。  
  
   2. 将复制到的程序集\< *BizTalk Server 安装文件夹*\>**\Developer Tools\Mapper 扩展**目录。 这是 BizTalk 映射器查找自定义 functoid。  
  
   3. 从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk 项目，在**工具**菜单中，单击**选择工具箱项**。  
  
   4. 在中**选择工具箱项**对话框中，单击**BizTalk 映射器 Functoid**选项卡。  
  
   5. 单击**重置**，然后单击**确定**。 此过程可能需要一些时间。  
  
       现在，自定义 functoid 应出现在与其类别相匹配的选项卡下的工具箱。  
  
      \- 或 -  
  
   6. 从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk 项目，在**工具**菜单中，单击**选择工具箱项**。  
  
   7. 在中**选择工具箱项**对话框中，单击**BizTalk 映射器 Functoid**选项卡。  
  
   8. 单击**重置**，然后单击**确定**。  
  
      > [!NOTE]
      >  如果自定义 functoid 没有公开任何内联代码，请确保它的程序集可在全局程序集缓存中。  
  
   9. 上**文件**菜单上，单击**退出**以关闭[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
   10. 启动**Visual Studio 命令提示符**。  
  
   11. 在命令提示符处，键入**devenv /setup**。  
  
   12. 启动**Microsoft Visual Studio**。  
  
        自定义 functoid 应出现在相应的选项卡中。  
  
2. 将程序集添加到全局程序集缓存中。 如果您的程序集只包含内联 functoid，则可以跳过此步骤。  
  
   1.  启动**Visual Studio 命令提示符**。  
  
   2.  切换到包含您的程序集的文件夹。  
  
   3.  在命令提示符处，键入**gacutil /if < assembly_path >**。 例如，如果程序集名为 FunctoidLibrary.dll，则键入**gacutil /if FunctoidLibrary.dll**。  
  
   4.  在完成后，请键入**退出**。  
  
## <a name="removing-custom-functoids-from-visual-studio"></a>从 Visual Studio 中删除自定义 Functoid  
 使用以下过程删除自定义 functoid。  
  
#### <a name="to-remove-a-custom-functoid"></a>若要删除自定义 functoid  
  
1. 删除 functoid 从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱。  
  
   1. 从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk 项目，在**工具**菜单中，单击**选择工具箱项**。  
  
   2. 在中**选择工具箱项**对话框中，单击**BizTalk 映射器 Functoid**选项卡。  
  
   3. 在列表中，选择查找自定义 functoid**删除**复选框，然后依次**确定**。  
  
      \- 或 -  
  
   4. 在编辑中的地图[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk 项目中，单击**工具箱**选项卡打开工具箱面板。  
  
   5. 单击包含自定义 functoid 的 functoid 组。  
  
   6. 右键单击你想要删除，然后单击的 functoid**删除**或按 delete 键。  
  
2. 删除 functoid 程序集从**Developer Tools\Mapper Extensions**目录。  
  
   > [!CAUTION]
   >  如果程序集包含活动的 functoid，请不要删除它。 执行此操作将中断其他映射。  
  
   1. 启动 Windows 资源管理器并导航到**Developer Tools\Mapper Extensions**目录的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
   2. 右键单击包含所删除的 functoid 的程序集，然后单击**删除**来删除该文件。  
  
3. 从全局程序集缓存中删除 functoid 程序集。 如果您的程序集只包含内联 functoid，则可以跳过此步骤。  
  
   > [!CAUTION]
   >  如果程序集包含活动的 functoid，请不要删除它从全局程序集缓存。 执行此操作将中断其他映射。  
  
   1.  启动**Visual Studio 命令提示符**。  
  
   2.  在命令提示符处，键入**gacutil /u < assembly_display_name >**。 例如，如果程序集名为 FunctoidLibrary.dll，则键入**gacutil /if FunctoidLibrary**。  
  
   3.  在完成后，请键入**退出**。  
  
## <a name="see-also"></a>请参阅  
 [开发自定义 Functoid](../core/developing-custom-functoids.md)