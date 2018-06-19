---
title: 如何配置确定形状 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Decide shape [Orchestration Designer]
- Decide shape [Orchestration Designer], configuring
- Decide shape [Orchestration Designer], branching
- configuring [Orchestration Designer], Decide shapes
ms.assetid: 70910861-3834-49e7-ab1e-d62730ea2a95
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a22368134e2c1a0d8deb277e186792158a7c2dd0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248685"
---
# <a name="how-to-configure-the-decide-shape"></a>如何配置判定形状
![](../core/media/ebiz-orch-decide.gif "ebiz_orch_decide")  
确定形状  
  
 每个分支**确定**形状，除**其他**分支，具有与之关联的规则。 您可以使用 BizTalk 表达式编辑器在规则中创建一个布尔表达式，根据该批的执行对该表达式进行求值。 因为**其他**分支意味着早期分支中的布尔表达式的求反，它不具有与之关联的表达式。  
  
 下面的规则或**其他**子句、 的分支**确定**形状可以包含其他形状，就像业务流程的任何其他部分一样。  
  
### <a name="to-configure-a-decide-shape"></a>配置判定形状  
  
1.  如果 BizTalk 表达式编辑器不可见，请右键单击该规则，然后单击**编辑布尔表达式**，或在属性窗口中，单击**省略号**(**...**) 按钮**表达式**属性。  
  
2.  在 BizTalk 表达式编辑器中，创建一个布尔表达式。 除每个分支**Else**分支。 例如：  
  
    ```  
    myMessage.Total > 1000  
    myObject.IsValid()  
    myMessage.VIP == true  
    ```  
  
### <a name="to-add-a-branch-to-a-decide-shape"></a>向判定形状添加分支  
  
1.  右键单击**确定**形状，并依次**新规则分支**。  
  
     -或者-  
  
2.  将一个新形状拖到两个现有分支之间。  
  
    > [!NOTE]
    >  若要删除分支起源**确定**形状，右键单击你想要删除，，然后单击的分支**删除**，或选择规则分支，然后按**删除**密钥。