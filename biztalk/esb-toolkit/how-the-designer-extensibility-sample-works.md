---
title: 设计器扩展性示例工作原理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f4dc622-28b8-498d-961f-df969cff9dcb
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 963c5ae2f778f193135fa73366d81cc359f5a798
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397122"
---
# <a name="how-the-designer-extensibility-sample-works"></a>设计器扩展性示例工作原理
设计器扩展性示例的每个项目包含两个类： **Extender**类和一个**扩展提供程序**类。 这些类用于扩展功能，并定义的属性**ItineraryDsl**模型元素。  
  
 **扩展提供程序**类派生自**ExtensionProviderBase**类，并有**ExtensionProviderAttribute**属性应用到它们，确定扩展和它的用途。 用户设置时，将在设计器中向用户显示这些值**扩展器**模型元素上的属性。 当**扩展提供程序**构造函数对它们调用类初始化**ExtensionProviderBase**并将扩展器类的类型传递给它。  
  
 **Extender**类具有**ObjectExtender**特性应用到它们; 到**ObjectExtender**属性，它们将中的对象类型传递**ItineraryDsl** ，它们扩展。 这些类的基类会有所不同，具体取决于扩展程序的类型。 对于冲突解决程序扩展程序的基类是**ObjectExtender\<冲突解决程序\>**。 对于路线服务扩展程序的基类是**ItineraryServiceExtenderBase**。 在中**扩展器**类，以下属性应用于的属性： 所需的正确显示在属性网格中，属性在出于验证目的，Microsoft Enterprise Library 中所包含的属性所需的正确序列化属性和/或确定如何保留属性的属性。  
  
 当编译这些程序集并将其放到 Lib 文件夹中时，它们加载并缓存在运行时由设计器。 当需要扩展器时， **ItineraryDsl**使用反射来从缓存加载适用的程序集，通过检查导出的类型和这些类型的属性。