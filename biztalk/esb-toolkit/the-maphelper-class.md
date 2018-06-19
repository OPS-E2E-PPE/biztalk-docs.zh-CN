---
title: MapHelper 类 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c552c066-835f-4515-939f-dd465a7a5ed0
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de74610c40b37560abcbce040d80320525f0a21c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295109"
---
# <a name="the-maphelper-class"></a><span data-ttu-id="6164b-102">MapHelper 类</span><span class="sxs-lookup"><span data-stu-id="6164b-102">The MapHelper Class</span></span>
<span data-ttu-id="6164b-103">使用**MapHelper**类来执行转换，不使用 Web 服务的转换情况下直接。</span><span class="sxs-lookup"><span data-stu-id="6164b-103">Use the **MapHelper** class to perform transformations directly without using the transformation Web service.</span></span>  
  
 <span data-ttu-id="6164b-104">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]安装程序安装并注册该程序集**Microsof.Practices.ESB.Transform.dll**与**MapHelper**全局程序集缓存中的类。</span><span class="sxs-lookup"><span data-stu-id="6164b-104">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] installer installs and registers the assembly **Microsof.Practices.ESB.Transform.dll** with the **MapHelper** class in the global assembly cache.</span></span>  
  
 <span data-ttu-id="6164b-105">**MapHelper**类公开两个公共方法：</span><span class="sxs-lookup"><span data-stu-id="6164b-105">The **MapHelper** class exposes two public methods:</span></span>  
  
-   <span data-ttu-id="6164b-106">**TransformMessage**。</span><span class="sxs-lookup"><span data-stu-id="6164b-106">**TransformMessage**.</span></span> <span data-ttu-id="6164b-107">一个字符串，包含要转换的消息和包含部署在 BizTalk 映射的完全限定的名称的字符串，则将使用此方法作为参数。</span><span class="sxs-lookup"><span data-stu-id="6164b-107">This method takes as parameters a string that contains the message to transform and a string that contains the fully qualified name of a map deployed in BizTalk.</span></span> <span data-ttu-id="6164b-108">该方法返回包含已转换的文档的字符串。</span><span class="sxs-lookup"><span data-stu-id="6164b-108">The method returns a string containing the transformed document.</span></span>  
  
-   <span data-ttu-id="6164b-109">**TransformMessageStream**。</span><span class="sxs-lookup"><span data-stu-id="6164b-109">**TransformMessageStream**.</span></span> <span data-ttu-id="6164b-110">包含要转换的消息的流和包含部署在 BizTalk 映射的完全限定的名称的字符串，则将使用此方法作为参数。</span><span class="sxs-lookup"><span data-stu-id="6164b-110">This method takes as parameters a stream that contains the message to transform and a string that contains the fully qualified name of a map deployed in BizTalk.</span></span> <span data-ttu-id="6164b-111">该方法返回一个字符串，包含转换后的文档。</span><span class="sxs-lookup"><span data-stu-id="6164b-111">The method returns a string that contains the transformed document.</span></span>