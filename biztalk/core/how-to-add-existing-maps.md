---
title: 如何添加现有映射 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fbeaea05-016e-488c-90f3-af8c6b9a3d84
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a61fb0faf5f4eed614257361b00cea781db2d94
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247453"
---
# <a name="how-to-add-existing-maps"></a>如何添加现有的映射
有时，您可能希望向 BizTalk 项目添加现有映射。 在进行此操作之前，必须确保映射的源架构和目标架构都包含在要向其添加映射的 BizTalk 项目中，或均由相应的 .NET 程序集引用。  
  
### <a name="to-add-an-existing-map-to-a-biztalk-project"></a>向 BizTalk 项目添加现有映射  
  
1.  右键单击解决方案资源管理器中的 BizTalk 项目，指向**添加**，然后单击**现有项**。  
  
2.  在**添加现有项**对话框中，浏览到包含要添加，选中它，，然后单击的映射的文件夹**添加**。  
  
     在 BizTalk 映射程序中打开代码图。 新添加的映射也会在解决方案资源管理器中显示为当前 BizTalk 项目的子项。  
  
    > [!NOTE]
    >  如果您浏览到的文件夹不是 BizTalk 项目文件夹，而在项目文件夹中创建了所添加映射的副本，并且添加到项目中的正是此映射副本， 那么，对该映射进行的后续更改将保存在这个副本中，而不会保存在另一文件夹下的原始映射中。  
  
    > [!IMPORTANT]
    >  BizTalk 映射只能通过 BizTalk 映射器打开，该映射器的宿主是 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 外壳程序。 如果您在 Windows 资源管理器中双击某个映射，并且已经正确加载了相应的架构，则会先打开一个新 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 实例，然后 BizTalk 映射器再打开该映射。  
  
    > [!NOTE]
    >  如果现有映射中包含自定义 functoid，则必须将相应 DLL 复制到文件夹“%BTSINSTALLPATH%\Developer Tools\Mapper Extensions”。 否则，映射将不会加载，并且会引发错误，因为加载自定义 functoid 失败。  
  
## <a name="see-also"></a>另请参阅  
 [管理项目中的映射](../core/managing-maps-within-projects.md)   
 [开发自定义 Functoid](../core/developing-custom-functoids.md)