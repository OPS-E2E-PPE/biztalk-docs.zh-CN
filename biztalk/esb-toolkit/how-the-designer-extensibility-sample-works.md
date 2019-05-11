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
# <a name="how-the-designer-extensibility-sample-works"></a><span data-ttu-id="0601d-102">设计器扩展性示例工作原理</span><span class="sxs-lookup"><span data-stu-id="0601d-102">How the Designer Extensibility Sample Works</span></span>
<span data-ttu-id="0601d-103">设计器扩展性示例的每个项目包含两个类： **Extender**类和一个**扩展提供程序**类。</span><span class="sxs-lookup"><span data-stu-id="0601d-103">Each project in the Designer Extensibility sample contains two classes: an **Extender** class and an **Extension Provider** class.</span></span> <span data-ttu-id="0601d-104">这些类用于扩展功能，并定义的属性**ItineraryDsl**模型元素。</span><span class="sxs-lookup"><span data-stu-id="0601d-104">These classes are designed to extend the capabilities and define the properties of the **ItineraryDsl** model elements.</span></span>  
  
 <span data-ttu-id="0601d-105">**扩展提供程序**类派生自**ExtensionProviderBase**类，并有**ExtensionProviderAttribute**属性应用到它们，确定扩展和它的用途。</span><span class="sxs-lookup"><span data-stu-id="0601d-105">The **Extension Provider** classes derive from the **ExtensionProviderBase** class and have the **ExtensionProviderAttribute** applied to them with properties that identify the extension and its purpose.</span></span> <span data-ttu-id="0601d-106">用户设置时，将在设计器中向用户显示这些值**扩展器**模型元素上的属性。</span><span class="sxs-lookup"><span data-stu-id="0601d-106">These values will be displayed to the user in the designer when the user is setting the **Extender** property on a model element.</span></span> <span data-ttu-id="0601d-107">当**扩展提供程序**构造函数对它们调用类初始化**ExtensionProviderBase**并将扩展器类的类型传递给它。</span><span class="sxs-lookup"><span data-stu-id="0601d-107">When the **Extension Provider** classes initialize, they call to the constructor for the **ExtensionProviderBase** and pass to it the type of the extender class.</span></span>  
  
 <span data-ttu-id="0601d-108">**Extender**类具有**ObjectExtender**特性应用到它们; 到**ObjectExtender**属性，它们将中的对象类型传递**ItineraryDsl** ，它们扩展。</span><span class="sxs-lookup"><span data-stu-id="0601d-108">The **Extender** classes have an **ObjectExtender** attribute applied to them; to the **ObjectExtender** attribute, they pass the type of the object in the **ItineraryDsl** that they extend.</span></span> <span data-ttu-id="0601d-109">这些类的基类会有所不同，具体取决于扩展程序的类型。</span><span class="sxs-lookup"><span data-stu-id="0601d-109">The base class for these classes varies, depending on the type of extender.</span></span> <span data-ttu-id="0601d-110">对于冲突解决程序扩展程序的基类是**ObjectExtender\<冲突解决程序\>**。</span><span class="sxs-lookup"><span data-stu-id="0601d-110">For Resolver extenders, the base class is **ObjectExtender\<Resolver\>**.</span></span> <span data-ttu-id="0601d-111">对于路线服务扩展程序的基类是**ItineraryServiceExtenderBase**。</span><span class="sxs-lookup"><span data-stu-id="0601d-111">For Itinerary Service extenders, the base class is **ItineraryServiceExtenderBase**.</span></span> <span data-ttu-id="0601d-112">在中**扩展器**类，以下属性应用于的属性： 所需的正确显示在属性网格中，属性在出于验证目的，Microsoft Enterprise Library 中所包含的属性所需的正确序列化属性和/或确定如何保留属性的属性。</span><span class="sxs-lookup"><span data-stu-id="0601d-112">In the **Extender** classes, the following attributes are applied to the properties: attributes necessary for proper display in a property grid, attributes included in the Microsoft Enterprise Library for validation purposes, attributes necessary for proper serialization, and/or attributes that determine how properties are persisted.</span></span>  
  
 <span data-ttu-id="0601d-113">当编译这些程序集并将其放到 Lib 文件夹中时，它们加载并缓存在运行时由设计器。</span><span class="sxs-lookup"><span data-stu-id="0601d-113">When these assemblies are compiled and placed in the Lib folder, they are loaded and cached by the designer at run time.</span></span> <span data-ttu-id="0601d-114">当需要扩展器时， **ItineraryDsl**使用反射来从缓存加载适用的程序集，通过检查导出的类型和这些类型的属性。</span><span class="sxs-lookup"><span data-stu-id="0601d-114">As extenders are needed, the **ItineraryDsl** uses reflection to load the applicable assemblies from the cache by examining the types exported and the attributes on those types.</span></span>