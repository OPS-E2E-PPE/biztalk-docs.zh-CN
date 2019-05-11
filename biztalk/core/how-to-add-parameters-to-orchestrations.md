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
ms.openlocfilehash: d68fc3491f8bdb55ad8e41a43144b0cb2f8f8cf8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387267"
---
# <a name="how-to-add-parameters-to-orchestrations"></a>如何将参数添加到业务流程
可以指定您的业务流程应在业务流程视图窗口中的参数。 业务流程可以将以下项作为参数：  
  
- 消息  
  
- 变量 （包括对象）  
  
- 相关集  
  
- 角色链接  
  
- 端口  
  
  可以作为 in 参数或 out 参数的业务流程之间传递参数。 在参数可以传递按值或按引用。 Out 参数可以仅通过引用传递。 参数可以包括变量、 消息、 相关集、 角色链接和端口。  
  
### <a name="to-set-orchestration-parameters"></a>若要设置业务流程参数  
  
1.  在业务流程视图窗口中，使用**业务流程参数**文件夹添加变量、 消息和端口。  
  
2.  每个项添加到**业务流程参数**文件夹中，使用属性窗口来指定**方向**属性：  
  
    -   在中，通过值传入的参数。  
  
    -   Ref-通过引用传入的参数。  
  
    -   Out-，通过引用传递的参数。  
  
### <a name="to-add-a-parameter-to-an-orchestration"></a>若要向业务流程添加参数  
  
1. 在业务流程视图窗口中，右键单击**业务流程参数**文件夹，再单击所需的参数的种类。  
  
2. 有关配置的端口和角色链接，使用向导来配置参数。  
  
    -或-  
  
    对于其他参数类型，使用属性页来配置参数。  
  
   **参数类型**  
  
   参数可以作为引用参数传递的值，或作为 out 参数。 当一个参数通过值传递到业务流程时，创建并业务流程使用的数据的副本。  
  
   当您使用引用参数时，会不创建任何副本。 调用程序和业务流程，之间共享的内存位置包含的数据和业务流程可以修改此内存位置的内容。 这种修改意味着不仅在业务流程，而且还调用程序中，更改参数的值。  
  
   Out 参数类似于引用参数，但业务流程不能假定它包含有效的数据时传入;而是调用程序则要求业务流程，以将值分配给此参数。  
  
   **业务流程参数的规则**  
  
-   可以传递唯一消息和变量 （包括对象） 作为 out 或引用参数。  
  
-   不能传出或引用参数中的业务流程**启动业务流程**形状。  
  
-   在参数中，包括任何角色链接和动态端口，必须明确赋值前被传递到业务流程。  
  
## <a name="see-also"></a>请参阅  
 [业务流程形状](../core/orchestration-shapes.md)   
 [如何向业务流程添加形状](../core/how-to-add-shapes-to-orchestrations.md)   
 [如何使用选择项目类型对话框](../core/how-to-use-the-select-artifact-type-dialog-box.md)