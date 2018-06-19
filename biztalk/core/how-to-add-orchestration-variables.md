---
title: 如何添加业务流程变量 |Microsoft 文档
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
ms.openlocfilehash: bb8516ceb780e64c4f4a01370de0e7c40098f3da
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968827"
---
# <a name="how-to-add-orchestration-variables"></a>如何添加业务流程变量
业务流程视图窗口可以管理业务流程的属性 (也称为**服务**属性)，参数、 端口、 消息以及其他变量。 除了端口和消息，您还可以创建整数变量、布尔型变量、字符串变量或 .NET 类的变量。  
  
 还可以使用“业务流程视图”窗口管理属于您的范围的变量。  
  
### <a name="to-add-a-variable"></a>添加变量  
  
1.  在业务流程视图窗口中，右键单击**变量**文件夹，然后单击**新变量**。  
  
     **变量**文件夹扩展，如果折叠状态，并添加一个新的变量。  
  
2.  在“属性”窗口中，在“标识符”属性中键入名称，为该变量命名。  
  
3.  将该变量与一个类型相关联，如 .NET 类。  
  
    > [!NOTE]
    >  **类型**下拉列表包含下列预定义的变量类型：**布尔**，**字节**， **datetime**， **十进制**， **double**， **int16**， **int32**， **int64**， **sbyte****单个**，**字符串**， **timespan**， **uint16**， **uint32**，和**uint64**。 你还可以通过选择访问.NET 数据类型和类 **\<.NET 类...\>** ，它可提供**选择项目类型**对话框。  
  
4.  如果选择预定义变量类型，则可以选择指定该变量的初始值。 在属性窗口中，设置**初始值**属性。  
  
     否则，如果所选类型为 .NET 类，可以选择使用默认构造函数。 在“属性”窗口中，设置以下属性：  
  
    |属性|Description|  
    |--------------|-----------------|  
    |**使用默认构造函数**|如果默认构造函数可用于 .NET 类，此属性将确定默认构造函数是否将在您初次使用该变量时被调用：<br /><br /> True — 将调用默认构造函数。 当默认构造函数可用时，这是默认值。<br /><br /> False — 不会调用默认构造函数；您必须首先在表达式中调用某一构造函数或向变量赋值，然后才可以在您的业务流程中使用它。|  
  
    > [!NOTE]
    >  如果默认构造函数需要输入的参数，则可以设置**使用默认构造函数**到**False** ，然后调用的构造函数从**分配**调整; 为示例中， `myVariable = myNamespace.myClass (param1, param2)`。  
  
    > [!NOTE]
    >  向业务流程添加变量时，在完全定义变量之前，您将在业务流程中看到叹号。 如果在完全定义变量之前删除该变量并且叹号仍然显示在业务流程中，您可以通过创建业务流程参数，然后再删除该参数，强制业务流程删除这些叹号。  
  
### <a name="to-remove-a-variable"></a>若要删除变量  
  
-   在业务流程视图窗口中，右键单击你想要删除，然后单击的变量**删除**。