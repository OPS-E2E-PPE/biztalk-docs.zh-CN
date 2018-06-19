---
title: 如何创建新映射 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 43b36cd8-f28e-4349-87d5-c94b7d8761bf
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 910d79782f4332ae1d706e12a8c5dda8c399a41b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249869"
---
# <a name="how-to-create-new-maps"></a>如何创建新的映射

## <a name="overview"></a>概述
若要生成新的 BizTalk 映射，有三个主要步骤执行：  
  
1.  创建 BizTalk 项目中的新映射。  
  
2.  向地图添加源和目标架构。  
  
3.  生成的链接集，并可能中间 functoid 指定如何将源架构映射到目标架构。  
  
 在当前上下文中，以上三个步骤中的前两个步骤被视为“创建”映射。 第三个步骤被视为“构建”映射。 许多生成图的过程与相关的任务的分步说明，请参阅[创建更复杂的映射到使用 Functoid](../core/using-functoids-to-create-more-complex-mappings.md)。  
  
## <a name="create-a-new-map"></a>创建一个新图 
  
1.  右键单击 BizTalk 项目在解决方案资源管理器，选择**添加**，然后选择**新项**。  
  
2.  在**添加新项**对话框中，在**模板**区域中，选择**映射**。  
  
3.  选择中的文本**名称**框中，键入的地图的名称，然后选择**添加**。  
  
     BizTalk 映射程序将在 Microsoft 中打开[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]编辑窗口中，显示三个不同的窗格，并排显示。 从左到右，这些窗格显示的源架构，网格中 （它们可能具有多个页），和目标架构。  
  
    > [!IMPORTANT]
    >  不能使用适用于映射以下名称:"XmlContent"、"SourceSchemas"、"TargetSchemas"或"XsltArgumentListContent"。 因为.NET 程序集编译为生成的 C# 代码的结果会产生命名限制，不能使用这些名称。  
  
4.  在 BizTalk 映射程序中，在左窗格中，选择**打开源架构**。  
  
5.  在**BizTalk 类型选取器**对话框框中，展开**架构**节点，选择合适的源架构中，，然后选择**确定**。  

    > [!TIP] 
    > **从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** ，你可以调整大小类型选取器窗口以查看您的架构的完整名称。
  
     如果只有单个根源架构中存在或已建立了根节点进行架构使用**根引用**属性**架构**节点，在左窗格中，并且你打开的源架构可以继续执行步骤 7。  
  
6.  如果源架构具有多个根节点，并且没有根节点建立源架构使用**架构**节点的**根引用**属性，请在**源的根节点架构**对话框中，选择适当的根节点，然后选择**确定**。  
  
    > [!IMPORTANT]
    >  如果您在 BizTalk 映射程序中选择架构的根节点，然后更高版本更改**根引用**属性在架构中，下次在 BizTalk 映射程序中打开架构的根节点不会更新到新的根引用配置在 BizTalk 编辑器。  
  
7.  在 BizTalk 映射程序中，在右窗格中，选择**打开目标架构**。  
  
8.  在**BizTalk 类型选取器**对话框框中，展开**架构**节点在树中，如果有必要，请选择适当的目标架构，然后选择**确定**。  
  
     如果只有单个根目标架构中存在或已建立了根节点进行目标架构使用**根引用**属性**架构**节点，目标架构打开在右窗格中，并且你将不需要执行步骤 9。  
  
9. 如果目标架构具有多个根节点，并且没有根节点建立目标架构使用**根引用**属性**架构**节点，请在**根节点对于目标架构**对话框中，选择适当的根节点，然后选择**确定**。  
  
     在右窗格中打开目标架构。  
  
## <a name="see-also"></a>另请参阅  
 [管理项目中的映射](../core/managing-maps-within-projects.md)