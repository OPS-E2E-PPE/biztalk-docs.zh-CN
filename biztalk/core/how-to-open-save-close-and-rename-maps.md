---
title: 如何打开、 保存、 关闭和重命名映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9aa88ca7-a731-4295-8692-6dd36fdf0872
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a95ba8e22baa10a0b47721b8a8b3eb3554e2b8a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968758"
---
# <a name="how-to-open-save-close-and-rename-maps"></a>如何打开、 保存、 关闭和重命名映射
在 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，映射在文件系统中以扩展名为 .btm 的文件形式存在。 不过，它是更常见，若要使用映射作为 BizTalk 项目，从其执行操作，如打开、 保存和关闭映射中的项。  
  
### <a name="to-open-a-map"></a>若要打开地图  
  
1.  在解决方案资源管理器，选择你想要打开的映射。  
  
2.  上**视图**菜单上，单击**打开**。  
  
     在 BizTalk 映射器中打开该映射。  
  
    > [!NOTE]
    >  您可以右键单击解决方案资源管理器中的映射，然后单击**打开**，或者仅双击解决方案资源管理器中的映射。  
  
### <a name="to-save-a-map"></a>若要保存映射  
  
1. 在解决方案资源管理器，选择你想要保存的映射。  
  
2. 上**文件**菜单上，单击 * * 保存 *\<名称的映射\>* * *。  
  
### <a name="to-save-a-map-to-a-new-location"></a>若要将映射保存到新位置  
  
1.  在解决方案资源管理器，选择你想要将保存到新位置的映射。  
  
2.  上**文件**菜单上，单击**保存*\<名称的映射\>* 作为**。  
  
3.  在中**将文件另存为**对话框中，浏览到要保存该映射的文件夹位置。  
  
4.  在中**文件名**框中，键入该文件的名称，然后单击**保存**。  
  
    > [!IMPORTANT]
    >  不使用映射以下名称:"XmlContent"、"SourceSchemas"、"TargetSchemas"或"XsltArgumentListContent"，因此，这样做将会编译问题导致在 C# 中生成的代码的相应的.NET 程序集。 有关问题及其解决方案的信息，请参阅[故障排除映射](../core/troubleshooting-maps.md)。  
  
### <a name="to-rename-a-map"></a>若要重命名映射  
  
1.  在解决方案资源管理器，右键单击你想要重命名，然后单击该地图**重命名**。  
  
2.  中将出现在解决方案资源管理器中的映射的位置的编辑框，键入新名称的地图或更改其现有的名称，，然后按 ENTER。  
  
> [!NOTE]
>  您可能还需要更改**类型名称**映射时，其重命名。 您更改**类型名称**通过选择**地图**中的解决方案资源管理器并输入中的新名称**类型名称**属性窗口中。  
  
#### <a name="to-close-a-map"></a>若要关闭映射  
  
1. 在解决方案资源管理器，选择你想要关闭的映射。  
  
2. 在 **“文件”** 菜单上，单击 **“关闭”**。  
  
   > [!NOTE]
   >  此外可以单击关闭图标 ([**x**]) 在 Microsoft 的右上角[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]编辑窗口。  
  
## <a name="see-also"></a>请参阅  
 [管理项目中的映射](../core/managing-maps-within-projects.md)