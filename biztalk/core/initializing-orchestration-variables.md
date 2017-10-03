---
title: "初始化 Orchestration 变量 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: orchestrations, variables
ms.assetid: 770e4e55-1fb9-4b43-854c-63aec5a3c5ba
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a90fbc33343e3576d6199a0a97a7a57ca881f720
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="initializing-orchestration-variables"></a>初始化业务流程变量
可以通过在“属性”窗口中设置某一变量的值，初始化该值。 例如，你可以设置**初始值**为 32 初始化类型 System.Int32 的变量。 在向字符串类型的变量添加初始值时，必须在“属性”窗口中将初始值用引号括起来。 如果您希望该字符串包含一个引号，则使用反斜杠作为转义符；如果您希望字符串中包括的是反斜杠字符本身，则使用连续的反斜杠。 如果你未为变量指定一个值，你的变量将分配默认值就会立即创建你的业务流程的实例。  
  
 如果该变量是某个类的实例，则可以指定一个构造函数来对其进行初始化。 默认情况下，**使用默认构造函数**属性设置为**True**如果默认构造函数是可用; 因此，默认构造函数将调用它。 如果你只想要使用默认构造函数，不需要初始化的变量中再次**表达式**形状以避免两次调用的构造函数。 如果**使用默认构造函数**属性设置为**False**，将不会调用默认构造函数; 您必须在表达式中调用构造函数或之前您可以使用它进行变量赋值在您的业务流程。 此外，如果构造函数需要输入的参数，则必须设置**使用默认构造函数**到**False** ，然后调用的构造函数从**表达式**调整; 为示例中， `myVariable = myNamespace.myClass (param1, param2)`。  
  
 只有你需要显式初始化你的变量的情况是当您的业务流程包含多个一个激活收到，尽可能在**作用域**，**并行操作**或**侦听**形状。 在这种情况下，禁用了自动初始化，并且你必须使用**表达式**形状初始化你的变量。 你必须将放**表达式**形状和接收的每次激活后之前在业务流程中访问任何变量。