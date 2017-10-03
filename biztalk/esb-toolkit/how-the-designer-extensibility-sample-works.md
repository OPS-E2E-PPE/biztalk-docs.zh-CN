---
title: "设计器扩展性示例的工作原理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f4dc622-28b8-498d-961f-df969cff9dcb
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74b72be8acb8fed465598814d2f76b32c6e3550d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-the-designer-extensibility-sample-works"></a>设计器扩展性示例的工作原理
在设计器扩展性示例的每个项目包含两个类：**扩展程序**类和**扩展提供程序**类。 这些类设计用于扩展功能，并定义属性的**ItineraryDsl**模型元素。  
  
 **扩展提供程序**类派生自**ExtensionProviderBase**类并具有**ExtensionProviderAttribute**具有属性应用于它们的确定扩展和其用途。 设置用户时，将向设计器中的用户显示这些值**扩展程序**模型元素的属性。 当**扩展提供程序**类初始化它们对的调用的构造函数**ExtensionProviderBase**并将传递给它的一种扩展类。  
  
 **扩展程序**类具有**ObjectExtender**属性应用到它们; 到**ObjectExtender**属性，它们将中的对象类型传递**ItineraryDsl** ，它们扩展。 这些类的基类各不相同，具体取决于扩展程序的类型。 对于冲突解决程序扩展程序的基类是**ObjectExtender\<冲突解决程序 >**。 对于路线服务扩展程序的基类是**ItineraryServiceExtenderBase**。 在**扩展程序**类，以下属性应用到属性： 属性一定用于正确显示在属性网格中，出于验证目的，Microsoft 企业库中包含的属性正确的序列化所需的属性和/或确定如何保持属性的属性。  
  
 在这些程序集进行编译，并在 Lib 文件夹中放入，它们是加载，且在运行时缓存由设计器。 根据需要扩展程序， **ItineraryDsl**使用反射来检查导出的类型和对这些类型的属性从缓存中加载的适用的程序集。