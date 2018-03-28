---
title: 如何打开、 保存、 关闭，以及重命名映射 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9aa88ca7-a731-4295-8692-6dd36fdf0872
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9383dd3751f9ccdd7790b0215e596eba95dc4a45
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-open-save-close-and-rename-maps"></a>如何打开、 保存、 关闭，以及重命名映射
在 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，映射在文件系统中以扩展名为 .btm 的文件形式存在。 不过，它是得更加常见，若要使用映射作为 BizTalk 项目，你在其中执行操作，如打开、 保存和关闭地图中的项。  
  
### <a name="to-open-a-map"></a>若要打开地图  
  
1.  在解决方案资源管理器，选择你想要打开的映射。  
  
2.  上 **视图** 菜单上，单击 **打开**。  
  
     在 BizTalk 映射程序中打开代码图。  
  
    > [!NOTE]
    >  你可以右键单击解决方案资源管理器中的映射，然后单击 **打开**, ，或只需双击解决方案资源管理器中的映射。  
  
### <a name="to-save-a-map"></a>用于保存代码图  
  
1.  在解决方案资源管理器，选择你想要保存的映射。  
  
2.  上**文件**菜单上，单击 * * 保存 *\<名称的映射\>* * *。  
  
### <a name="to-save-a-map-to-a-new-location"></a>若要保存到一个新位置的地图  
  
1.  在解决方案资源管理器，选择你想要将保存到新位置的映射。  
  
2.  上**文件**菜单上，单击**保存*\<名称的映射\>*作为**。  
  
3.  在 **文件另存为** 对话框中，浏览到你想要保存代码图的文件夹位置。  
  
4.  在 **文件名** 框中，键入该文件的名称，然后单击 **保存**。  
  
    > [!IMPORTANT]
    >  不使用地图的以下名称:"XmlContent"、"SourceSchemas"、"TargetSchemas"或"XsltArgumentListContent";因此，这样做将在 C# 中生成的代码的相应的.NET 程序集导致编译问题。 问题和及其解决方法有关的信息，请参阅[故障排除地图](../core/troubleshooting-maps.md)。  
  
### <a name="to-rename-a-map"></a>若要重命名地图  
  
1.  在解决方案资源管理器，右键单击你想要重命名，然后单击地图 **重命名**。  
  
2.  在出现在解决方案资源管理器中的映射的位置编辑框中，键入新名称的地图或改变其现有的名称，，然后按 ENTER。  
  
> [!NOTE]
>  你可能还想要更改 **类型名称** 映射时将其重命名。 你更改 **类型名称** 通过选择 **映射** 在解决方案资源管理器并输入中的新名称 **类型名称** 属性窗口中。  
  
#### <a name="to-close-a-map"></a>若要关闭映射  
  
1.  在解决方案资源管理器，选择你想要关闭的映射。  
  
2.  在 **“文件”** 菜单上，单击 **“关闭”**。  
  
    > [!NOTE]
    >  您也可以单击关闭图标 ([**x**]) 的 Microsoft 右上角[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]编辑窗口。  
  
## <a name="see-also"></a>另请参阅  
 [管理项目中的映射](../core/managing-maps-within-projects.md)