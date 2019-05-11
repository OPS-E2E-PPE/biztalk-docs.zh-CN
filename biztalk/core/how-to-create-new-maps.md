---
title: 如何创建新映射 |Microsoft Docs
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
ms.openlocfilehash: 9eff8e4776ea1ead46f28572e4c950b3d72d970f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385502"
---
# <a name="how-to-create-new-maps"></a>如何创建新映射

## <a name="overview"></a>概述
若要生成新的 BizTalk 映射，有三个主要步骤执行：  
  
1. 创建新 BizTalk 项目中的映射。  
  
2. 向映射添加源和目标架构。  
  
3. 生成的链接集，这样一来，中间 functoid 指定如何将源架构映射到目标架构。  
  
   在当前上下文中，这三个步骤的前两个被视为"创建"映射。 第三个步骤将被视为"构建"映射。 许多与构建映射过程相关的任务的分步说明，请参阅[使用 Functoid 创建更复杂的映射](../core/using-functoids-to-create-more-complex-mappings.md)。  
  
## <a name="create-a-new-map"></a>创建新的映射 
  
1. 右键单击 BizTalk 项目在解决方案资源管理器，选择**外**，然后选择**新项**。  
  
2. 在中**添加新项**对话框中**模板**区域中，选择**映射**。  
  
3. 选择中的文本**名称**框中，键入映射的名称，然后选择**添加**。  
  
    BizTalk 映射器将在 Microsoft 中打开[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]编辑窗口，显示三个不同的窗格，通过并行。 从左到右，两个窗格显示源架构，网格 （它们可能具有多个页面） 和目标架构。  
  
   > [!IMPORTANT]
   >  不能使用以下名称用于映射："XmlContent"、"SourceSchemas"、"TargetSchemas"或者"XsltArgumentListContent"。 由于编译到.NET 程序集作为结果生成的 C# 代码所生成的命名限制，不能使用这些名称。  
  
4. 在 BizTalk 映射器中，在左窗格中，选择**打开源架构**。  
  
5. 在中**BizTalk 类型选取器**对话框框中，展开**架构**节点，选择相应的源架构，然后选择**确定**。  

   > [!TIP]
   > **从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** ，可以调整大小类型选取器窗口以查看您的架构的完整名称。
  
    如果只有在源架构中，存在单个根或根节点的架构使用已建立**根引用**的属性**架构**节点，在左窗格中，并且您打开源架构可以转到步骤 7。  
  
6. 如果源架构包含多个根节点，并已使用源架构建立任何根节点**架构**节点的**根引用**属性，请在**源的根节点架构**对话框中，选择相应的根节点，然后选择**确定**。  
  
   > [!IMPORTANT]
   >  如果您在 BizTalk 映射器中选择架构的根节点，并随后更改**根引用**属性在架构中，下次在 BizTalk 映射器中打开该架构的根节点不会更新到新的根引用配置在 BizTalk 编辑器中。  
  
7. 在 BizTalk 映射器中，在右窗格中，选择**打开目标架构**。  
  
8. 在中**BizTalk 类型选取器**对话框框中，展开**架构**节点在树中，如有必要，选择相应的目标架构中，然后选择**确定**。  
  
    如果只有一个根目标架构中存在或已使用目标架构建立了根节点**根引用**的属性**架构**节点，将打开目标架构在右窗格中，您不需要执行步骤 9。  
  
9. 如果目标架构具有多个根节点，并且已使用目标架构建立任何根节点**根引用**的属性**架构**节点，请在**根节点为目标架构**对话框中，选择相应的根节点，然后选择**确定**。  
  
     在右窗格中打开目标架构。  
  
## <a name="see-also"></a>请参阅  
 [管理项目中的映射](../core/managing-maps-within-projects.md)