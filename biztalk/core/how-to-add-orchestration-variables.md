---
title: 如何添加业务流程变量 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, variables
ms.assetid: c387cd56-5443-4de2-bbda-be34b95cbe71
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 876799a7baf58d7dacc8185d09d6f9d63a70127d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343255"
---
# <a name="how-to-add-orchestration-variables"></a>如何添加业务流程变量
业务流程视图窗口可以管理业务流程的属性 (也称为**服务**属性)，参数、 端口、 消息和其他变量。 除了端口和消息，可以创建整数变量、 布尔变量、 字符串变量或.NET 类的变量。  
  
 业务流程视图窗口还可用于管理属于你作用域的变量。  
  
### <a name="to-add-a-variable"></a>添加变量  
  
1.  在业务流程视图窗口中，右键单击**变量**文件夹，然后单击**新变量**。  
  
     **变量**文件夹会展开，如果处于折叠状态，并将其添加一个新的变量。  
  
2.  通过在属性窗口中的标识符属性中键入一个名称命名该变量。  
  
3.  将该变量与一个类型，如.NET 类相关联。  
  
    > [!NOTE]
    >  **类型**下拉列表包含以下预定义的变量类型：**布尔**，**字节**， **datetime**， **十进制**，**双**， **int16**， **int32**， **int64**， **sbyte****单个**，**字符串**， **timespan**， **uint16**， **uint32**，和**uint64**。 您还可以通过选择访问.NET 数据类型和类**\<.NET 类...\>**，这会打开**选择项目类型**对话框。  
  
4.  如果选择预定义的变量类型，您可以指定该变量的初始值。 在属性窗口中设置**初始值**属性。  
  
     否则，如果所选的类型是一个.NET 类，必须使用默认构造函数的选项。 在属性窗口中，设置以下属性：  
  
    |属性|Description|  
    |--------------|-----------------|  
    |**使用默认构造函数**|如果默认构造函数可用于.NET 类，此属性确定当首次使用该变量时，是否将调用默认构造函数：<br /><br /> True — 将调用默认构造函数。 默认构造函数可用时，这是默认值。<br /><br /> False — 不会调用默认构造函数;必须在表达式中调用构造函数或之前您可以在业务流程中使用它进行变量赋值。|  
  
    > [!NOTE]
    >  如果默认构造函数要求输入的参数，则可以设置**使用默认构造函数**到**False** ，然后调用从构造函数**分配**形状; 为示例中， `myVariable = myNamespace.myClass (param1, param2)`。  
  
    > [!NOTE]
    >  当将变量添加到业务流程中，完全定义之前时，你将看到在业务流程中的感叹号。 如果之前已完全定义和叹号仍然显示在业务流程中删除该变量，则可以强制业务流程，以通过创建并随后将删除将业务流程参数中删除这些叹号。  
  
### <a name="to-remove-a-variable"></a>若要删除变量  
  
-   在业务流程视图窗口中，右键单击你想要删除，然后单击的变量**删除**。