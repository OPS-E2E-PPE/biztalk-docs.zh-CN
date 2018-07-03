---
title: 如何将参数添加到业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, parameters
ms.assetid: 35c731ed-6327-4de7-8d2e-4d14024bda77
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 220b0fbcb9970beae10e4c76b9386c65d7fb4fca
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988838"
---
# <a name="how-to-add-parameters-to-orchestrations"></a>如何向业务流程添加参数
您可以在“业务流程视图”窗口中指定业务流程应采用的参数。 业务流程可用以下项作为参数：  
  
- 消息  
  
- 变量（包括对象）  
  
- 相关集  
  
- 角色链接  
  
- 端口  
  
  参数可以作为 In 参数或 Out 参数在业务流程之间传递。 In 参数可以通过值或通过引用传递。 Out 参数只能通过引用传递。 参数可包括变量、消息、相关集、角色链接和端口。  
  
### <a name="to-set-orchestration-parameters"></a>设置业务流程参数  
  
1.  在业务流程视图窗口中，使用**业务流程参数**文件夹添加变量、 消息和端口。  
  
2.  每个项添加到**业务流程参数**文件夹中，使用属性窗口来指定**方向**属性：  
  
    -   在中，通过值传入的参数。  
  
    -   Ref - 通过引用传入参数。  
  
    -   Out-，通过引用传递的参数。  
  
### <a name="to-add-a-parameter-to-an-orchestration"></a>向业务流程添加参数  
  
1. 在业务流程视图窗口中，右键单击**业务流程参数**文件夹，再单击所需的参数的种类。  
  
2. 对于配置的端口和角色链接，请使用向导来配置参数。  
  
    -或-  
  
    对于其他参数类型，请使用属性页来配置参数。  
  
   **参数类型**  
  
   参数可以通过值、作为引用参数或作为 Out 参数来传递。 通过值向业务流程传递参数时，将制作数据的一个副本，供业务流程使用。  
  
   使用引用参数时则不会制作副本。 包含该数据的内存位置在调用程序和业务流程之间共享，并且业务流程可以修改此内存位置的内容。 这种修改意味着参数值不仅在业务流程中更改，而且也在调用程序中更改。  
  
   Out 参数类似于引用参数，但是业务流程无法认定该参数在传入后包含有效数据；而调用程序则要求业务流程为此参数赋值。  
  
   **业务流程参数的规则**  
  
-   只能将消息和变量（包括对象）作为 Out 或引用参数传递。  
  
-   不能传出或引用参数中的业务流程**启动业务流程**形状。  
  
-   向业务流程传递 In 参数（包括所有角色链接和动态端口）之前，必须明确为这些参数赋值。  
  
## <a name="see-also"></a>请参阅  
 [业务流程形状](../core/orchestration-shapes.md)   
 [如何向业务流程添加形状](../core/how-to-add-shapes-to-orchestrations.md)   
 [如何使用选择项目类型对话框](../core/how-to-use-the-select-artifact-type-dialog-box.md)