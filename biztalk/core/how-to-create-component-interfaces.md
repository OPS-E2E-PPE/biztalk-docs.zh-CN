---
title: 如何创建组件接口 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating component interfaces
- component interfaces, creating
ms.assetid: 9def053a-cbf6-4b34-b2e8-b2d03bffc5fe
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86ee68edba66b05d3c2541dd9c41cc074bd790b7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249293"
---
# <a name="how-to-create-component-interfaces"></a>如何创建组件接口
您将使用 PeopleSoft 应用程序设计器创建组件接口。 （有关应用程序设计器的详细信息，请参阅 PeopleSoft Enterprise 文档。）  
  
 可以从组件视图中的记录添加属性。 在组件接口中，您可以删除不希望公开的属性。 可以通过以下方式重命名属性：单击属性，然后再次单击，直到可以键入新的名称。 重命名属性后，只需通过新的属性名即可在组件接口中对其进行引用，无需使用底层组件名。  
  
 属性旁边可能有各种图标。 例如，EMPLID 有一个图标指示它是来自底层记录的键字段。 NAME 有一个图标指示它是来自底层记录的备用键字段。 （有关属性图标的完整列表，请参阅 PeopleBooks 文档。）  
  
### <a name="creating-a-new-component-interface"></a>创建新的组件接口  
  
1.  打开 PeopleSoft 应用程序设计器。  
  
2.  在“文件”  菜单上，单击“新建” 。  
  
     ![](../core/media/psadapter-42-ps-new-compinterface.gif "PSAdapter_42_PS_New_CompInterface")  
  
3.  在**新建**对话框中，选择**组件接口**，然后单击**确定**。  
  
     ![](../core/media/psadapter-43-ps-selectsourcecomp.gif "PSAdapter_43_PS_SelectSourceComp")  
  
4.  在**组件接口选择源组件**窗口中，选择要用作基础组件接口，然后单击的组件**选择**。  
  
     ![](../core/media/psadapter-44-ps-appdesigner1.gif "PSAdapter_44_PS_AppDesigner1")  
  
    > [!NOTE]
    >  如果组件接口很大，请手动公开组件属性。  
  
5.  在**应用程序设计器**对话框框中，选择以下选项之一：  
  
    -   单击**否**以创建而不显示属性的组件接口并手动公开组件属性。  
  
         a. 将相关字段从左窗格中拖动到右窗格中。  
  
         b. 若要选择要执行的各种函数，右键单击是右或向左窗格中，根据哪些窗格处于活动状态。  
  
         有关完整的功能列表，请参阅 PeopleBooks 文档。  
  
    -   单击**是**创建组件接口和显示的基础组件接口的属性。  
  
         ![](../core/media/psadapter-45-ps-appdesigner2.gif "PSAdapter_45_PS_AppDesigner2")  
  
## <a name="see-also"></a>另请参阅  
 [组件接口中的标准方法](../core/standard-methods-in-component-interfaces.md)   
 [附录 c： 使用组件接口](../core/appendix-c-using-component-interfaces.md)   
 [附录 a： 组件接口方法](../core/appendix-a-component-interface-methods.md)