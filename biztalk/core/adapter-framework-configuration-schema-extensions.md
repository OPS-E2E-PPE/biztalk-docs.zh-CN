---
title: 适配器框架配置架构扩展 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 27c9727f-5f97-41ee-a0b8-45d90427b0af
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac88ce098f546bf97fcb2d3897f71f4e6429966f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361489"
---
# <a name="adapter-framework-configuration-schema-extensions"></a><span data-ttu-id="e38f6-102">适配器框架配置架构扩展</span><span class="sxs-lookup"><span data-stu-id="e38f6-102">Adapter Framework Configuration Schema Extensions</span></span>
<span data-ttu-id="e38f6-103">BizTalk 适配器框架支持动态生成基于 XSD 定义的用户界面。</span><span class="sxs-lookup"><span data-stu-id="e38f6-103">The BizTalk Adapter Framework supports the dynamic generation of user interfaces based on an XSD definition.</span></span> <span data-ttu-id="e38f6-104">该适配器还提供必需的 XSD 和适配器框架将创建允许用户输入值的属性页。</span><span class="sxs-lookup"><span data-stu-id="e38f6-104">The adapter supplies the required XSD and the Adapter Framework creates a property page that allows the user to enter values.</span></span>  
  
 <span data-ttu-id="e38f6-105">若要创建自定义用户界面，适配器框架提供若干扩展。</span><span class="sxs-lookup"><span data-stu-id="e38f6-105">To create custom user interfaces, the Adapter Framework provides several extensions.</span></span> <span data-ttu-id="e38f6-106">若要使用这些扩展，必须导入适配器框架架构 (BizTalkAdapterFramework.xsd)。</span><span class="sxs-lookup"><span data-stu-id="e38f6-106">To use these extensions, you must import the Adapter Framework schema (BizTalkAdapterFramework.xsd).</span></span> <span data-ttu-id="e38f6-107">通过导入架构，可以访问并使用该适配器配置架构中的修饰和专用的类型。</span><span class="sxs-lookup"><span data-stu-id="e38f6-107">By importing the schema, you can access and use the decorations and specialized types in the adapter configuration schema.</span></span>  
  
 <span data-ttu-id="e38f6-108">使用修饰标记和在本部分中所述的内置类型自定义适配器的属性网格。</span><span class="sxs-lookup"><span data-stu-id="e38f6-108">Use the decoration tags and built-in types discussed in this section to customize the property grid for an adapter.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e38f6-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="e38f6-109">In This Section</span></span>  
  
-   [<span data-ttu-id="e38f6-110">启用适配器框架配置架构扩展</span><span class="sxs-lookup"><span data-stu-id="e38f6-110">Enabling Adapter Framework Configuration Extensions</span></span>](../core/enabling-adapter-framework-configuration-extensions.md)  
  
-   [<span data-ttu-id="e38f6-111">适配器框架配置架构修饰标记</span><span class="sxs-lookup"><span data-stu-id="e38f6-111">Adapter Framework Configuration Schema Decoration Tags</span></span>](../core/adapter-framework-configuration-schema-decoration-tags.md)  
  
-   [<span data-ttu-id="e38f6-112">适配器的自定义配置架构示例</span><span class="sxs-lookup"><span data-stu-id="e38f6-112">Examples of Custom Configuration Schemas for Adapters</span></span>](../core/examples-of-custom-configuration-schemas-for-adapters.md)